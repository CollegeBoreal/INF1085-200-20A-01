

--Dans ce fichier, je vais vous expliquer comment installer OpenVPN-server et sur votre serveur, apres le configurer pour recevoir un script dans lequel il y a des clées codées, 
  avec lequel, votre OpenVPN -client peut se connecter à ce serveur sur une connexion point-to-point. après je vous explique comment préparer votre ordinateur pour être capable   de se connecter à son serveur.
 
 -- À la fin, je vais vous montrer comment vous assurer que vous êtes connecté à votre serveur à partir de votre OpenVPN en utilisant:
 
 -- 1- La commande TRACERT
 
 -- 2- Firewalld. D'abord je vous explique comment installer firewalld sur votre serveur,et comment le configurer. Et après, le configurer d'une manière que seulement une           spécifique address IP ait l'autorité de le conneceter. À la suite, vous utilisez SSH et l'address IP de l'interface de votre OpenVPN pour vous connecter à votre serveur.
 


 -- D'abord en utilisant les commmandes suivantes on va recevoire les derniers mis à jours.
 
 :~$ sudo apt-get update
 
 :~$ sudo apt-get upgrade
 
 ![image](22.PNG)
 ![image](1000.PNG)



-- En utilisant ce commande on peut télécharger le script d'installation de OpenVPN:


:~$ wget https://git.io/vpn -O openvpn-ubuntu-install.sh



![image](1.PNG)



-- Maintenant on va changer le mode scrip pour le rendre executable: 



:~$ chmod -v +x openvpn-ubuntu-install.sh


![image](2.PNG)



--on peut vérifier le contenu du fichier en utilisant nano ou vi: 


:~$ nano openvpn-ubuntu-install.sh


![image](3.1.PNG)



![image](3.PNG)



-- executer le script pour installer le serveur OpenVPN 


:~$ sudo ./openvpn-ubuntu-install.sh


![image](4.PNG)



-- D'abord vous devevez choisir que quelle adresse IP sera utilisée par votre client OpenVPN pour se connecter au serveur.
   Dans ce cas, mon client utilisera 10.13.237.100.
   Après vous pouvez vérifier que votre adresse IP pulic sera utilisé afin que votre serveur soit capable de se connecter à l'internet.
   dans l'étape suivante, vous devez choisir votre DNS server.
   Maintenant, vous devez écrire le nom de votre utilisateur, et ça va devenir le nom de script qui sera créé par votre serveur, avec lequel, votre clien      sera capable de se connecter à ce serveur. Dans ce cas, j'ai écrit (morti).
   
   
   
![image](5.PNG)


  -- Une fois que la configuration sera terminé, vous pouvez vérifier dans les deux dernières lignes, le chemain pour avoir au script créé par votre serveur      pour votre clien nomé morti.ovpn. oon va l'utiliser pour importer ce script dans notre client-OpenVPN.
  
  
  
 ![image](6.PNG)
  
-- Maintenant votre Openvpn-serveur ets prêt, et vous pouvez vérifier son statut en utilisant la commande suivante:
  
-- sudo systemctl status openvpn-server@server.service

--le statut du serveur, c'est active(running) 

![image](7.PNG)



pour changer le statut de votre serveur, vous pouvez utiliser les commandes suivantes selon vos besoins:



 --  :~$ sudo systemctl start openvpn-server@server.service
 --  :~$ sudo systemctl restart openvpn-server@server.service
 -- :~$ sudo systemctl stop openvpn-server@server.service
 
 

--Le moment où, vous configuré votre serveur OpenVPN avec le script openvpn-ubuntu-install.sh, une spécifique interface sera configuré pour votre connexion,
--le status de cette interface sera point-to-point, et utilise l'adresse IP de l'intervalle 10.8.0.0/24.
-- on peut le vérifier avec la commandeci-dessous:

--:~$ ip addr

![image](8.PNG)



--- Maintenant, on doit installer OpenVPN sur la machine de notre client:

-- sur Windows, oo peut utiliser:

-- > choco install openvpn 


![image](21.PNG)



-- sur Linux, on peut utiliser:

-- sudo apt-get install openvpn

-- sudo apt-get install network-manager-openvpn



![image](100.PNG)


