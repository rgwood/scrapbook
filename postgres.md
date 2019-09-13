# Postgres (WIP)

`psql -d scrapbook -U reilly -h 10.211.55.7`

## Enabling connections

Edit `/var/lib/pgsql/data/pg_hba.conf`

Allow username/pass logins from localhost and anything on the private network: 
```
host    all             all             127.0.0.1/32            md5
host    all             all             10.0.0.0/8              md5
host    all             all             192.168.0.0/16          md5
```

Reload after config file change: `systemctl reload postgresql`


Now, make Postgres listen for remote connections.

Edit `/var/lib/pgsql/data/postgresql.conf`, set `listen_addresses = '*'`

Restart: `systemctl restart postgresql`

View status and recent logs: `systemctl status postgresql`

## Passwords

[PG passwords can be stored in ~/.pgpass](https://www.postgresql.org/docs/8.3/libpq-pgpass.html).
