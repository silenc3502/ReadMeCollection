## <?php 없이 <? 로 인식시키기
```make
sudo vi /etc/php/7.4/apache2/php.ini

short_open_tag = Off를 On으로 변경한다.

주의사항: 동작하지 못하는 DB 코드가 묶여있을 경우 이를 잘못 활용하면 다 같이 터져서 페이지가 안나오게 된다.
```

## Apache 웹 서버가 참조할 디렉토리 설정
```make
sudo vi /etc/apache2/apache2.conf

<Directory /home/oem/proj/dahada-php-legacy/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

## php의 index.php 위치시킬 장소
```make
sudo vi /etc/apache2/sites-enabled/000-default.conf

<VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port that
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin webmaster@localhost
        DocumentRoot /home/oem/proj/dahada-php-legacy/www/
        #DocumentRoot /var/www/html
```
