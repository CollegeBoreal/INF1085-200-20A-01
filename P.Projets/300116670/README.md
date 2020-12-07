# INSTALLER UNE CAMERA DE SURVEILLANCE AVEC MOTION SUR RASPBERRY PI 4 :camera:

Bienvenu

## :pushpin: SOMMAIRE

I/ Matériel et Prerequis nécessaire

II/ Installer MOTION

III/Monter et activer la camera sur le pi 

IV/

VI/ Enregistrer les vidéos dans un répertoire partagé de Windows

VII/ Démarrer motion automatiquement

 Accéder au flux vidéo 



## INSTALLER MOTION

Un très bon logiciel de détection de mouvement et/ou de surveillance avec de nombreuses options de configuration est motion. Il est open-source et gratuit ce qui rajoute encore à ses qualités.

Pour l’installer il faut utiliser la ligne de commande (en se connectant au Raspberry Pi en tant qu’utilisateur “pi“):

sudo apt-get install motion

Un certain nombre de paquets vont être installés pendant la phase d’installation. Répondez simplement “y” pour autoriser l’installation.

## Accéder au flux vidéo 

Maintenant, vous pouvez accéder à la diffusion en direct de la caméra depuis n’importe quel navigateur via l’url http://adresse_IP_du_raspberry:8080

Où 8080 est le port qui est configuré dans le fichier motion.conf. Vous pouvez faire votre propre réglage pour le port en modifiant le paramètre “stream_port” dans motion.conf.



