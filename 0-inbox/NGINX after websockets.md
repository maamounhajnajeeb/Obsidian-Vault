---
tags:
  - brokers
---
# for rate_limit
limit_req_zone $binary_remote_addr zone=one:10m rate=5r/s;

upstream django {
    server app-1:8000;
    # second server
}

# Return 444 status code & close connection if no Host header present
# server {
#     listen                  80 default_server;
#     # return                  444;
#     return                  443;
# }

server {
    server_name localhost;
    # server_name .dev.brokers-app.sy;
    listen 80;
    # Redirect all HTTP requests to HTTPS
    return 301 https://$server_name$request_uri;
}


server {
    # change it to brokers.sy
    server_name localhost;
    # server_name .dev.brokers-app.sy;

    # # http and https settings # #
    listen 80; # for normal http
    listen 443 ssl; # for normal https
    listen [::]:443 ssl;
    http2 on;
    ssl_certificate /etc/nginx/conf.d/localhost.crt;
    ssl_certificate_key /etc/nginx/conf.d/localhost.key;

    # proxy_ssl_trusted_certificate /etc/nginx/conf.d/localhost.crt;
    # proxy_ssl_verify on;

    # ssl_verify_client on;
    # ssl_trusted_certificate /etc/ssl/cachain.pem;
    # ssl_ocsp on; 

    # # Optimize SSL settings # #
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_prefer_server_ciphers on;
    ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
    ssl_session_cache shared:SSL:20m;
    ssl_session_timeout 4h;
    # ssl_handshake_timeout 10s;

    # note: Enable HSTS (HTTP Strict Transport Security)
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
    
    # note: add_header X-Frame-Options DENY;
    add_header X-Content-Type-Options nosniff;
    add_header X-XSS-Protection "1; mode=block";

    # match server_ok {
    #     status 200-399;
    #     body   !~ "maintenance mode"; Here the health check is passed if the status code of the response is in the range 200–399, and its body does not contain the string maintenance mode.
    # here is another check
    # status 200;
    # header Content-Type = text/html;
    # body   ~ "Welcome to nginx!";
    # }

    error_log /var/log/nginx/error.log warn;
    access_log /var/log/nginx/access.log;

    location / {
        # resolver 127.0.0.1;
        proxy_pass http://django;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_redirect off;
        client_max_body_size 100M;
        # check_health match=server_ok uri=/admin;

        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Original-URI $request_uri;

        # WebSocket support (if needed)
        # proxy_http_version 1.1;
        # proxy_set_header Upgrade $http_upgrade;
        # proxy_set_header Connection "upgrade";

    }

    location ~ ^/(admin|ar/admin)/ {
        # allow 00000;
        # deny all;
        # rate_limit
        limit_req zone=one;  # burst=5 delay=3  first 3 requests (delay) are passed without delay, next 2 requests (burst - delay) are delayed in such a way that the overall rate is not greater than specified

        # for slowdown downlowds
        limit_rate_after 500k;
        limit_rate       20k;


        proxy_pass http://django;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_redirect off;
        client_max_body_size 100M;

        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Original-URI $request_uri;
    }

    # location /ar/admin/ {
    #     # allow 00000;
    #     # deny all;
    #     # rate_limit
    #     limit_req zone=one;  # burst=5 delay=3  first 3 requests (delay) are passed without delay, next 2 requests (burst - delay) are delayed in such a way that the overall rate is not greater than specified

    #     # for slowdown downlowds
    #     limit_rate_after 500k;
    #     limit_rate       20k;


    #     proxy_pass http://django;
    #     proxy_set_header Host $host;
    #     proxy_set_header X-Real-IP $remote_addr;
    #     proxy_redirect off;
    #     client_max_body_size 100M;

    #     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    #     proxy_set_header X-Forwarded-Proto $scheme;
    #     proxy_set_header X-Original-URI $request_uri;

    # }

    location /static {
        alias /app/static;
        expires 30d;
        add_header Cache-Control "public, max-age=2592000";
        # optimize
        sendfile on;
        tcp_nopush on;
        sendfile_max_chunk 1m;
    }

    location /files {
        alias /app/files;
        # expires 30d;
        # add_header Cache-Control "public, max-age=2592000";
    }

        # Enable gzip compression
    gzip on;
    gzip_vary on;
    gzip_min_length 1000;
    gzip_proxied expired no-cache no-store private auth;
    gzip_types text/plain text/css text/xml text/javascript application/x-javascript application/xml;
    gzip_disable "MSIE [1-6]\.";
    # for clients that dont accept gzip
    gunzip on;
}
