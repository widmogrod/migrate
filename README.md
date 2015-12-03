# migrate
## Introduction
Run database migrations fast and easy.

Given project is based on [github.com/mattes/migrate](https://github.com/mattes/migrate).

## How to use it
### Migration directory
Assuming that you have directory `./migrations` with migration files like:
```
001_initial_plan_to_do_sth.up.sql     # up migration instructions
001_initial_plan_to_do_sth.down.sql   # down migration instructions
002_xxx.up.sql
002_xxx.down.sql
...
```

You are ready to use this docker image.

### Run migrations
```bash
$DB_DSN="postgres://postgres:postgres@postgres:5432/srv?sslmode=disable"
docker run -v ./migrations:/migrations \
    widmogrod/migrate -url $DB_DSN up
```

> **NOTE:** More documented options you can find here: https://github.com/mattes/migrate#usage-from-terminal

### Available drives
  - PostgreSQL
  - Cassandra
  - SQLite
  - MySQL (experimental)
