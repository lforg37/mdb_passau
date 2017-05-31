# Architecture du système

## Volumes :
 - Un volume de stockage des fichiers envoyés par le client web
 - Un volume de stockage des images du dataset core10k
 - Un volume de stockage de la BDD (construit avec l'image jaspeen)

## Client Web :
### Conteneurs :
* Un conteneur nginx proxy et serveur static sur les images
* Un conteneur nodejs pour l'interaction client

### Connexion avec les volumes :
* Connexion avec le volume de stockage des images core10k en lecture (pour le conteneur nginx)
* Connexion avec le volume de stockage des fichiers temporaires en écriture (pour le conteneur nodejs)

### Ports et liens
* Port 80 ouvert pour intercepter les requêtes http client (proxy nginx)
* Lien avec le conteneur de BDD pour requêter les noms d'images proches
* Port ouvert sur l'app node
* Lien entre le proxy et l'app node

## BDD :
### Conteneurs :
* Un conteneur de BDD oracle 12c basé sur jaspeen

### Volumes :
* Connexion avec le volume de BDD en lecture et écriture

### Ports et liens
* Port ouvert pour l'interrogation de la BDD
* Lien vers le conteneur LIRE

## Conteneur LIRE

### Conteneurs :
* Conteneur contenant une instance de LIRE et son moyen d'interrogation

### Volumes :
* Lecture sur les deux volumes d'images

### Ports et liens :
* Port ouvert pour l'interrogation via API on sait pas trop comment mais API réseau



