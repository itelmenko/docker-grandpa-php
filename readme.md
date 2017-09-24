# docker-grandpa-php

It's configuration for docker-compose with images Apache + php5.3, mysql, mariadb and memcached. It is useful for old php projects on php5.3.

# Requerements

* docker
* docker-compose 

# Installation

* Just clone it into any directory 
* Edit option MAIN_WEB_ROOT_PATH and another options in docker-compose.yml
* Add virtual host configuration for Apache into main/sites folder. Use example file in it
* Add your local domains in /etc/hosts
* Run docker-compose "up" command:

```
docker-compose up -d main mysql  
```

or

```
docker-compose up -d main mariadb  
```

# Useful commands

Open bash terminal in main container:

```
docker-compose exec main bash
```

Show list of containers and them statuses:

```
docker-compose ps
```

Stop all container of current build:

```
docker-compose stop
```
