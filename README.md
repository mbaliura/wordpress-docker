# Wordpres docker boilerplate with Xdebug

## Why you need this
This repo helps you run Wordpress for local dev purposes, or whatever.
Contain official WP image, Mysql, PHPMyadmin.
Original official wordpres image doesn't contain Xdebug and WP-cli, so it will be installed automaticly on containers build.

## Requires
Docker and Docker-compose.

## How to run
Rename or copy `.env.example` to `.env`. Change env variables if necessary.
Run Docker contaiters as usually with `docker-compose up` or use shell script:

    $ ./up

At first run, this command pull the images, so it takes some time.
When mysql container starting first time, they can be inited with sql-dump. Just put `.sql` file to `db/init` folder before first start of the container, and wait for a while.

__Open localhost:8000 to see running site__

## Some another usefull commands:

Run bash inside wordpress container:

    $ ./shell

Stop and remove containers:

    $ ./down

Make database dump (dump stored to db/backup.sql):

    $ ./db_dump

Restore database from dump (dump should be in db/backup.sql):

    $ ./db_restore