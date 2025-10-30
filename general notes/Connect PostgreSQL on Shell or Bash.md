---
tags:
  - PostgreSQL
  - Shell
---

#### sign in into psql:
- psql --username=freecodecamp --dbname=periodic_table
#### dump db.sql:
- pg_dump -cC --inserts -U freecodecamp periodic_table > periodic_table.sql
#### build from dump:
- psql -U postgres < periodic_table.sql
