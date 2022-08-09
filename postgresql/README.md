## Install PostgreSQL 12 on Linux
Same steps as 11, but pg_hba.conf and postgresql.conf were not in /var/lib/pgsql/11/data/ anymore. They locate in /etc/postgresql/12/main

## Install PostgreSQL 11 on Linux
1. Go to Dowload PostgreSQL site, choose your OS and then follow the steps
2. After installing and starting the PostgreSQL services, run: `sudo su - postgres`, enter sudo password.
3. If you has not set PATH yet, run `export PATH="path_to_bin:$PATH"`. E.g `export PATH="/usr/pgsql-11/bin:$PATH"`.
4. Run `psql` to open psql interface. Now, we can use sql queries with postgresql
### Connect to PostgreSQL
1. Run Query `SHOW hba_file;` to show path of hba_file (E.g `/var/lib/pgsql/11/data/pg_hba.conf`)
2. Open `/var/lib/pgsql/11/data/pg_hba.conf` and configure follow the intructions. If you don't understand anything, only change METHOD (local, ipv4, ipv6 connection) to md5. Keep in mind the ADDRESS connection
3. Open `/var/lib/pgsql/11/data/postgresql.conf`, uncomment line `listen_addresses = 'localhost'` and `port = 5432`
4. Restart service: `sudo systemctl restart postgresql-11`
5. Test connection `psql -h 127.0.0.1 -d database_name -U user` and enter password for `user`
### Allow remotely connection to PostgreSQL
1. Firstly, open port if closed by firewall
2. Change `listen_addresses = '*'` in `/var/lib/pgsql/11/data/postgresql.conf`. Add this config if not exists (should be at the end of file).
3. Change in `/var/lib/pgsql/11/data/pg_hba.conf`: `host all all [ip/32 or 0.0.0.0/0 to any ip] md5`
4. Restart service: `sudo systemctl restart postgresql-11`
### Basic PostgreSQL query
1. Create a user `CREATE USER larry WITH ENCRYPTED PASSWORD 'x' SUPERUSER CREATEROLE CREATEDB REPLICATION BYPASSRLS;`
