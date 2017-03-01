Docker example for a normal web (Drupal) site
=============================================

Build status
------------

[![Build Status](https://travis-ci.org/cameronandwilding/dockertest.svg?branch=master)](https://travis-ci.org/cameronandwilding/dockertest)


This repository is educational / sample to provide some bootstrapping code to create Docker containers for y/our projects.

What does Docker provide? Docker is a superlight "virtualization" that makes you insulated environments for - let's say webservers, php, redis, solr, mysql - everything. This and the ability to configure it allows you and other developers to instantly setup development environment without compromising anything on your host machine.

Why this and not Vagrant? The pros:
- Vagrant is full fledged VM, this is not
- Vagrant needs heavy provisioning, this does not
- Docker has built in scaling (one command and you have any number of servers)
- Docker is supported on major hosting and CI platforms
- it works on very small footprint


# Recommended material

[Docker in Action](https://www.manning.com/books/docker-in-action)


# Requirements

* [Docker](https://www.docker.com/products/overview)
* [Docker compose](https://docs.docker.com/compose/install/) in case it's not installed together


# Contents of this repository

docker-compose.yml
------------------

The main configuration that describes the used images and their configuration.

docker/php/Dockerfile
---------------------

The detailed sub-config for the php image.

docker/config
-------------

Folder to provide project related configurations.

db
--

Folder to host the database data in order to persist it.

webroot
-------

Project source to work with.

bin
---

Useful scripts to help work. As an example a drush command to do operations inside the running web server instance.


# Run

Depending on your system config you might need `sudo`.

Building the instances from the images:

```bash
docker-compose build
```

Starting the instances:

```bash
docker-compose up
```

Stopping it:

```bash
docker-compose kill
```

To access the site, open: http://localhost:8888


# Caveat

This structure and the details are all demonstrational. If you have general improvements, please send a pull request.
