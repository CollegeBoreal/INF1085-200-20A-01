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

**`sudo chmod a+rwx /shared/Presentation`** :exclamation: **a** représente **all(owner, group, others)**

> partage le répertoire */ shared* comme un répertoire qui est *lisible* et *inscriptible* par n'importe qui sur le réseau local

- ajoute des lignes de configuration dans le fichier smb.conf

**`cat raspi_slideshow/add_to_smb.conf >> /etc/samba/smb.conf`**

> concatène le fichier add_to_smb.conf(dans le repertoire cloné) à la fin de /etc/samba/smb.conf

##  Modifier le mot de passe et configurer l'exécution automatique

- Cliquez sur le menu du raspberry en haut à gauche, sélectionnez Préférences/  Raspberry Pi Configuration

- "Change Password " si vous le souhaitez :bomb::bomb::bomb: 

- choississez Boot "To CLI" :fire::fire::fire:

> Le Raspberry Pi ne démarrera pas un gestionnaire de fenêtres, mais s'exécutera simplement sur l'écran

- Définir la connexion automatique Auto Login à "Login as user 'pi'"

> Le Raspberry Pi se connectera automatiquement en tant qu'utilisateur pi

- configurer le diaporama pour qu'il s'exécute lors du démarrage

**`nano .bashrc`**

- à la fin du fichier et rajoutez la ligne suivante :point_down::point_down:

**`python3 raspi_slideshow / play_slideshow.py`**

> Le Raspberry Pi démarrera le shell bash, qui lit le fichier .bashrc, et la dernière ligne de ce fichier dit d'exécuter le diaporama.

:anger:Vous pouvez accéder au terminal bash avec Ctrl-C pendant le diaporama:anger:

vous pouvez démarrer le gestionnaire de fenêtres à partir du terminal bash avec :point_right: **`startx`**

## Configuration de la machine Windows

- Ouvrez votre explorateur de fichier Windows

  - ÉTAPE 1 : Cliquez sur "Ce PC"
  
  - ÉTAPE 2 : Cliquez sur "Connecter un lecteur réseau"
  
  - ÉTAPE 3 : Dans le champ Dossier, saisir: **`\\ {nom_du_Raspberry_Pi} \ shared`**
  
  - ÉTAPE 4 : Choisir à quelle lettre on veut connecter le lecteur, *par exemple "Z:"* 
  
  - ÉTAPE 5 : Cocher se "Se reconnecter lors de la connexion"
  
  Si vous voulez protéger votre dossier par mot de passe, vous devez cochez "Se connecter à l'aide d'informations d'identification différentes" et en entrant le   nom d'utilisateur et mot de passe du Raspberry Pi.
  
:clap::clap::clap: Le Pi affiche UNIQUEMENT le contenu du dossier Présentation, et rien au niveau supérieur (\ shared)

- 120 secondes est le temps configuré pour que le raspberry pour réinitialiser les diapositives(diapositives ajoutées, supprimées ou modifiées)

  > Cela donne à la personne le temps de faire toutes les modifications nécessaires sans réinitialiser après chaque diapositive ajouté

## CRÉER DES IMAGES jpeg OU png AVEC Powerpoint ET LES FAIRE AFFICHER

- ouvrez powerpoint puis créer vos diapositives 

- cliquez sur **Fichier** puis sur  **Exporter**

- enregistrez le diapositive au format PNG ou JPEG.

> Cela produira les diapositives sous forme de fichiers individuels sous formes diapositive1 --diapositive2 ainsi de suite

- glisser et déposer des fichiers individuels dans la lettre de lecteur que vous avez utilisée /Presentation

- la présentation est organisée par ordre alphabétique donc renommez les diapositives selon l'ordre que vous voulez

# Références

[slideshow](https://www.instructables.com/Raspberry-Pi-Bulletin-Board/)
