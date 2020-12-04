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

**Les étapes de l'écriture de mon code:**  

  1. **Importer** les modules, les plates-formes d'intégration, un framework, les serveurs HTTP, tout cela sur Phyton.  
    J'ai décidé d'importer les éléments suivants selon mes besoins:  
    
          ** serveur http pour écrire ma page browser sur laquelle sera réalisé le streaming live
          ** le framework socketserver, très utulisé sur Unix, à partir duquel le streaming sera configuré (utilisant StreamingOutput dans une définition sur Python                        https://pymotw.com/2/SocketServer/
             
          ** importer le module camera de RaspberrPi: picamera  
             Je me suis inspiré de ce projet suivant pour écrire le code à partir du modu;e  picamera et en l'intégrant sur la définition StreamingOutput  
             https://picamera.readthedocs.io/en/release-1.10/recipes1.html  
         
 Cela donnera le résultat suivant:
         
 <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/import.jpg" width="350">
         
   2. **Écrire le texte HTML** qui servira pourle browser pour lequel le live streaming sera utilisé. En effet, le but est d'ouvrir un broswer (Chrome, IE ou Firefox par           exemple), d'inscrire l'adresse IP de mon RaspberryPi et le port Raspberry utilisé pour pouvoir voir au final le live streaming.
      Dans le texte HTML, je vais donner le nom à ma page web en haut :'Projet Camera de surveillance College Boreal Zack SB'  
      Je vais aussi donner comme titre à ma page(en haut de la page ou s'affichera la cam): 'Zack SB Projet Camera College Boreal et la camera de surveillance live streaming'       Le live streaming se fera dans une image qui aura un cadre standard: 1280 pour la hauteur et 720 pour la hauteur.
      
 <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/html2.jpg" width="450">
      
   3. **Écrire** la fonction Output dans 3 différents class: StreamingOutput - StreamingHandler et StreamingServer  
      StreamingOutput  
      <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/output1.PNG" width="450">
      
      StreamingHandler  
      <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/Handler1.PNG" width="450">  
      
      
      <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/Handler2.PNG" width="450">
      
      StreamingServer est le troisiéme élément.  
      
      <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/server1.PNG" width="450">
      
      
      Il peremet entre autres, de mettre la caméra au format jpeg (préférable au format rgb, bien que j'ai essayé les deux). La résolution choisie sera 1280x120.  
      J'ai consulté le tableau suivant et ssayé plusieurs choix avant de m'arrêter à la résolution 1280X120 avec un framerate de 24.
      
       <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/frame.PNG" width="450">  
       
        
       Le code signifie que la caméra ne va pas s'arrêter à la prise d'images, ce qui permet le live streaming.
    
    
 
 
 Voici la version finale et complète du code utilisé:
  ```
              $import io
               import picamera
               import logging
               import socketserver
               from threading import Condition
               from http import server

               PAGE="""\
               <html>
               <head>
               <title>Raspberry Pi - Projet Camera de surveillance College Boreal Zack SB</title>
               </head>
               <body>
               <center><h1>Raspberry Pi -Zack SB Projet College Boreal et la camera de surveillance live streaming</h1></center>
               <center><img src="stream.mjpg" width="1280" height="720"></center>
               </body>
               </html>
               """

               class StreamingOutput(object):
                   def __init__(self):
                       self.frame = None
                       self.buffer = io.BytesIO()
                       self.condition = Condition()

                   def write(self, buf):
                       if buf.startswith(b'\xff\xd8'):
                           self.buffer.truncate()
                           with self.condition:
                               self.frame = self.buffer.getvalue()
                               self.condition.notify_all()
                           self.buffer.seek(0)
                       return self.buffer.write(buf)

               class StreamingHandler(server.BaseHTTPRequestHandler):
                   def do_GET(self):
                       if self.path == '/':
                           self.send_response(301)
                           self.send_header('Location', '/index.html')
                           self.end_headers()
                       elif self.path == '/index.html':
                           content = PAGE.encode('utf-8')
                           self.send_response(200)
                           self.send_header('Content-Type', 'text/html')
                           self.send_header('Content-Length', len(content))
                           self.end_headers()
                           self.wfile.write(content)
                       elif self.path == '/stream.mjpg':
                           self.send_response(200)
                           self.send_header('Age', 0)
                           self.send_header('Cache-Control', 'no-cache, private')
                           self.send_header('Pragma', 'no-cache')
                           self.send_header('Content-Type','multipart/x-mixed-replace; boundary=FRAME')
                           self.end_headers()
                           try:
                               while True:
                                    with output.condition:
                                        output.condition.wait()
                                        frame = output.frame
                                    self.wfile.write(b'--FRAME\r\n')
                                    self.send_header('Content-Type', 'image/jpeg')
                                    self.send_header('Content-Length', len(frame))
                                    self.end_headers()
                                    self.wfile.write(frame)
                                    self.wfile.write(b'\r\n')
                           except Exception as e:
                               logging.warning(
                                   'Removed streaming client %s: %s',
                                   self.client_address, str(e))
                       else:
                           self.send_error(404)
                           self.end_headers()

               class StreamingServer(socketserver.ThreadingMixIn,server.HTTPServer):
                   allow_reuse_address = True
                   daemon_threads = True

               with picamera.PiCamera(resolution='1280x720', framerate=24) as camera:
                   camera.rotation = 180
                   output = StreamingOutput()
                   camera.start_recording(output, format='mjpeg')
                   try:
                       address = ('', 8000)
                       server = StreamingServer(address, StreamingHandler)
                       server.serve_forever()
                    finally:
                        camera.stop_recording()
 ```
 
 
## Ouvrir un browser avec l'adresse IP et le port
L'adrees Ip du Raspberry Pi est donc 192.168.2.25  
Le port pour RaspberryPi est 8000  
Il faut donc ouvrir un browser de son choix tel que IE ou Chrome.  

Je choisit Chrome:  


| <img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/stream2.jpg" width="250"> 


Voilà donc le résultat: le live streaming près de mon bureau, dans le salon!

## Le rendu de la caméra Live streaming

En direct, je peux regarer le live streaming de mon salon:

<img src="https://github.com/CollegeBoreal/INF1085-200-20A-01/blob/master/P.Projets/300115140/IMAGES/stream1.jpg" width="250">  



[//]: <(https://placehold.it/20/157500?text=+) green!>
![](https://placehold.it/350x90/009955/fff?text=ETVOILA!!!)
