# Nginx, PHP and MySQL stack with Docker 1.9

Clean LEMP stack with docker.

This is a very basic LEMP stack with minimal configuration.

I's a good starting point for docker and playing around with containers on top of it you can try to run your php projects in a containerized manner.

## Requirements

* Docker 1.9 or greater
* Docker compose

## Try it yourself

You can run the containers in your machine by cloning (or download and extract) this repository.

After cloning/extracting open a terminal window and run the commands below:

```bash
 cd /path/to/the/repository/root
 docker-compose --x-networking up -d
```

Browse to `http://localhost` to see the `phpinfo()` page.

If you're using boot2docker or Docker Toolbox you need to browse to the vm ip instead, to find the ip you can do the following:

```bash
 docker-machine active 
 # see the name of the active machine 
 docker-machine ip <name-of-active-machine>
```

You should get an IP e.g. 192.168.99.100. Now browse to it `http://192.168.99.100` and enjoy your phpinfo() page

## A simple exercise

Now that you have everything up and running, let's do some changes to the php configuration.

Browse to `http://localhost/phpwitherror.php` and you will see a php parse error.
 
Now let's edit the php.ini file in config/php/ 

Change the line `display_errors = On` to `display_errors = Off` and save the file. 

The change will prevent php from displaying errors but for our changes to take effect we need to restart our container, let's do that!

In the terminal window run:

```bash
 docker restart container_php
```

Browse again to `http://localhost/phpwitherror.php` and you'll notice that the error is not displayed anymore.

That's it! We've made some changes to the php configuration, quick and easy. 
