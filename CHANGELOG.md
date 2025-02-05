# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [WebDevOps.io Dockerfile](https://github.com/webdevops/Dockerfile).

## [1.1.0] - 2016-12-14
- Fixed dnsmasq startup
- Removed all logfiles inside containers (using stdout)
- Fixed syslog-ng setup (was complaining about version)
- Fixed some php/hhvm tests
- Improve bin/console
- Add cleanup after container installation
- Add multiple vhost support for dns lookup (VIRTUAL_HOST)

## [1.0.0] - 2016-11-28
- Introduced python based processing script
- Introduced testinfra test suite
- Updated documentation
- Added roundcube to `webdevops/mail-sandbox`
- Update liquibase to 3.5.3

## [0.57.1] - 2016-10-11
- Added webdevops/liquibase:mysql (same as latest) with mysql support
- Added webdevops/liquibase:postgres with postgres support

## [0.57.0] - 2016-10-10
- Removed version numbers in php configuration in apache
- Added liquibase image

## [0.56.1] - 2016-09-12
- Removed geoip database

## [0.56.0] - 2016-09-11
- Fix non caching resource files not be passed to document root in `php-nginx-dev`
- Added update of geoip database for applications (currently testing only)
- Added graphviz and ttf-dejavu for `sphinx`
- Added setting `VIRTUAL_HOST` to internal loopback address via dnsmasq

## [0.55.3] - 2016-07-30
- Moved gpg to base 

## [0.55.2] - 2016-07-30
- Add gpg for php-dev (required by blackfire installation) 

## [0.55.1] - 2016-07-29
- Renamed 99-webdevops.ini to 98-webdevops.ini for PHP-7 images (Bug)

## [0.55.0] - 2016-07-01
- Add docker env vars for XDEBUG and BLACKFIRE
- Added blackfire-agent for php-dev

## [0.54.0] - 2016-06-30
- Update alpine-3 to 3.4
- Fixed webdevops/php:alpine-3
- Fixed webdevops/php:alpine-3-php7
- Added webdevops/cerbot for let's encrypt
- Improved docker graph (image build)
- Added WHITELIST for image building

## [0.53.2] - 2016-06-27
- Added test for `PHP_DEBUGGER` blackfire

## [0.53.1] - 2016-06-27
- Fixed and improved `PHP_DEBUGGER` for php-dev

## [0.53.0] - 2016-06-23
- Added apache-dev and nginx-dev
- Restructed php-*dev provision
- Removed whoami call
- Removed provision from `make all` and `make build` 
- Removed --force from apk-install
- Fixed pecl for alpine images
- Updated documentation and tests 

## [0.52.0] - 2016-06-20
- Added tag centos-7-php56 for php images
- Added POSTFIX_MYNETWORKS and POSTFIX_RELAYHOST environment variables
- Added pysed
- Added PHP_DEBUGGER environment variable for php*dev images
- Fix warnings in vsftp image
- Fix package names in alpine (broken build)
- Updated documentation and tests

## [0.51.0] - 2016-06-16
- Added php module apcu
- Added (disabled) php module blackfire to php-dev and inherit images
- Added apt-transport-https for debian family images
- Added link from /etc/aliases to /etc/postfix/alises for alpine

## [0.50.6] - 2016-06-14
- Switch from dotdeb to sury and install libpcre3 from testing

## [0.50.5] - 2016-06-10
- Added Magallanes deployer for samson-deployment
- Improved documentation

## [0.50.4] - 2016-06-06
- Removed superfluous environment variables for PHP inside nginx
- Added more layout sections to documentation


## [0.50.3] - 2016-06-06
- Added `WEB_PHP_SOCKET` for apache and nginx images, this env variable specifies the host where php-fpm is listening
- Added `WEB_NO_CACHE_PATTERN` to apache and nginx images (regexp of files which should not be cached by browser) for php*-dev images
- Added `make baselayout` for building baselayout.tar (not always needed)
- Added php-fpm clear_env workaround for php-fpm versions which doesn't support it
- Set PHP-FPM ports to public on php*-dev images
- Set mail-sandbox to latest tag (using Ubuntu 16.04)
- Moved environment macros of jinja2 templates to environment.jinja2
- Updated documentation

## [0.50.2] - 2016-05-27
- Fix /opt/docker/bin/service.d/php-fpm.sh using php.d instead of php-fpm.d
- Restructured documentation, Added customization section

## [0.50.1] - 2016-05-24
- Fixed required root rights for entrypoint, provisioning is now only running when entrypoint is entered with root
- Modularized service.d scripts (will include servide.d/$serv.d/*.sh before execution)

## [0.50.0] - 2016-05-23
- Improve image sizes (backported to 0.23.0 due to build issues)
- Improved provisioning system with new python wrapper
- Modularized apache and nginx configuration
- Dockerfile are now generated via jinja2 files
- webdevops/storage is now using busybox
- Latest tag is now ubuntu 16.04
- Set clear_env to no for php-fpm (if possible)
- Added ubuntu 16.04 images (eg. php, hhvm)
- Added webdevops/php-dev webdevops/php-apache-dev webdevops/php-nginx-dev (xdebug and disabled caching for webserver) 
- Added webdevops/varnish
- Added mod_expire for webdevops/apache

## [0.23.0] - 2016-04-03
- Enabled alpine-3-php7 images
- Fixed some smaller issues
- Added TYPO3 packages to sphinx image
- Fixed build system for new docker version (1.11.0)

## [0.22.0] - 2016-04-03
- Introduced base-app for application images
- Added alpine-3 images
- Added sphinx image

## [0.21.6] - 2016-03-25
- Refactored directory layout (container -> docker/, .bin -> bin, testsuite -> test/

## [0.21.5] - 2016-03-24
- Fixed permissions automatically for /tmp if mounted as volume
- Added error checks for samson service script

## [0.21.0] - 2016-03-20
- Improved entrypoint startup time
- Removed entrypoint ansible provisioning if not needed
- Added java-jre and latest npm for samson-deployment


## [0.20.0] - 2016-02-24
- Added sqlite to base images
- Moved WEB_DOCUMENT_ROOT to /app (from /application/code) 
- Improved samson-deployment
