# INSTALLER UNE CAMERA DE SURVEILLANCE AVEC MOTION SUR RASPBERRY PI 4 :policeman:

C’est un projet de Christoph BUENGER. L’objectif de ce projet est la réalisation d’une caméra de vidéosurveillance à l'aide d'un Raspberry Pi (Picam) et le flux vidéo est diffusé sur un PC ou sur un smartphone.
Le prix doit rester raisonnable d’où l’utilisation d'un Pi.

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMfqzJsfxzjgg5b1eI1yaEppEiftr2Ts3Cow&usqp=CAU" width="250"> <img src="data:image/jpeg;base64,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" width="250"> 


 ## :pushpin: SOMMAIRE

I/Matériel et Prerequis nécessaire

II/Installer MOTION 

III/Monter et activer la camera sur le pi 

IV/Accéder au flux vidéo 

V/ Quelques plus


## Materiel et prerequis

Au prealale, vous devrez vous equipez des elements suivants:

:heavy_check_mark: Un Raspberry Pi 4 sous Raspbian(systeme d'exploitation le plus avance pour le Raspbery Pi  mais vous pouvez utiliser le systeme d'exploitation de votre choix )

:heavy_check_mark:Un module de Caméra Raspberry Pi

:heavy_check_mark:Un adaptateur HDMI

:heavy_check_mark:Un cable d'alimentation pour votre pi

:heavy_check_mark:Une carte SD

:heavy_check_mark: Un clavier et un moniteur

|RASPBERRY | CAMERA | Cable d'alimentation, HDMI converter, Souris, Clavier
|----------|--------|------------------------------------------------------
|<img src="IMG_0406.jpg" width="250">| <img src="IMG_0407.jpg" width="250">         |  <img src="IMG_0408.jpg" width="250"> 



## INSTALLER MOTION

Un très bon logiciel de détection de mouvement et/ou de surveillance avec de nombreuses options de configuration est motion. Il est open-source et gratuit ce qui rajoute encore à ses qualités.

Acceder à votre terminal (image)

  **Tout d'abord, effectuer les mises a jour**

       $sudo apt update

       $sudo apt full-upgrade

Pour installer MOTION il faut utiliser la ligne de commande (en se connectant au Raspberry Pi en tant qu’utilisateur “pi“):

       $sudo apt-get install motion

Un certain nombre de paquets vont être installés pendant la phase d’installation. Répondez simplement “y” pour autoriser l’installation.
 
  <img src="IMG_0422.jpg" width="250"> 

Modifiez également le démon de motion pour que motion fonctionne en permanence :

        $sudo nano /etc/default/motion
        
 <img src="InkedIMG_0427_LI.jpg" width="250"> 
 <img src="IMG_0426.jpg" width="250"> 

Modifiez cette ligne comme suit :

        *start_motion_daemon=yes

**Les principaux changements sont les suivants** :

S’assurer que motion est toujours en cours d’exécution en tant que démon en arrière-plan :

        daemon on

Le fichier journal va être enregistré dans le répertoire /tmp sinon l’utilisateur autostart ne pourra pas accéder au répertoire /home/pi :

        logfile /tmp/motion.log

Pour avoir une vidéosurveillance de bonne qualité la définition est fixée à 1280 x 720 pixels :

         width 1280
         height 720
         

La vidéosurveillance peut se contenter de 2 images par seconde. Le flux vidéo continu est inutile :

        framerate 2
        

Nous ne voulons pas de films sans fin. Au lieu de cela, nous voulons avoir au plus des séquences vidéo de 10 minutes maximum. Cette option de configuration qui s’appelait max_movie_time a été renommée  max_mpeg_time dans motion. Si vous utilisez la version motion-mmal, cela fonctionne. Si vous obtenez une erreur Unknown config option  “max_mpeg_time” modifiez l’option en max_movie_time ou assurez-vous d’utiliser vraiment la version motion-mmal comme indiqué ci-dessus.

        max_mpeg_time 600
        

