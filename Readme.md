# Composer Docker Image
Composer docker image with composer 1.5.2, php 7.1 installed and common used libraries.

Ideal for multi stage builds with dependencies which require one of those packages.

Use: `docker pull koutsoumpos89/composer-php7.1`

Details in the [Dockerhub repository](https://hub.docker.com/r/koutsoumpos89/composer-php7.1/)

## PHP
PHP Version 7.1
`php:7.1-alpine3.4`

## Composer
Composer version 1.5.2

## Installed Packages
`autoconf`, `build-base`, `curl`, `git`, `subversion`, `openssh`, 
`openssl`, `mercurial`, `tini`, `bash`, `freetype-dev`, `libjpeg-turbo-dev`,
`libmcrypt-dev`, `libpng-dev`, `libbz2`, `libstdc++`, `libxslt-dev`, `openldap-dev`,
`make`, `unzip`, `wget`, `bcmath`, `mcrypt`, `zip`, `mbstring`, `pcntl`, `xsl`, `gd`, `ldap`

## Use
## Use
Mount your working directory `-v $(PWD):/app`
```
docker run --rm -v $(PWD):/app koutsoumpos89/composer-php7.1 install
```

With more env variables
```
docker run --rm -v $(PWD):/app -v $($HOME)/.composer:/composer --user $(id -u):$(id -g) koutsoumpos89/composer-php7.1 install --optimize-autoloader --no-interaction --no-progress --no-scripts
```