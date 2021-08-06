## PostgreSQL installation for beginner on linux (fedora)
1. Go to Dowload PostgreSQL site, choose correctly version to your OS, follow the steps on this page.
![Choose version](/image/choose.png)
2. After installing and starting the PostgreSQL services, open terminal, run: `sudo su - postgres`, enter sudo password.
3. If you has not added PATH yet, run `export PATH="path_to_bin:$PATH"`. E.g `export PATH="/usr/pgsql-11/bin:$PATH"`. Then run it.
4. Run `psql` to run psql interface. Now, we can use sql queries with postgresql
### Create user
1. `CREATE USER username WITH ENCRYPTED PASSWORD 'passoword';`
2. `ALTER USER username WITH ROLE1 ROLE2....;`
### Connect to PostgreSQL
1. go to pg_hba.conf in /var/lib/pgsql/11/data/ (maybe need superuser permission)
2. open it and configure it follow the intructions. If you dont understand, only change METHOD (local, ipv4, ipv6 connection) to md5. Keep in mind the ADDRESS connection
3. open postgresql.conf in the same direction, uncomment line `listen_addresses = 'localhost'` and `port = 5432`
4. Restart the postgresql service: run `sudo systemctl restart postgresql-11` in terminal
5. Test connect `psql -h 127.0.0.1 -d database_name -U user` and enter password for `user`. (You need create a database)
