# woodby
Prototype for ISLE using only wodby images e.g. Drupal, PHP, Solr and Mariadb

* `mkdir codebase` in this project root
  * _`.gitignored` currently_

* `cp -Rv composer/* codebase/`
  * _this will be the composer.json & .lock files_

* Add this to `/etc/hosts`
  * `127.0.0.1 drupal.docker.localhost portainer.drupal.docker.localhost`

* `docker-compose pull`

* `docker-compose up -d`

* `docker exec -it my_drupal8_project_php -c "composer install"`

* Access site at: http://drupal.docker.localhost

* Follow instructions for Drupal 8 site setup
  * User, database and password are all: `drupal`
  * Mariadb host in `Advanced ...` dropdown is `mariadb`

* Configure Solr via ...

## Ignore and/or don't attempt to use

* `Makefile`
* `docker-compose.override.drupal`
* Additional services defined in `.env` file
* `docker-sync.yml`
* `traefik.yml`