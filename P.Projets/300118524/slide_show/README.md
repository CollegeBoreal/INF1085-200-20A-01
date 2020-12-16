# Ce projet consiste de faire défiler sur un écran des informations 

## Les prérequis 

- Un Raspberry (dans mon cas une Raspberry pi 4)

- Un écran compatible CEC (Consumer Electronics Control) sur lequel afficher (si on veut automatiser la mise sous et hors tension)

- Un câble HDMI compatible CEC (Consumer Electronics Control) (si on veut automatiser la mise sous et hors tension)

- Un réseau internet privé

## Objectif

- Diapositive statique en jpeg ou PNG

- L’administrateur est chargé de concevoir ces diapositives.

- L’administrateur colle ces diapositives conçues dans le dossier spécifique (à suivre). Il peut également les modifier

## AJOUT DE LOGICIELS 

- Faire une mise à jour du système 

**`Sudo apt-get update`**

**`Sudo apt upgrade`**

- INSTALLER SAMBA

SAMBA permet le partage de dossiers avec la ou les machines Windows sur le réseau.

**`sudo apt install samba samba-common-bin smbclient cifs-utils`**

- INSTALLER fbi

> fbi est un utilitaire unix qui affiche des graphiques sur l’écran. La particularité est qu’il n'exécute pas de gestionnaire de fenêtres.

**`sudo apt install fbi`**

- INSTALLER inotify-tools

> inotify-tools permet au diaporama de regarder le dossier partagé pour tout changement.

**`sudo apt install inotify-tools`**

- INSTALLER cec-utils

> cec-utils permet au Raspberry Pi d'allumer et d'éteindre le téléviseur via le câble HDMI.

**`sudo apt installer cec-utils`**

- TÉLÉCHARGER les petits utilitaires que Dean Grannes a écrits pour lire le diaporama

**`git clone https://github.com/dgrannes/raspi_slideshow.git`**

## CONFIGURATION DU DOSSIER PARTAGÉ *SAMBA* 

> Par défaut, le code du diaporama recherche le répertoire / shared / Presentation. Nous devons créer ce répertoire.

**`sudo mkdir -p /shared/Presentation`**

Puis, nous devons modifier les autorisations de ce répertoire pour que n'importe qui sur ce raspberry puisse lire, écrire et exécuter.

**`sudo chmod a+rwx /shared/Presentation`**






