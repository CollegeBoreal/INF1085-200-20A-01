# WikiMedia

:bookmark: 1.Installer le serveur LAMP
---------------------------------------
```
$ sudo apt-get install apache2 serveur-mariadb php php-mysql libapache2-mod-php php-xml php-mbstring
```
Pour telecharger wikimedia 
```
$wget https://releases.wikimedia.org/mediawiki/1.35/mediawiki-1.35.0.tar.gz
```
Pour creer un repertoire de wikimedia 
```
$ sudo mkdir /var/lib/mediawiki
```
Deplacer vers le dossier 
```
sudo mv mediawiki - */ */var/lib/mediawiki
```
2.Configuration mysql
----------------------
```
$sudo mysqld_safe --skip-grant-tables --skip-networking
```
Creer un conteneur

```
$docker container run --name my_wiki --env MYSQL_ROOT_PASSWORD=password --publish 33044:3306 --detach mysql:latest
```
Lancer CLI (command level Interface )
```
#mysql --user root --password 
```
Creer un utilisateur en MYSQL
```
CREATE USER'amirali'@'localhost' IDENTIFIED BY 'brice ';
GRANT ALL ON amir.* TO'amirali'@'localhost' ;
```
Creer une base de donnees 
```
CREATE DATABASE my_wiki ;
```
3.Configurateur Mediawiki
-------------------------
```
$sudo ln -s /var/lib/mediawiki/var/www/ html/mediawiki
```

# References

lien du blog
#pour installer mariadb-server
https://computingforgeeks.com/how-to-install-mariadb-on-ubuntu-focal-fossa/
#pour installer Wikimedia 
https://www.mediawiki.org/wiki/Manual:Running_MediaWiki_on_Debian_or_Ubuntu/fr
