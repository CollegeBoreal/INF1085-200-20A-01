# WikiMedia

:bookmark: How to Install Apache Web Server on Ubuntu 20.04
1. Tout d'abord, connectez-vous à votre système Ubuntu 20.04 
et mettez à jour vos packages système en utilisant les éléments suivants
```
$ sudo apt update
```
2. Une fois le processus de mise à jour terminé, installez le logiciel du serveur Web Apache2 comme suit.
``` 
$sudo apt install apache2
```
3. Lors de l'installation du package Apache2, le programme d'installation déclenche systemd pour démarrer et activer automatiquement le service apache2. Vous pouvez vérifier que le service apache2 est actif / en cours d'exécution et qu'il est activé pour démarrer automatiquement au démarrage du système en utilisant les éléments suivants

```
$ sudo systemctl is-active apache2
$ sudo systemctl is-enabled apache2
$ sudo systemctl status apache2
```

4. Maintenant que votre serveur Web Apache est en cours d’exécution, il est temps d’apprendre quelques commandes de gestion de base pour gérer le processus Apache à l’aide des commandes systemctl suivantes.
```
$ sudo systemctl stop apache2      
$ sudo systemctl start apache2     
$ sudo systemctl restart apache2  
$ sudo systemctl reload apache2    
$ sudo systemctl disable apache2   
$ sudo systemctl enable apache2   
```
5.Tous les fichiers de configuration Apache2
```
$ ls /etc/apache2/*
```
6. Pour définir le nom de domaine complet du serveur Web, utilisez ServerName
```
$sudo vim /etc/apache2/apache2.conf 
