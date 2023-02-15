### Login to db
```text
psql -U username
psql -U username database
psql -U username -d database
```

### Databases list
```text
\l
```

### Connect to database
```text
\c database
```

### Database Tables list
```text
\dt
```

### DROP, CREATE 
```text
CREATE DATABASE db_title;
DROP DATABASE db_title;
```

### Create new db user and add authorities
```text
CREATE USER username WITH PASSWORD 'superlong-secret-passwoprd';
GRANT ALL ON DATABASE notes_db TO noteholder;
ALTER DATABASE notes_db OWNER TO noteholder;
```

### application.data
```text
spring.datasource.url=jdbc:postgresql://192.168.0.10:3232/database
spring.datasource.username=username
spring.datasource.password=supersecretpassword
```

## Examples
```text
DELETE FROM author WHERE name = 'supersecretpassword';
DELETE FROM author WHERE name = 'name';
DELETE FROM author WHERE id > 1;
```
