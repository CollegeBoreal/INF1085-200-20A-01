# Reseau local  d'entreprise Amir Abdullahi 

:bookmark:  Objctif : du projet est configuration routage inter-vlan 
------------------------------------------------------------------------------
1.Routeur 
---------
Etape 1: configure de base  d'un routeur cisco 
------------------------------------

```
en
config t
hostname R1
line console 0
password cisco 
login
exit
line vty 0 4
password cisco 
login 
exit 
enable secret cisco
do wr
``````
Etape 2 : configure mode priviligie d'un routeur cisco 
-------------------------------------------------------
```
config t 
interface fastEthernet 0/0
ip address 192.168.0.1  255.255.255.0
no shutdown
exit
do wr
```

2.Switch 
------------
Etape 3: configure de base switch 
---------------------------------
Switch 0 est un mode server 
````
en
config t
hostname S0 
enable secret cisco
no ip domain-lookup
line console 0
password cisco
login 
line vty 0 15
password cisco
login
exit
do wr
````
``utiliser le meme commande de base les autres swith``


Etape 4: configuration du protocole VTP 
----------------------------------------
```
vtp mode server 
vtp domain service_12 
vtp password cisco
do wr
```
``idem mettez les autres switch vtp mode client ``

Etape 5: configuration Port trunck 
---------------------------------

```
interface range fa0/21-23
switchport mode trunk
no shutdown 
exit 
do wr
```

Etape 6: configuration vlan 
-----------------------------
```
vlan 99
name management
exit

vlan 10
name faculty-staff
exit

vlan 20
name dev
exit

vlan 30
name guest
exit
```
"une fois que vous configurez le protocole VTP la memoire switch server transmettre le mise a jour a les autres switch client"

Etape 7: Configuration interface vlan pour les trois switch client  
------------------------------------------------------------------
```
interface rang fa0/1-9
switchport mode access 
switchport access vlan 20 
exit 
interface rang fa0/10-15
switchport mode access 
switchport access vlan 10 
exit 

interface rang fa0/16-20
switchport mode access 
switchport access vlan 99
exit 

interface rang fa0/21-22
switchport mode access 
switchport access vlan 30
exit
do wr
```


GRACIAS 






