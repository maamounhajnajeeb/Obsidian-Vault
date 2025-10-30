---
tags:
  - brokers
---
http {
    
    # will include all types, like (text/css, text/html .....)
    include mime.types;

    server {
        listen 80;
        root /var/www/html;

        # it will automatically search for index.html in the root directory
        # index index.html;

        # when never we go to /number/()
        # it will show the content from /count location block
        # but in the url it's /number
        rewrite ^/number/(\w+) /count/$1;

        location ~* /count/[0-9] {
            root /var/www/html;
            
            try_files /index.html =404;
        }

        location /fruits {
            # this root will be /var/www/html/fruits
            # because NGINX add the location to the root
            root /var/www/html;
            
            # NGINX will automatically search for index.html
        }

        location /carbs {
            # using alias will use fixed path
            # and append the location to the end of it
            alias /var/www/html/fruits;

            # NGINX will automatically search for index.html
        }

        location /vegetables {
            root /var/www/html;
            
            # first look at vegetables/veggies.html
            # then look at: index.html at root: /var/www/html/index.html
            # if no one exists, through 404 not found error
            # <start with> <backup page> <no one exists=404>
            try_files /vegetables/veggies.html /index.html =404;
        }

        location /corps {
            # it will redirect user to /frutis location
            # and we will never see /corps in the url
            return 307 /fruits;
        }
    }
}

events {}