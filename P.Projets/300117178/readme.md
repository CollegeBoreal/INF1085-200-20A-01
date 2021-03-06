#  :pushpin: Video Streaming

---
# Introduction et matériel utilisé
* **Raspberry Pi** [==>](https://www.amazon.fr/gp/product/B00Q8MM4PI/ref=as_li_tl?ie=UTF8&camp=1642&creative=6746&creativeASIN=B00Q8MM4PI&linkCode=as2&tag=magdiblog-21&linkId=ILNQLTZCCS5EITBS)

* **Module Camera** [==>](https://www.amazon.fr/gp/product/B00E1GGE40/ref=as_li_tl?ie=UTF8&camp=1642&creative=6746&creativeASIN=B00E1GGE40&linkCode=as2&tag=magdiblog-21&linkId=5AG5Y5WRP3IRFDAU)

* **Carte micro-SD Sandisk 8Go**

 
---
```{r setup, include=FALSE}
ALL STEPS:
```
DESCRIPTION
--------------------------------------------------
### :a: :star: First Step :star:
:one: On installe **Raspbian**, tout ce qu’il y a de plus standard, on se connecte à son réseau WiFi et on active le module caméra grâce à l’outil **raspi-config**.



 ## **INSTALLER Raspbian SUR SON RASPERRY PI**
 1. Installer raspberry imager[->](https://www.raspberrypi.org/software/)
 2. Choisir un system d'exploitation dans mon cas j'ai choissis Raspbian
 ## **NB:choisir raspbian est tres conseiller pour pouvoir facilement utilise le module camera et autres plugins raspberry pie**
 
 <img src="img/raspberry.JPG" height=350 width="450"></img>
 

 3. Choisr la carte sd dans laquelle vous allez monter l'image
 4. write
 
  <img src="img/raspberry Pi image.JPG" height=350 width="450"></img>
 
  
 ### :b: Second Step 
 :two: configurer et activer notre camera
 
 1. Installer les dernieres mis a jour du noyau
 
```{r}
$ sudo apt update
$ sudo apt full-upgrade
```
2. activez votre camera grace a la commande

```{r}
sudo raspi-config

```
**interface option** puis **camera**
## :exclamation:**NOTE:Installer raspi-config on linux si vous ne l'avez pas par default [==>](https://rootsaid.com/raspi-config-install-setup-in-any-raspberry-pi-linux-os/)**


**NB: EN General le module camera est par default activer** 

3. tester votre camera

```{r}
$ raspistill -v -o test.jpg

```
vas donner un preview et prendre une photos test.jpg

### :cinema: Last Step:Video Streaming avec raspberry pie camera :cinema:
1. voir son addresse ip

```
$ sudo apt-get install net-tools
$ sudo ifconfig | grep -i mask
```
![ip address/mask](img/st1.JPG)

2. ecrivons notre script screaming
### le script dans [=>](https://github.com/CollegeBoreal/INF1085-200-20A-01/tree/master/P.Projets/300117178/src)
copiez streaming.py dans votre raspberry pie

### :red_circle: modifier affichage html
![ip address/mask](img/st2.JPG)

remplacer les tag **title** ou **h1**

### :red_circle: changer la resolution video
![ip address/mask](img/st3.JPG)

peut etre plus **grande**

## :warning: par defaut le picamera est deja installer dans raspbian sinon pour l'avoir avec les derniers mise a jour

```
# sudo apt-get install python3
# sudo apt-get install python3-picamera
```

3. lancer le script

```
$ python3 streaming.py

```

5. tapez votre **address ip:8000** dans le navigateur
### :warning: votre pc et raspberry pie doivent etre dans le meme reseau
#### :red_circle: creez un mobile hostpot dans window 10 et connectez votre pie au wifi



![ip address/mask](img/st4.JPG)


![ip address/mask :100:](img/st5.JPG)
 


### SOURCE
[:round_pushpin:get started with picamera](https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/6)

### bonus
## :a: file share avec samba [==>](https://www.etechpath.com/how-to-share-files-between-raspberry-pi-windows-using-shared-folder/#:~:text=%20How%20to%20share%20files%20between%20Raspberry%20Pi,%2Fetc%2Fsamba%2Fsmb.conf%0Api%40raspberrypi%20~%20%24...%204%20Restart%20SAMBA%2C%20More%20)

## :b: open ssh [==>](https://thishosting.rocks/how-to-enable-ssh-on-ubuntu/#:~:text=%20How%20to%20Enable%20SSH%20on%20Ubuntu%20%2820.04%2C,changing%20the%20default%20port%20%28recommended%20for...%20More%20)





