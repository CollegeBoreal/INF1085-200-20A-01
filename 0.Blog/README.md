
# Blog


Creer un blog (i.e. Wordpress) permettant de décrire l'installation de:

* Linux [Ubuntu 20.04LTS](https://releases.ubuntu.com/20.04/) plus précisément installer la version  Serveur en [64-bit](https://releases.ubuntu.com/20.04/ubuntu-20.04.1-live-server-amd64.iso)

## Creer un blog (i.e. wordpress.com)

Le `blog` permettra de décrire toute la recherche effectuée pour installer Linux sur les machines [HP Proliant G6 ou G7](https://github.com/CollegeBoreal/Laboratoires/tree/master/3202/proliant)

Astuces: 

* Utiliser un CD-Rom (si vous en avez un) ou une clé USB pour `booter` sur la machine

* Installer la machine dans le laboratoire:

       Choisir une adresse dans la plage de réseau: 10.13.237.0/28
       
## Liste des blogs

|:hash:| :id:      |   Blog (https://wordpress.com)                                                    | Serveur Local| [Serveur Ext.](README.md#references) |
|------|-----------|-----------------------------------------------------------------------------------|--------------|--------------|
| 01   | 300111441 |                                                                                   | 10.13.237.?  | 10.13.?.?  |
| 02   | 300111824 |                                                                                   | 10.13.237.?  | 10.13.?.?  |
| 03   | 300115065 | https://fadde99.wordpress.com/                                                    | 10.13.237.?  | 10.13.?.?  |
| 04   | 300115140 | https://blogzacklinux.wordpress.com                                               | 10.13.237.117|10.13.32.50 |
| 05   | 300116670 | https://auriane790987616.wordpress.com/blog                                       | 10.13.237.?  | 10.13.?.?  |
| 06   | 300116685 | https://Amirlinux.wordpress.com/blog                                              | 10.13.237.51  | 10.13.2.59 |
| 07   | 300116973 | https://nathalielinux.wordpress.com/2020/09/14/example-post/                      | 10.13.237.23 |10.13.2.24  |
| 08   | 300117178 | https://kblinuxca.wordpress.com/2020/09/16/comment-installer-linux-server-20-04   | 10.13.237.15 | 10.13.0.15 |
| 09   | 300117314 |  https://mortilinuxserver.wordpress.com/wp-admin/post.php?post=49&action=edit     | 10.13.237.100| 10.13.2.100|
| 10   | 300117444 |https://dido05327.wordpress.com/blog/                                              | 10.13.237.?  | 10.13.0.20 |
| 11   | 300117782 |http://erna161707791.wordpress.com                                                 | 10.13.237.85 | 10.13.2.77 |
| 12   | 300117784 | https://linuxinstallationca.wordpress.com/                                        | 10.13.237.77 | 10.13.2.70 | 
| 13   | 300117806 | https://marketing376655173.wordpress.com                                          | 10.13.237.76 | 10.13.2.99 |
| 14   | 300118524 |                                                                                   | 10.13.237.?  | 10.13.?.?  |


#### Example
| :id:      |   Blog (https://wordpress.com)                          |
|-----------|---------------------------------------------------------|
| 300098957 | https://setrar.wordpress.com/2015/01/10/bitstamp/       | 


## References

:one: Reseau Externe

http://jodies.de/ipcalc?host=10.13.0.0&mask1=20

       Address:   10.13.0.1             00001010.00001101.0000 0000.00000001
       Netmask:   255.255.240.0 = 20    11111111.11111111.1111 0000.00000000
       Wildcard:  0.0.15.255            00000000.00000000.0000 1111.11111111
       =>
       Network:   10.13.0.0/20          00001010.00001101.0000 0000.00000000 (Class A)
       Broadcast: 10.13.15.255          00001010.00001101.0000 1111.11111111
       HostMin:   10.13.0.1             00001010.00001101.0000 0000.00000001
       HostMax:   10.13.15.254          00001010.00001101.0000 1111.11111110
       Hosts/Net: 4094                  (Private Internet)

:one: Reseau Interne

http://jodies.de/ipcalc?host=10.13.237.0&mask1=25

       Address:   10.13.237.0           00001010.00001101.11101101.0 0000000
       Netmask:   255.255.255.128 = 25  11111111.11111111.11111111.1 0000000
       Wildcard:  0.0.0.127             00000000.00000000.00000000.0 1111111
       =>
       Network:   10.13.237.0/25        00001010.00001101.11101101.0 0000000 (Class A)
       Broadcast: 10.13.237.127         00001010.00001101.11101101.0 1111111
       HostMin:   10.13.237.1           00001010.00001101.11101101.0 0000001
       HostMax:   10.13.237.126         00001010.00001101.11101101.0 1111110
       Hosts/Net: 126                   (Private Internet)
