# INSTALLER UNE CAMERA DE SURVEILLANCE AVEC MOTION SUR RASPBERRY PI 4 :camera:

C’est un projet de Christoph BUENGER. L’objectif de ce projet est la réalisation d’une caméra de vidéosurveillance à l'aide d'un Raspberry Pi (Picam) et le flux vidéo est diffusé sur un PC ou sur un smartphone.
Le prix doit rester raisonnable d’où l’utilisation d'un Pi.
 

## :pushpin: SOMMAIRE

I/Matériel et Prerequis nécessaire

II/Installer MOTION

III/Monter et activer la camera sur le pi 

IV/

VI/ Enregistrer les vidéos dans un répertoire partagé de Windows

VII/ Démarrer motion automatiquement

 Accéder au flux vidéo 


## Materiel et prerequis

Au prealale, vous devrez vous equipez des elements suivants:

_ :thumb: Un Raspberry Pi 4 sous Raspbian(systeme d'exploitation le plus avance pour le Raspbery Pi)
_Un module de Caméra Raspberry Pi
_Un adaptateur HDMI
_Un cable d'alimentation pour votre pi
_Une carte SD
_ Un clavier et un moniteur

## INSTALLER MOTION

Un très bon logiciel de détection de mouvement et/ou de surveillance avec de nombreuses options de configuration est motion. Il est open-source et gratuit ce qui rajoute encore à ses qualités.

Pour l’installer il faut utiliser la ligne de commande (en se connectant au Raspberry Pi en tant qu’utilisateur “pi“):

sudo apt-get install motion

Un certain nombre de paquets vont être installés pendant la phase d’installation. Répondez simplement “y” pour autoriser l’installation.

## Accéder au flux vidéo 

Maintenant, vous pouvez accéder à la diffusion en direct de la caméra depuis n’importe quel navigateur via l’url http://adresse_IP_du_raspberry:8080

Où 8080 est le port qui est configuré dans le fichier motion.conf. Vous pouvez faire votre propre réglage pour le port en modifiant le paramètre “stream_port” dans motion.conf.



