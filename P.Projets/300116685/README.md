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
:utiliser le meme commande de base les autres swith:
Etape 4: configuration du protocole VTP 
----------------------------------------
```
vtp mode server 
vtp domain service_12 
vtp password cisco
do wr
```

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
