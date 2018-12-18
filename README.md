# PHP for Docker

``php-apache`` contains an apache 2.4 webserver and PHP as module to execute applications.

apache the web root at `/var/www/html/htdocs/` 

* extends [humilit/common](https://github.com/humilit/common)
* extends [humilit/common-php](https://github.com/humilit/common-php)
* base of [humilit/php-apache-debug](https://github.com/humilit/php-apache-debug)

## integrated tools

### apache2-module-enable

enables an apache2 module that's available in `/etc/apache2/modules-available`

### apache2-module-disable

disables an apache2 module that's available in `/etc/apache2/modules-enabled`

## configuration

### ALLOW_ROBOT_INDEXING

Default: ``false``
 
So that deployed containers are not accidentally crawled indexed by bots,
this container provides following default 
 
* ``/robots.txt`` via ``mod_alias``, rejects search engine crawlers 
* Header ``X-Robots-Tag = noindex, nofollow, noarchive, nosnippet, noodp, noimageindex`` via ``mod_headers`` prevents crawlers from descending through site links
* Cache durations max. ``1 minute`` via ``mod_expires``, for short caching during development and pre-production deployments

