# Projet
## ÉTAPE :one: : PRÉ-REQUIS


### :a: ACTIVER L'INTERFACE DE LA CAMÉRA


`% sudo raspi-config`


![image](activer_camera.png)


### :b: :point_down: choississez "Interface Options    Configure connections to peripherals"  :point_down:


![image](interface_camera.png)


### :c: choississez "yes"


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
``

`![image](interface_camera)`
## ÉTAPE 3 : INSTALLATION  DES APPLICATIONS NÉCESSAIRES


- on utilisera **motion** pour notre projet


`sudo apt-get install motion`


## ÉTAPE 4 : CONFIGURATION DES APPLICATIONS INSTALLÉES


`sudo nano /etc/motion/motion.conf`


##### voici les configurations à modifier :point down:


- daemon   on


> pouvoir lancer motion en tant que daemon, et pouvoir ainsi libérer un terminal


- framerate   10

> Ce chiffre montre le nombre d’images enregistrées par seconde. Chiffre élevé = RAM consommée.


- stream_port   8081

> Le port par defaut du mini serveur web.

- stream_quality   100

> Pourcentage de qualité des images streamées.


> stream_localhost   off


> stream_motion   off


- stream_maxrate (de 10 à 30)

> Ce chiffre montre le nombre d’images streamées par seconde. Chiffre élevé = RAM consommée


- webcontrol_localhost   off

> Si le paramètres est passé à « on », on autorise l’accès uniquement local au serveur de stream


- quality   100

> Pourcentage de qualité des images enregistrées


- width   640

> Indique la largeur des images enregistrées et streamées


- height   480

> Indique la hauteur des images enregistrées et streamées


- post_capture   5 (au choix)

> nombre de photos après l'enregistrement de la vidéo 

- pre_capture   2 (au choix)

nombre de photo avant l'enregistrement de la vidéo

- target_dir /var/lib/motion/

> Indique le chemin d’enregistrement des images et des vidéos. vous pouvez modifiez le chemin. exemple installer samba puis créer un dossier où le pi va stocker les enregistrements

- ffmpeg_output_movies  ON

> pour permettre au pi d'enregistrer




## ÉTAPE :five: : ACTIVÉ MOTION AU BOOT

`sudo nano /etc/default/motion`


- remplacer no par yes 


```diff
- no :x: par yes :white_check_mark: 
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
