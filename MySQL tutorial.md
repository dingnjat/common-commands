## Installing
### Debian, Ubuntu,...
1. Download lastest repositories

`wget –c https://dev.mysql.com/get/mysql-apt-config_0.8.11-1_all.deb`

2. Install repositories

`sudo dpkg –i mysql-apt-config_0.8.10-1_all.deb`

3. Update

`sudo apt-get update`

4. Install MySQL server

`sudo apt-get install mysql-server`

### Fedora, CentOs,...

`wget https://dev.mysql.com/get/mysql80-community-release-el7-3.noarch.rpm`
`wget https://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm`

`sudo rpm –ivh mysql80-community-release-el7-3.noarch.rpm`

`sudo yum install mysql-server`

***After installing, you must start MySQL service***

## Terminal Commands
0. Find temporary password

`sudo grep ‘temporary password’ /var/log/mysqld.log`

1. Login

`(sudo) mysql -u username -p`

2. Start MySQL service

`sudo systemctl start mysqld`

3. Check status service

`sudo systemctl status mysqld`

4. Disable startup

`sudo systemctl disable mysqld`

5. Stop service

`sudo systemctl stop mysqld`

6. Configure MySQL security

`sudo mysql_secure_installation`

7. Exit mysql

`exit`

8. Check MySQL version

`mysql --version`

## SQL
* change password policies

`SHOW VARIABLES LIKE 'validate_password%';`

`SET GLOBAL validate_password_length = 6;`

* create user

```
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
```
* Remote Mysql Server

`GRANT [ALL, SELECT, INSERT, DELETE,...] ON [database name].[table name] TO '[username in remote mysql]'@'[ip address]' IDENTIFIED BY '[MySQL password]';`

_[database name], [table name] can set wildcard *_
_ip address can set localhost, 127.0.0.1 or wildcard %_

* show databases, show tables

`SHOW DATABASES;`

`SHOW TABLES;`

* Import from file

```
SET autocommit=0;
source [file-path];
COMMIT;
SET autocommit=1;
```

