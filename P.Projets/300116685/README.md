## Reseau local  d'entreprise Amir Abdullahi 

![image](inter13.PNG)

:bookmark:  Objctif : du projet est configuration routage inter-vlan 
------------------------------------------------------------------------------
1.Routeur 
---------
Etape 1: configure de base  d'un routeur cisco 
------------------------------------

![image](1.PNG)
```
R1#en
config t
hostname R1
R1(config)line console 0
R1(config)password cisco 
R1(config)login
R1(config)exit
R1(config)line vty 0 4
R1(config)password cisco 
R1(config)login 
R1(config)#exit 
R1(config)#enable secret cisco
R1(config)#do wr
``````
#configuration SSH du routeur 
```
R1(config)#ip domain-name borealc.on.ca 
R1(config)#crypto key generate rsa
R1(config)#transport input ssh
R1(config)#login local
$ ssh -oKexAlgorithms=+diffie-hellman-group14-sha1  amirali11@10.13.237.200
```
Etape 2 : configure mode priviligie d'un routeur cisco 
-------------------------------------------------------
```
config t 
R1(config)#interface Ge 0/0/0
R1(config)#ip address 192.168.0.1 255.255.255.0
R1(config)#no shutdown
R1(config)#exit
R1(config)# interface Ge 0/0/1
R1(config)#ip address 10.13.237.200  255.255.255.0
R1(config)#do wr
R1# ip route 0.0.0.0 0.0.0.0 Ge0/0/1
```

2.Switch 
------------
Etape : configure de base switch 
---------------------------------
 
````
en
config t
hostname S0 
enable secret cisco
line console 0
password cisco
login 
line vty 0 15
password cisco
login
exit
do wr
````
configuration SSH du commutateur (switch )
```
ip domain-name borealc.on.ca 
crypto key generate rsa
transport input ssh
login local
```
  utiliser le meme commande de base les autres swith

Etape : configuration vlan 
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
#configuration address ip du vlan 1
```
 int vlan 1
 ip address 192.168.0.10 255.255.255.0
 no shutdown 
 exit
 
```

Etape : Configuration interface vlan  
------------------------------------
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






