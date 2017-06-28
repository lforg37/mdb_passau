# Multimedia database project - Universität Passau

## Presentation

## Requirements
In order to run this project you need docker and docker-compose installed.
You also need a docker image with oracle 11g installed in it named oracle11g-installed. 
We recommand to use the base image from [jaspeen](https://github.com/jaspeen/oracle-11g "Jaspeen oracle-11g github")

## Installation

Clone this repository and the submodules :
```
git clone git@github.com:lforg37/mdb_passau.git
cd mdb_passau
git submodule init
git submodule update
```

## Usage
Use the docker-compose client to start the whole system
```
docker-compose up
```

At the first start, the complete corel10k dataset will be downloaded which could take a while.
If you already have the picture from the dataset you can stop the corel10k_fetcher service and copy the data_set in the corel-10k volume. Please restart the corel10k_fetcher service after that in order to proceed to the indexing of the pictures.

In order to properly remove every docker artefact that has been created during the run of the programm, please run `docker-compose down`. Please note that the associated volume and images are not removed automatically.
