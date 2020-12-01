
# SAMBA: Sharing files with windows users using samba  


## 1.	Definition:Samba est un logiciel d’interopérabilité qui implémente le protocole propriétaire SMB/CIFS de Microsoft Windows dans les ordinateurs 


# 2.NOTRE BUT:



# 1.	Créez un compte utilisatateur samba sur le serveur linux
   
# 1ÉRE Étape:Installez le serveur samba avec la commande followng
    
  
  


     
   ## sudo apt -get update
      sudo apt-get install samba -y
   
   
   
      2 éme Étape : une fois l'installation terminée, vous pouvez vérifier la version de samba avec la commande followng
        
        smbd --version
 
  ## (administrateuu@ubuntu:$ smbd --version
     version 4.11.6-ubuntu
     administrateur@ubuntu2004: $
 
# Étape 3: Ensuite, nous devons d'abord configurer samba pour activer le partage sur le réseau, créer une sauvegarde du fichier de configuration d'origine
 
## (administrateur@ubuntu2004:-$ sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.orignl
 (administrateur@ubuntu2004:-$ ls /etc/samba/
 gdbcommands smb.conf.orignl tls
 administrateur@ubuntu2004:-$
 


# Étape 4: ouvrir smb remplace son contenu par le suivant

## (global)
groupe de travail = groupe de travail
chaîne de serveur = serveur samba
nom netbios = ubuntu
security = utilisateur
map to guest = mauvais utilisateur
proxy DNS = non
(Publique)
chemin = / var / samba / partages / public
navigable = oui
inscriptible = oui
invité ok = oui
lecture seule = non
créer un masque = 644

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








  








 
