# Aide mémoire Docker

## Installation

### Windows

```
https://download.docker.com/win/stable/InstallDocker.msi
```

### MacOS

```
https://download.docker.com/mac/stable/Docker.dmg
```

### Linux

```
curl -sSL https://get.docker.com/ | sh
```

## Les images

### Recherche

```
docker search nginx
```

### Récupérer une image

```
docker pull nginx
```

## Lancer un conteneur 

* Démarre l’image ubuntu:latest
* Déclare le port ```80``` du conteneur sur le port 3000 de votre machine.
* Monte le dossier courant dans le dossier ```/data``` du conteneur
* Note: Sur Windows vous devez remplacer ```-v ${PWD}:/data``` par ```-v "C:\Data":/data```

```
docker run --name monConteneur -it -p 3000:80 -v ${PWD}:/data ubuntu:latest
```

## Les Logs

### Afficher les logs

```
docker logs monConteneur
```

### Afficher et suivre les logs

```
docker logs monConteneur -f
```


