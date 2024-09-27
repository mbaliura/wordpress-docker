# Wordpres docker boilerplate with Xdebug

# How to run
1. Rename or copy `.env.example` to `.env`. Change env variables if necessary (defaults will also work).

    $ cp .env.example .env

2. Optional. When mysql container starting first time, they can be inited with DB-dump (if presented). So, if you have DB dump and want to init your app with it, put `.sql` file to `db/init` folder before first start of containers. There is also 'default' dump in `db/init`. Rename it to `backup.sql`, if you want to use it. User/password is `admin/admin` for this dump.

    $ mv db/init/backup.init db/init/backup.sql

3. Run Docker contaiters as usually with `docker compose up` or use shell script. At first run, this command pull the images, so it takes some time:

    $ ./up

4. Open *localhost:8000* to see running site

5. For developing you can place your developed plugins and themes in the respective `./plugins` and `./themes` folders.


## Why you need this?
This repo helps you run Wordpress for local dev purposes, or whatever.
Contain official WP image, Mysql, PHPMyadmin.
Original official Wordpres image doesn't contain Xdebug and WP-cli, so they will be installed automaticly on containers build.

## Requires
Docker, Bash

## Another usefull commands:

Run bash inside wordpress container:

    $ ./shell

Stop and remove containers:

    $ ./down

Rebuild containers (f.e. after config changes):

    $ ./rebuild

Make database dump (dump stored to db/backup.sql):

    $ ./db_dump

Restore database from dump (dump should be placed in db/backup.sql):

    $ ./db_restore