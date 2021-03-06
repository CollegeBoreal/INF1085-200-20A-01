# Shell Suite

Fichier .bashrc (profile)

:m: Sur votre serveur:

:one: Modifier votre prompt pour afficher `[moi@ip-10-13-237-16 /home/moimeme]$` dans votre fichier `.bashrc`

:two: Récupérer votre fichier `.bashrc` du serveur et mettez son contenu dans le fichier .:id:`.rc` de ce répertoire présent

example

```
$ scp ubuntu@10.13.14.15:.bashrc .300098957.rc
```

* Pemissions

https://www.tutorialspoint.com/unix/unix-file-permission.htm

* Variables d'environnement

https://www.tutorialspoint.com/unix/unix-environment.htm

## Docker Machine

* voir les machines virtuelles disponibles

```
$ docker-machine ls
NAME           ACTIVE   DRIVER    STATE     URL                     SWARM   DOCKER     ERRORS
fianarantsoa   -        generic   Running   tcp://10.13.5.21:2376           v19.03.5   
```

* remettre à zéro

```
$ docker-machine env --unset
unset DOCKER_TLS_VERIFY
unset DOCKER_HOST
unset DOCKER_CERT_PATH
unset DOCKER_MACHINE_NAME
# Run this command to configure your shell: 
# eval $(docker-machine env --unset)
```

<image src="images/docker-engine.png" width="980" height="540"></image>

## Archive

Linux In Action: Chapitre 4

Sur votre PC en `git bash`

- [ ] Cloner le cours INF1006 sur votre PC dans votre répertoire `~/Developer` (si ce n'est pas déjà fait)

- [ ] Trouver un groupe de fichier (i.e. .sql) en utilisant l'utilitaire `find` de votre répertoire `~/Developer`

- [ ] en créer un fichier compressé avec l'utilitaire `tar` ayant comme nom `b`:id:`.tar.gz`

- [ ] copier le fichier sur votre serveur Linux scp `~/Developer/SQL/b`:id:`.tar.gz` 

- [ ] décompresser le fichier sur le serveur linux
