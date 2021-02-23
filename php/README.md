# How to Install PHP

## Prepare
```make
sudo apt-get update
```

## Installation
```make
sudo apt-get install php
```

## Web Server Installation
```make
sudo apt install -y apache2 apache2-utils
```

## Check Server
```make
systemctl status apache2
```

## Start Server
```make
sudo systemctl start apache2
```

## Check Server Version
```make
apache2 -v
```

## Firewall Policy Allow
```make
sudo iptables -I INPUT -p tcp --dport 80 -j ACCEPT
sudo ufw allow http
```

## Permission Setting
```make
sudo chown www-data:www-data /var/www/html/ -R
```

## Set Global ServerName in Apache
```make
sudo vi /etc/apache2/conf-available/servername.conf

ServerName localhost
```

## Apply Config File
```make
sudo a2enconf servername.conf
```

## Restart Server
```make
sudo systemctl reload apache2
```

# How to Run PHP-FPM with Apache

## Disable the Apache PHP7.4 module.
```make
sudo a2dismod php7.4
```

## Install PHP-FPM.
```make
sudo apt install php7.4-fpm
```

## Enable proxy_fcgi and setenvif module.
```make
sudo a2enmod proxy_fcgi setenvif
```

## Enable /etc/apache2/conf-available/php7.4-fpm.conf
```make
sudo a2enconf php7.4-fpm
```

## Restart Apache for the changes to take effect.
```make
sudo systemctl restart apache2
```
