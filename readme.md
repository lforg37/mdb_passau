# Multimedia database project - Universität Passau
# Nicolas BONFANTE - Paul COMPAGNON - Luc FORGET

## Presentation

## Requirements
In order to run this project you need : 
  * docker and docker-compose installed.
  * a docker image with oracle 11g installed in it, named oracle11g-installed. (We recommand to use the base image from [jaspeen](https://github.com/jaspeen/oracle-11g "Jaspeen oracle-11g github"))
  * To get the Oracle instant-client rpm for the client container : download `oracle-instantclient12.2-basic-12.2.0.1.0-1.x86_64.rpm` for `linux x86_64` from [this page](http://www.oracle.com/technetwork/topics/linuxx86-64soft-092277.html) and put it at the root of the mdb_client repository which should appear once the submodule initiated and updated.

## Installation

Clone this repository and the submodules :
```
git clone https://github.com/lforg37/mdb_passau.git
cd mdb_passau
git submodule init
git submodule update
```

## Usage
Use the docker-compose client to start the whole system
```
docker-compose up
```
Open localhost:4242 in your web browser to access the project. 

At the first start, the complete corel10k dataset will be downloaded which could take a while.
If you already have the picture from the dataset you can stop the corel10k_fetcher service and copy the data_set in the corel-10k volume. Please restart the corel10k_fetcher service after that in order to proceed to the indexing of the pictures.

In order to properly remove every docker artefact that has been created during the run of the programm, please run `docker-compose down`. Please note that the associated volume and images are not removed automatically.
