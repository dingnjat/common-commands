###If you use Apache2, it defaultly uses port 80. Then if you need http port 80 point to your web app port like 8080
1. Add or edit ```/etc/apache2/sites-available/000-default.conf```
```
<VirtualHost *:80>
        ServerName thuvienaz.vn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        ProxyPreserveHost On
        ProxyPass / http://127.0.0.1:8080/
</VirtualHost>
```
2. Restart Apache2
```
sudo systemctl restart apache2
```
