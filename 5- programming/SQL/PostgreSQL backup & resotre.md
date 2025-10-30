##### see command docs
```bash
psql -U <db user> <db name> pg_dump --help
```
##### to backup data in a file with .sql format
```bash
psql pg_dump -U <db user> <db name> --data-only <optional> -f <full backup file path.sql>
```
##### to restore backup data
```bash
psql pg_dump -U <db user> <db name> -f <full backup file path.sql>
```
##### to save backup data in format other than .sql
```bash
psql pg_dump -U <db user> <db name> -F c -f <full backup file path.dump>
```
##### to restore backup data in format other than .sql
```bash
psql pg_restore -U <db user> <db name> -F c <full backup file path.dump>
```