-- Maintenant c'est le moment d'arriver à notre serveur et prendre notre script de configuration.
-- Dans notre machine client-serveur, en utilisant cette commande, on arrive à notre serveur en utilisant Gitbash, et on copie ce fichier dans notre machine:

 -- ssh morti@10.13.237.100 "sudo -S cat /root/morti.ovpn" > morti.ovpn
 
 ![image](9.PNG)
 
 
 ![image](10.PNG)
 
 
 
 -- Maintenant, d'abord il faut touver ce fichier sur votre ordinateur:
 
 
 ![image](11.PNG)
 
 
 -- À la suite, il faut le mettre dans le fichier de config de votre OpenVPN.
 
 
 
  ![image](12.PNG)
  
  
 
 -- Faites clique droit sur l'application de OpenVPN, cliquez sur Properties, et cochez les option comme la photo suivante.
   
   
   
   ![image](13.PNG)
   
   
   ![image](14.PNG) 
   
   
 -- Maintenant, OpenVPN va créer connexion entre votre ordinateur et votre serveur en utilisant ce fichier: 
 
 
  ![image](15.PNG)
  
  
  -- Dès que la connexion est établie, vous pouvez vérifier votre address IP, et l'interface Point-to-point créée dans l'intervalle 10.8.0.0/24
  
  
   ![image](17.PNG)
   
 
 -- vous pouvez toujours vérifier le statut de votre OpenVPN en cliquant sur :
 
 
   ![image](19.PNG)
 
 
 -- en utilasant la commande ifconfig, vous pouvez vous assurer que vous avez reçu la bonne adresse IP:  
 
 
    ![image](16.PNG)
 
 
 -- en utilisant la commande tracert et addresse Ip de l'interface de votre serveur, vous pouvez vous assurer que c'est une connection point-to-point.
 
  ![image](18.PNG)
 
 
 --Maintenat, on va installer firewalld sur notre serveur.
 
 ![image](24.PNG)
 
 
 -- on peut vérifier le statut de notre firewall en utilisant la commande suivante:
 
  ![image](26.PNG)
 
 
 -- il y a deux méthodes pour donner l'autorité à un spécifique protocole pour passer de notre firewall, soit par son numéro de porte, soit par son nom. je vais vous montrer
     les deux manières. 
     
     
  morti@morti:~$ sudo firewall-cmd --permanent --add-port=80/tcp
  
  morti@morti:~$ sudo firewall-cmd --permanent --add-port=443/tcp

  morti@morti:~$ sudo firewall-cmd --permanent --add-port=1194/udp
  
  
  morti@morti:~$ sudo firewall-cmd --permanent --add-service=http

  morti@morti:~$ sudo firewall-cmd --permanent --add-service=https

  morti@morti:~$ sudo firewall-cmd --permanent --add-service=ssh

  ![image](27.PNG) 
  
  -- quand vous ajoutez une nouvelle règle à votre firewall, faites le commande reload pour vous assurer qu'il a été ajoutée:
  
  morti@morti:~$ sudo firewall-cmd --reload

  -- vous pouvez aussi vous assurer du statut de votre firewall et les services et les services offerts:
  
 morti@morti:~$ sudo firewall-cmd --state
 
 morti@morti:~$ sudo firewall-cmd --list-services

 
 
 --- Maintenant, je voudrais configurer mon firewall pour donner seulement le droit de connecter à mon ordinateur avec adresse IP 10.8.0.2 à mon serveur, en fait, à l'interface      10.8.0.1 de mon serveur. comme ça, seulement cette adresse IP peut se connecter à mon serveur, en utilisant SSH.

 morti@morti:~$ sudo firewall-cmd --add-rich-rule='rule family="ipv4" source address="10.8.0.2" port protocol="tcp" port="22" accept'

   ![image](29.PNG)
   
   -- on arrive sur notre ordinateur et cette fois-ce, on utilise SSH avec address IP de notre OpenVPN, à la place de 10.13.237...
   
   ![image](30.PNG)
   
   ![image](31.PNG)
   
   --Dans ces deux dernières photos je vous montre que quand mon OpenVPN est étaind je peux pas arriver à mon serveur, mais quand il est allumé, mon SSH marche.
   
   
   ![image](32.PNG)
   
   
   ![image](33.PNG)
   
   
