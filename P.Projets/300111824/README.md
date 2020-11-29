
# SAMBA: Sharing files with windows users using samba  


## 1.	Definition:Samba est un logiciel d’interopérabilité qui implémente le protocole propriétaire SMB/CIFS de Microsoft Windows dans les ordinateurs 


# 2.NOTRE but:



## 1.	Créez un compte utilisatateur samba sur le serveur linux
   2.	Désigner un répertoire de partage.
   3.	Définissez le partage via le fichier d’édition smb.conf
   4.	Testez la configuration.
   5.	Connectez -vous a partir d’un client windows.
   
   
   
# 3.1 Créez un compte utilisateur samba sur le serveur linux

3.1.2 Installer samba 


 ## $ sudo  apt install  samba
    $ sudo apt-get update
    
    Ensuite vous devrez utilizer  un programme appelé smbpasswd pour configurer un utilisateur samba en tant que compte que les clients utilise
   - adduser sambauser
   - smbpassword-a sambauser
   
   
   # 4. Designer un repertoire de partage
   
   ## Créer  un repertoire ou sera bassé le partage . pour faciliter les tests ultérieurs, il faut donc  créer un nouveau répertoire .Etant donné.
 mkdir -p /samba/ sharehome
 touch / samba / sharehome/ myfile
 
 
 
 ## Vous pouvez évitez les problémes d’autorisations potentiels en utilisant chmod pour ouvrir les autorisations de répertoire au 777.
Chmod 777 /samba/ sharehome


## C’est l’environnement samba tout construit . vous pouvez maintenant ajouter une configuration au fichier  smb.conf dans le répertoire / nano /etc/ smb.conf


# 5.Définir le partage via le fichier d’édition smb.conf


## En etant dans nano taper les commandes suivants sans les commentaires (#) :



(sharehome)
Path =/ samba/sharehome
Writable*yes


Puis enregistrer la modifaction et ensuite sortez.


Utilisez maintenant systemctl pour démarrer et activer le démon samba. Ubuntu connait samba comme smbd, mais sur centos,ce sera smb



Systemctl start smbd
Systemctl enable smbd


5.# 	TESTEZ LA CONFIGURATION

## Il est toujour mieux d’ assurer ces arrieres avant d’aller un plus loin ,du coup testparm sera notre moyen de verification 

testparm


Encore un test avant d’inviter vos amis windows : vous pouvez utiliser le programme smbclient pour vous connecter a votre partage samba
depuis la machina locale. Vous devez d’abord basculer l’utilisateur (su) vers le compte sambauser que vous avez associé a samba plus tot.vous  pouvez ensuite exécuter smbclient sur l’adresse et le nom d’hote du partage (//loclhost/sharehome va falloir d’abord créer samba client et ensuite proceder aux étapes suivantes :


First il basculer (su) vers le compte sambauser que vous avez associe a samba


$ su sambauser 
Password:


Ensuite il faut créer samba client 


-sudo apt- get install smbclient.


Smbclient //localhost/sharehome
Enter sambauser ,s password:


# Resultats


##  Smbclient //localhost/sharehome 
Enter sambauser’s password:
Domain=(WORKGROUP) os= (windows 6.1)  serveur=(samba 4.3.11-ubuntu)
Smb: 



# 6. Connectez -vous a partir d’un client windows 



## -clique droite sur le logo de windows ensuite appuye sur run.
Tape :// 10.13.237.66/ sharehome








  








 
