1. Make sure DNS configuration is setup![image](https://user-images.githubusercontent.com/14835764/147650609-f7694716-20e0-4873-9f45-239f6cac98b8.png)
2. Add to Apache2 default conf ```/etc/apache2/sites-available/000-default.conf``` <br/> Or create ```/etc/apache2/sites-available/subdomain.example.com.conf```
```
<VirtualHost *:80>
        ServerAdmin admin@example.com
        ServerName subdomain.example.com
        ServerAlias subdomain.example.com
        ProxyRequests Off

        #ProxyPass / http://localhost:8080/
        <Location />
                ProxyPreserveHost On
                ProxyPass http://example.com:8080/
                ProxyPassReverse http://example.com:8080/
        </Location>
     # Uncomment the line below if your site uses SSL.
     #SSLProxyEngine On
</VirtualHost>
```
3. Enable mod_proxy and restart apache2
```
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests
sudo a2ensite subdomain.example.com.conf (000-default.conf if you use default .conf)
sudo systemctl restart apache2
```
