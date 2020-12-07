

### SAMBA

### DEFINTION

Samba est un logiciel d'interopérabilité qui implémente le protocole propriétaire SMB/CIFS de Microsoft Windows dans les ordinateurs tournant sous le système d'exploitation Unix et ses dérivés de manière à partager des imprimantes et des fichiers dans un réseau informatique8. Samba facilite l'interopérabilité entre systèmes hétérogènes Windows-Unix. Il offre la possibilité aux ordinateurs d'un réseau d'accéder aux imprimantes et aux fichiers des ordinateurs sous Unix9 et permettent aux serveurs Unix de se substituer à des serveurs Windows 10.



### Comment installer Samba

boreal@10.13.237.76 /home/Hassana $ sudo apt update
boreal@10.13.237.76 /home/Hassana $ sudo apt-get install samba


### Installation Verifier

boreal@10.13.237.76 /home/Hassana $ whereis samba

samba: /usr/sbin/samba /usr/lib/x86_64-linux-gnu/samba /etc/samba /usr/share/samba /usr/share/man/man7/samba.7.gz /usr/share/man/man8/samba.8.gz

sama est installer, 

### Suite a la creation d'un repertoire à partager

boreal@10.13.237.76 /home/Hassana $ mkdir /home/hassana/sharefolder/

### Fichier de configuration et Sauvegarde

boreal@10.13.237.76 /home/Hassana $ sudo cp /etc/samba/smb.conf /etc/smb.conf.org

boreal@10.13.237.76 /home/Hassana $ sudo nano /etc/samba/smb.conf

### AJOUT

[sharefolder]
          comment = samba on ubuntu
          path = /home/luxury/sharefolder
          browseable = yes
          readonly = no
 ###  Enregistrement et redemarrage de Samba
 
 boreal@10.13.237.76 /home/Hassana $ sudo service smbd restart 
 
 ### Configuration du password: Compte d'utilisateur

boreal@10.13.237.76 /home/Hassana $ sudo smbpasswd -a hassana
New SMB password:

### Mise a jour du pare-feu pour samba

boreal@10.13.237.76 /home/Hassana $ sudo ufw allow samba
Rules updated
Rules updated (v6)

###Apres installation de samba, Verifions l'adresse de la machine

root@boreal:~# ip add

### Adresse de la machine

10.13.237.76

### Verifions le sharehome a partir de windows








   
