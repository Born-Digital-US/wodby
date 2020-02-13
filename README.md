# wodby proto
Prototype for ISLE using only wodby images e.g. Drupal, PHP, Solr and Mariadb

* `mkdir codebase` in this project root
  * _`.gitignored` currently_

* `cp -Rv composer/* codebase/`
  * _this will be the composer.json & .lock files_

* `cp scripts/install-drupal-modules.sh codebase/`
  * _to be used later to install Drupal Solr search modules_

* Add this to `/etc/hosts`
  * `127.0.0.1 drupal.docker.localhost portainer.drupal.docker.localhost`

* `docker-compose pull`

* `docker-compose up -d`

* `docker exec -it my_drupal8_project_php bash -c "composer install"`

* Access site at: http://drupal.docker.localhost:8000

* Follow instructions for Drupal 8 site setup
  * Choose language, click blue `Save and continue`button
  * Select `Standard` for the installation profile
  * Database type: `MySQL, MariaDB, Percona Server, or equivalnet`
    * Database name, user and password are all: `drupal`
    * Advanced options > Host: `mariadb` (_change from localhost_)
      * Port number: `3306`
      * Table name prefix: `leave blank`
    * Click the blue `Save and continue` button
* Configure site 
  * Site name: `ISLE 8 Local`
  * Enter the `Site email address, Username, password, email address, default country and default time zone` settings of your choice.
  * Click the blue `Save and continue` button

* `docker exec -it my_drupal_project_php bash -c "chmod +x install-solr-drupal-modules.sh && ./install-solr-drupal-modules.sh"`


## Ignore and/or don't attempt to use

* `Makefile`
* `docker-compose.override.drupal`
* Additional services defined in `.env` file
* `docker-sync.yml`
* `traefik.yml`
