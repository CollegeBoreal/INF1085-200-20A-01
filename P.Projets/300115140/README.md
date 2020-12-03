# PROJET RASPBERRY PI - SYSTEME DE SÉCURITÉ VIDEO EN STREAMING LIVE 📹👮       

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/camera1.jpg" width="250">

## Table des matiéres:
1. Introduction
2. Le matériel nécessaire
3. Mettre en marche la fonction caméra sur RaspberryPi
4. Trouver l'adresse IP
5. Télécharger Thonny Python IDE sur Linux
6. Crééer le code Python sur Thonny: les étapes
7. Ouvrir un browser avec l'adresse IP et le port
8. Le rendu de la caméra Live streaming


## Introduction

Ce projet permet d emettre en place une caméra de surveillance live streaming qui permettra de surveiller en direct un lieu pré-défini. Il pourra être utilisé pour surveiller par exemple, l'entrée de sa maison, une chambre dans la maison, le salon pour surveiller son chien, ou encore son magasin, son jardin ou sa maison secondaire. La caméra utilisée sera une PiCam donc avec peu de frais et le visionnage se fera à partir d'un browser que ce soit Chrome, Foxfilla ou IE car nous utiliserons une adresse IP.


## Rassembler le matériel Raspberry Pi + CamPi + câbles
Il faut en effet plusieurs choses pourpouvoir mener à bien ce projet.Voici une liste de ce que j'ai utilisé:

  * un **raspberryPi 4** avec 8Go
  * une RasberryCam 
  * un HDMI to VGA Converter pour pouvoir avoir accès à un écran
  * câbles USB pour connecter clavier et souris au RaspberryPi

| RaspberryCam | câbles | HDMI
| ------------ | ------------- | -------------
| <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/cam1.jpg" width="150"> | <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/cables.jpg" width="150">| <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/HDMI.jpg" width="150">

## Mettre en marche la caméra sur RaspberryPi(enable camera)

Une fois que le RaspberryPi est branché sur un clavier et un écran, nous arrivons sur l'écran comme l'image ci-desssous. RaspberryPi utilise Linux Debian, nous allons donc d'abord enable la caméra sur Linux pour pouvoir l'utiliser et ensuite récupérer l'adresse IP.

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/ecran.jpg" width="350">


Pour activer la caméra, nous allons sur Menu>RaspberryPi Configuration>Interfaces>Camera>Enable

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/enable1.jpg" width="350">
<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/enabl2.jpg" width="350">



## Trouver l'adresse IP de mon RaspberyPi

Ensuite, il faut trouver l'adresse IP du RaspberryPi car nous en aurons besoin pour le live streaming. pour cela, il faut aller dans le terminal et taper la commande suivante:  
**hostname -I** 


<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/ip.jpg" width="350">

L'adresse IP de mon RaspberryPi est: **192.168.2.25**

## Télécharger Thonny IDE sur Linux

Il exist plusieurs IDE pour écrire son code Python ou HTML. Sur Debian, aprés avoir essayé plusieurs, je pense que ThonnyIDE est le meilleur et le plus simple d'utilisation. Pour le télécharger, il faut aller sur le terminal et taper la commmande suivante:  
**sudo apt install thonny**

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/thonny1.jpg" width="350">

_Troubleshooting_: il est possible d'avoir des messages d'erreur en voulant télécharger Thonny. A ce moment-là, je conseille de faire un update sur Debian en tapant  
**$ sudo apt full-upgrade**  
Si l'erreur persiste, cela voudrait dire que Linux est en train de réaliser des updatess et qu'il ne peut pas installer encore Thonny. Il faut patienter et refaire la demande d'installation, ou encore arrêter les updates avec  
**$ sudo killall apt apt-get**


## Créer le code Python sur Thonny IDE
Nous voilà installer avec la dernière version de Thonny IDE (3.3.0)

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/thonny.jpg" width="350">

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/thonny3.jpg" width="350">

Les étapes de l'écriture de mon code:  
  * importer les modules, les plates-formes d'intégration, un framework, les serveurs HTTP, tout cela sur Phyton.  
    J'ai décidé d'importer les éléments suivants selon mes besoins:  
    
          ** serveur http pour écrire ma page browser sur laquelle sera réalisé le streaming live
          ** le framework **socketserver**, très utulisé sur Unix, à partir duquel le streaming sera configuré (utilisant StreamingOutput dans une définition sur Python)
    
[url](https://pymotw.com/2/SocketServer/)  
    
    
    
    
## Ouvrir un browser avec l'adresse IP et le port



## Le rendu de la caméra Live streaming

[//]: <(https://placehold.it/20/157500?text=+) green!>
![](https://placehold.it/350x90/009955/fff?text=TADA!!!)
