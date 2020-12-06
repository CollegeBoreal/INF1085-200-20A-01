# :pushpin: NEXTCLOUD

---
## A PROPOS 
 **NextCloud**est un logiciel libre, de site d'hébergement de fichiers et une plateforme de collaboration. À l'origine accessible via WebDAV, n'importe quel navigateur web, ou des clients spécialisés, son architecture ouverte a permis de voir ses fonctionnalités s'étendre depuis ses origines. En 2020, il propose de nombreux services.

---

# INSTALATIONS :round_pushpin:

## :one: Snap  
**Snap** Le format snap vise à permettre l'installation de nouvelles versions de logiciels dans les systèmes Linux, tout en apportant aux développeurs la facilité de distribution, la fiabilité et la sécurité.Nous l'utiliserons pour installer notre NextCloud 
```
$ sudo apt install snapd
```
![install snap](Img/image-1.PNG)

```
Vérification du staut de snap

$systemctl status snap
```
![Verif status snap](Img/image-2.PNG)

## :two:NextCloud
```
$sudo snap install nextcloud
```
![install nextcloud](Img/image-3.PNG)

# CONFIGURATION DE NEXTCLOUD:round_pushpin:

## :one: Configuration de l'Administrateur
![Config Admin](Img/image-4.PNG)
## Installation des applications

```
Une fois l'administrateur cré les applications (Utilitaires) s'installent automatiquement
```
![install app](Img/image-5.PNG)

```
 Tableau de Bord
```
![Tableau bor](Img/image-6.PNG)
## :two:Création d'un utilisateur
```
$ sudo nextcloud.occ user:add Bertrand
```
![Crea User](Img/Capture-8.PNG)
## PREREQUIS



