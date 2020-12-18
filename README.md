# Installation-Lizmap



```bash
sudo apt update
```
```bash
sudo apt upgrade
```
Configuration des locales
```bash
sudo locale-gen fr_FR.UTF-8
```
replace fr with your language
```bash
sudo dpkg-reconfigure locales
```
define your timezone [useful for logs]
```bash
sudo dpkg-reconfigure tzdata
```
```bash
apt install ntp ntpdate
```
```bash
sudo apt install gnupg software-properties-common
```

```bash
wget -qO - https://qgis.org/downloads/qgis-2020.gpg.key | sudo gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/qgis-archive.gpg --import
```

```bash
sudo chmod a+r /etc/apt/trusted.gpg.d/qgis-archive.gpg
```

Version LTR debian

```bash
sudo sh -c 'echo "deb https://qgis.org/debian-ltr buster main" >> /etc/apt/sources.list'
```

Dernière version debian

```bash
sudo add-apt-repository "deb https://qgis.org/debian `lsb_release -c -s` main"
```

```bash
sudo apt update
```

```bash
apt install qgis-server python-qgis
```

```bash
sudo apt install apache2
```
```bash
#Debian 9

apt install php7.0-fpm php7.0-cli php7.0-bz2 php7.0-curl php7.0-gd php7.0-intl php7.0-json php7.0-mbstring php7.0-pgsql php7.0-sqlite3 php7.0-xml php7.0-ldap

#Debian 10

apt install php7.3-fpm php7.3-cli php7.3-bz2 php7.3-curl php7.3-gd php7.3-intl php7.3-json php7.3-mbstring php7.3-pgsql php7.3-sqlite3 php7.3-xml php7.3-ldap
```

sudo apt install libapache2-mod-fcgid

sudo a2enmod fcgid

sudo a2enconf serve-cgi-bin

sudo service apache2 restart

sudo nano /etc/apache2/sites-available/000-default.conf

    ScriptAlias /cgi-bin/ /usr/lib/cgi-bin/
    <Directory "/usr/lib/cgi-bin/">
    Options ExecCGI FollowSymLinks
    Require all granted
    AddHandler fcgid-script .fcgi
    </Directory>


sudo service apache2 restart

http://146.59.231.55/cgi-bin/qgis_mapserv.fcgi?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities --> OK


cd /var/www/

VERSION=3.3.12

cd /lizmap-web-client-3.3.12/var/config

sudo wget https://github.com/3liz/lizmap-web-clie … ERSION.zip

sudo unzip lizmap-web-client-$VERSION.zip

ln -s /var/www/lizmap-web-client-$VERSION/lizmap/www/ /var/www/html/lizmap

cd /var/www/lizmap-web-client-$VERSION/

lizmap/install/set_rights.sh www-data www-data

cd lizmap/var/config

sudo cp lizmapConfig.ini.php.dist lizmapConfig.ini.php

sudo cp localconfig.ini.php.dist localconfig.ini.php

sudo cp profiles.ini.php.dist profiles.ini.php

sudo apt install xauth htop curl libapache2-mod-php7.0 php7.0-cgi php7.0-gd php7.0-sqlite3 php7.0-xml php7.0-curl php7.0-xmlrpc php7.0-pgsql python-simplejson

cd var/www/lizmap-web-client-3.3.12

cd lizmap/var/config

sudo nano localconfig.ini.php

Ajouter --> lizmap.installparam=demo

[modules]
lizmap.installparam=demo

cd /var/www/lizmap-web-client-3.3.16

sudo php /lizmap/install/installer.php

sudo chown :www-data temp/ lizmap/var/ lizmap/www lizmap/install/qgis/edition/ -R

sudo chmod 775 temp/ lizmap/var/ lizmap/www lizmap/install/qgis/edition/ -R

sudo service apache2 restart





wget https://github.com/3liz/lizmap-web-client/releases/download/3.4.0-rc.2/lizmap-web-client-3.4.0-rc.2.zip

unzip lizmap-web-client-3.4.0-rc.2.zip

mv lizmap-web-client-3.4.0-rc.2 lizmap-web-client-3.4.0

cd /var/www/lizmap-web-client-3.4.0

sudo chown :www-data temp/ lizmap/var/ lizmap/www lizmap/install/qgis/ -R
sudo chmod 775 temp/ lizmap/var/ lizmap/www lizmap/install/qgis/ -R

ln -s /var/www/lizmap-web-client-3.4.0/lizmap/www/ /var/www/html/lizmap
