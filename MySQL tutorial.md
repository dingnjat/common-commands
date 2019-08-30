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

5. (Optional) Configure MySQL security

`sudo mysql_secure_installation`

### Fedora, CentOs,...

## Terminal Commands

`(sudo) mysql -u username -p`

## SQL
* change password policies

`SHOW VARIABLES LIKE 'validate_password%';`

`SET GLOBAL validate_password_length = 6;`

* create user

```
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'username'@'localhost' IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
```

* show databases, show tables

`SHOW DATABASES;`

`SHOW TABLES;`

