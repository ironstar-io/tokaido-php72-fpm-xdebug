Introduction
============

This container provides a PHP FPM instance for use in the Tokaido hosting
platform. It is intended to be used alongside the other Tokaido containers.

This is a special container that implements xdebug in the base Tokaido FPM
container. For full configuration options and other values, you should reference
the [original source](https://github.com/tokaido-io/fpm)

## Default Values

You can dynamically change the configuration of my PHP settings by supplying
new values for the following environment varibles:

| Environment Variable        | Set In   | Default Value                    |
|-----------------------------|----------|----------------------------------|
| XDEBUG_REMOTE_ENABLE        | php.ini  | Off                              | 

## Running

If you want to run this container locally (to check it out, debug, or whatever)
you can do so by running:

`docker run -it -u1001 -v /path/to/your/site:/tokaido/site tokaido/fpm-xdebug`

The container will fail if it can't find a Drupal site in `/tokaido/site/docroot`. 
If you're lacking this, you can mock the directory and force the container to
run with:

`docker run -it -u1001 -v /tmp:/tokaido/site/docroot tokaido/fpm-xdebug`