Certains lecteurs multimédia comme VLC sont incapables de lire les films enregistrés. En utilisant le codec msmpeg4 les films sont lus par tous les lecteurs.

       ffmpeg_video_codec msmpeg4
       

Pour pouvoir lire le flux vidéo en direct de n’importe où il faut l’autoriser. Sinon, seul localhost (le Raspberry Pi lui-même) serait autorisé à accéder à la diffusion en direct :

        stream_localhost off
        

Si vous voulez protéger le flux vidéo le flux avec un login et un mot de passe, ajoutez l’option suivante :

        stream_auth_method 2
        stream_authentication LOGIN:MOT_DE_PASSE

Après avoir réalisé vos modifications de paramètres dans motion.conf, redémarrez le Raspberry Pi pour qu’ils soient pris en compte :

         sudo reboot

Après le redémarrage, la LED rouge de la caméra devrait être allumée, indiquant que motion utilise la caméra pour détecter tout mouvement.

**MONTER ET ACTIVER LA CAMERA SUR LE PI**

Sur le Pi , vous verrez "camera" ecrit devant un port, c'est la que vous mettrez votre caméra

 <img src="IMG_0418.jpg" width="250">   <img src="IMG_0417.jpg" width="250">  <img src="IMG_0411.jpg" width="250">
 
 
 **Maintenant on va enable notre camera**

 A l'aide de la commande suivante 
 
    sudo raspi-config

Interfacing options>Pi Camera> Enable , utiliser Tabulation pour defiler dans les menus.

  <img src="https://cdn.shopify.com/s/files/1/0176/3274/files/raspi-config-1.jpg?v=1588172694" width="250">  
  
  <img src="https://cdn.shopify.com/s/files/1/0176/3274/files/raspi-config-2.jpg?v=1588172756" width="250">
 
 
 
 Apres avoir intaller vootre camera , verifier si elle fonctionne en utilisant la commande suivante:
(Vous pouvez mettre ce que vous voulez à la place de test)

        $raspistill -v -o test.jpg
        
 Normalement le pop-up suivant devrait s'ouvrir 
 
 <img src="IMG_0420.jpg" width="250">
 
Sinon entrez la commande suivante pour verifier que le Pi detecte et supporte bien la camera:

       $vcgencmd get camera

Si l'un des résultats affiche 0 veuillez vérifier si vous avez bien connecter/brancher votre caméra sinon prenez en une autre.


        
        
## Accéder au flux vidéo

**Trouver l'adresse IP**

Afin d'acceder au flux video il vous faut vore addresse ip. Tapez la commande suivante dans votre terminal

      $ip address
      
 <img src="IMG_0427.jpg" width="250"> 
 
 
 Notre adresse IP est **172.20.10.6**
 
 
Maintenant, vous pouvez accéder à la diffusion en direct de la caméra depuis n’importe quel navigateur via l’url **http://adresse_IP_du_raspberry:8080** . 

(image)

Où 8080 est le port qui est configuré dans le fichier motion.conf. Vous pouvez faire votre propre réglage pour le port en modifiant le paramètre “stream_port” dans motion.conf.

:warning: **Votre Pi et l'appareil sur lequel vous acceder à l'enregistrement video doivent etre dans le meme reseau pour fonctionner. Sinon pour avoir acces a votre flux video n'importe ou, utilisez un VPN.**

## Quelques PLus 

**Connexion SSH**

Il est aussi possible de configurer SSH sur votre Pi ainsi vous pourrez travailler depuis un terminal sur votre ordinateur. (ajouter un lien)

:loudspeaker: :heavy_exclamation_mark: :loudspeaker: :heavy_exclamation_mark:
Soyez sûr que les permissions sur les fichiers sont correctes : lorsque vous installez motion via ssh en étant connecté en tant qu’utilisateur “pi”, vous devez vous assurer de donner à l’utilisateur «motion» les autorisations pour exécuter motion comme service après le redémarrage :


      sudo chmod 664 /etc/motion.conf

      sudo chmod 755 /usr/bin/motion

      sudo touch /tmp/motion.log

      sudo chmod 775 /tmp/motion.log
      
  



