# CE PROJET CONSISTE DE FAIRE DÉFILER SUR UN ÉCRAN DES INFORMATIONS  

## LES PRÉ-REQUIS 

- Un Raspberry (dans mon cas une Raspberry pi 4)

- Un écran compatible CEC (Consumer Electronics Control) sur lequel afficher (si on veut automatiser la mise sous et hors tension)

- Un câble HDMI compatible CEC (Consumer Electronics Control) (si on veut automatiser la mise sous et hors tension)

- Un réseau internet privé

## OBJECTIF

- Diapositive statique en jpeg ou PNG

- L’administrateur est chargé de concevoir ces diapositives.

- L’administrateur colle ces diapositives conçues dans le dossier spécifique (à suivre). Il peut également les modifier

## AJOUT DE LOGICIELS 

- obtenir une mise à jour du système 

**`% sudo apt-get update`**

- installer la mise àjour la raspberry (choississez une commande) :point_down:

**`sudo apt-get upgrade`** pour faire la MAJ sécurité (ou fondamentale)

**`sudo apt-get full-upgrade`** pour faire la MAJ totale

- vous pouvez rajouter `-y` à la fin de la commande choisi pour que le systéme fasse *yes* aux questions lors de la MAJ

- INSTALLER SAMBA :point_down:

> SAMBA permet le partage de dossiers avec la ou les machines Windows sur le réseau.

**`sudo apt install samba samba-common-bin smbclient cifs-utils`**

- INSTALLER fbi :point_down:

> fbi est un utilitaire unix qui affiche des graphiques sur l’écran. La particularité est qu’il n'exécute pas de gestionnaire de fenêtres.

**`sudo apt install fbi`**

- INSTALLER inotify-tools :point_down:

> inotify-tools permet au diaporama de regarder le dossier partagé pour tout changement.

**`sudo apt install inotify-tools`**

- INSTALLER cec-utils :point_down:

> cec-utils permet au Raspberry Pi d'allumer et d'éteindre le téléviseur via le câble HDMI.

**`sudo apt installer cec-utils`**

- TÉLÉCHARGER les petits utilitaires que Dean Grannes a écrits pour lire le diaporama

**`git clone https://github.com/dgrannes/raspi_slideshow.git`**

## CONFIGURATION DU DOSSIER PARTAGÉ *SAMBA* 

> Par défaut, le code du diaporama recherche le répertoire / shared / Presentation. Nous devons créer ce répertoire.

**`sudo mkdir -p /shared/Presentation`**

- Puis, nous devons modifier les autorisations de ce répertoire pour que n'importe qui sur ce raspberry puisse lire, écrire et exécuter.

**`sudo chmod a+rwx /shared/Presentation`**






