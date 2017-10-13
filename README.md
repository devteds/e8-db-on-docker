# README

Devteds [Episode #8](https://devteds.com/episodes/8-mysql-and-postgresql-with-docker-in-development) source code

Run multiple versions of MySQL databases and PostgreSQL with Docker using Docker Compose. Test multiple options of connecting to the databases running in containers.

[![Episode Video Link](https://s3.us-east-2.amazonaws.com/devteds/episodes/e8-db-on-docker.png)](https://www.devteds.com/episodes/8-mysql-and-postgresql-with-docker-in-development)

[Episode video link](https://youtu.be/q5J3rtAGGNU)


Visit https://devteds.com to watch all the episodes

## Tested on

- macOS 10.12.3
- Docker 17.06.2-ce
- Docker Compose 1.14.0
- MySQL Workbench 6.3

## Run services

```
mkdir ~/projs
cd ~/projs
git clone https://github.com/devteds/e8-db-on-docker.git db-on-docker
cd db-on-docker
mkdir data
docker-compose up

# on new terminal tab
cd ~/projs/db-on-docker
docker-compose ps
```

## Test connection - multiple options

- Test connection w/ database client on host OS using host OS ports
- Test with PHP based adminer tool that run on container - http://localhost:8080
- Test with databse clients within running containers. Examples below

```
docker-compose exec mysql-dev mysql -uroot -ppassword blogapp
docker-compose exec mysql-legacy mysql -uroot -ppassword legacyapp
docker-compose exec pgdb psql -U root -W blogapp
```

## A few useful commands

```
docker-compose stop
docker-compose rm
docker-compose rm -f 
```

## References

Find the resources and references on [https://devteds.com/episodes/8-mysql-and-postgresql-with-docker-in-development](https://devteds.com/episodes/8-mysql-and-postgresql-with-docker-in-development)
