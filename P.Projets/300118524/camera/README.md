# Projet
## ÉTAPE :one: : PRÉ-REQUIS


### ACTIVER L'INTERFACE DE LA CAMÉRA


`% sudo raspi-config`


![image](activer_camera.png)


### :point_down: choississez "Interface Options    Configure connections to peripherals"  :point_down:


![image](interface_camera.png)


### choississez "yes"


![image](yes_camera.png)


voilà l'interface caméra est activé


## ÉTAPE :two: : CONFIGURATION DE LA RASPBERRY


- obtenir la mise àjour la raspberry


`% sudo apt-get update`


- installer la mise àjour la raspberry (choississez une commande)


`sudo apt-get upgrade` pour faire la MAJ sécurité (ou fondamentale)


`sudo apt-get full-upgrade` pour faire la MAJ totale


- vous pouvez rajouter `-y` à la fin de la commande choisi pour que le systéme fasse *yes* aux questions lors de la MAJ


## ÉTAPE :three: : VÉRIFIER SI L'INTERFACE CAMÉRA ET LA CAMÉRA PHYSIQUE


`raspistill -o test.jpg`


- cette commande affiche l'image en temps réel de la caméra


## ÉTAPE :four: : INSTALLATION  DES APPLICATIONS NÉCESSAIRES


- on utilisera **motion** pour notre projet


`sudo apt-get install motion`


## ÉTAPE :five: : CONFIGURATION DES APPLICATIONS INSTALLÉES


`sudo nano /etc/motion/motion.conf`


##### voici les configurations à modifier 

:point_down: :point_down: :point_down:


- **daemon   on**


pouvoir lancer motion en tant que daemon, et pouvoir ainsi libérer un terminal


- **stream_port   8081**

:exclamation: Le port par defaut du mini serveur web.


- **stream_maxrate (de 10 à 30)**

Ce chiffre montre le nombre d’images streamées par seconde. Chiffre élevé = RAM consommée

- **webcontrol_localhost   off**

Si le paramètres est passé à « on », on autorise l’accès uniquement local au serveur de stream

- **post_capture   5 (au choix)**

nombre de photos après l'enregistrement de la vidéo 

- **pre_capture   2 (au choix)**

nombre de photo avant l'enregistrement de la vidéo

- **target_dir /var/lib/motion/**

:exclamation: Indique le chemin d’enregistrement des images et des vidéos. vous pouvez modifiez le chemin. exemple installer samba puis créer un dossier où le pi va stocker les enregistrements

- **ffmpeg_output_movies  ON**

pour permettre au pi d'enregistrer

- **quality   100**

Pourcentage de qualité des images enregistrées


- **width   640**

Indique la largeur des images enregistrées et streamées


- **height   480**

Indique la hauteur des images enregistrées et streamées

- **stream_quality   100**

Pourcentage de qualité des images streamées.

- **framerate   10**

Ce chiffre montre le nombre d’images enregistrées par seconde. Chiffre élevé = RAM consommée.

- **stream_localhost   off**


- **stream_motion   off**


## ÉTAPE :five: : ACTIVÉ MOTION AU BOOT

`sudo nano /etc/default/motion`


- remplacer no :x: par yes :white_check_mark:


```diff
- no  par yes  
```

## ÉTAPE :six: : REDÉMARRER MOTION

`systemctl restart motion.service`

## ÉTAPE :seven: : RÉCUPÉRER L'ADRESSE IP DU PI

`ip address`

## ÉTAPE :eight: : VISIONNER LA VIDÉO

- aller dans votre navigateur et tapez:

`l'adresse ip du PI:stream_port`

- exemple **192.168.10.32:8081**

## VOILÀ
