# VM

Créer sa machine virtuelle en suivant la documentation ci-dessous: 

- [ ] [Générique](https://github.com/CollegeBoreal/Tutoriels/tree/master/2.Virtualisation/2.VM/1.Docker-Machine/0.Generic)

## Liste des machines

```
$ docker-machine ls
NAME          ACTIVE   DRIVER    STATE     URL                      SWARM   DOCKER      ERRORS
ambatolampy            generic   Running   tcp://10.13.14.15:2376           v19.03.13   
```


## Rendre une machine active

```
$ eval $(docker-machine env ambatolampy)
```
