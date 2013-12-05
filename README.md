# Protobox #

Protobox is the only [Vagrant](http://vagrantup.com) development box you will ever need. A single YAML file controls all configuration and software installed on the box. It was originally based off of [puphpet](https://puphpet.com) configuration but has since diverged to add more functionality onto the box. It also contains automatic installation of applications from composer or git. 

Protobox easily allows you to setup a development environment with PHP, Apache, MySQL, Grunt and quickly switch to developing the same application in PHP, Nginx, Mongodb, Redis. If you need Node, Beakstalkd, or any other package just turn it on in the configuration file and `vagrant up`. 

## Installation ##

	mkdir protobox && cd protobox
    git clone git@github.com:protobox/protobox.git .
    cp data/config/common.yml-dist data/config/common.yml
    vagrant up

Make sure you add an entry to your `/etc/hosts` for any virtualhosts in your `data/config/common.yml` file:

	192.168.5.10    protobox.dev www.protobox.dev

Then pull up `http://protobox.dev` in your browser to see if it is setup correctly.

## Configuration ##

The protobox configuration file is found at `data/config/common.yml`. You can easily install new services by setting `install: 1` under any of the software in the configuration file. 

## Functionality ##

Protobox has built in support for the following functionality:

- **Puppet Infrastructure**: Protobox uses librarian-puppet to manage your puppet module infrastructure. Its all controlled from a single yaml file so you can easily add new module dependencies.   
- **Application Installing**: Set the path to a git repo (public or private) or a composer project and upon vagrant up it will be installed for you. 
- **User Preferences**: Upon boot up your dot files in data/dot will be copied to the virtual machine.
- **SSH Keys**: Place your ssh keys in the data/ssh and reference them from the configuration file to be copied to the virtual machine to easily access any remote servers or github. 
- **SQL Import**: You can add any sql files in data/sql and reference them in the configuration file to be imported upon the bootup of the virtual machine. 
- **Mailcatching**: The mailcatcher package can catch any mail leaving the system for debugging and testing. 
- **Vast Module Selection**: Protobox comes bundled with 15+ of the most common modules that PHP developer use everyday.

## Modules ##

Protobox has built in support for the following modules:

- [Any Distro](http://www.vagrantbox.es/)
- [PHP](http://php.net)
- [Apache](http://httpd.apache.org/)
- [Nginx](http://wiki.nginx.org/Main)
- [Composer](http://getcomposer.org/)
- [XDebug](http://xdebug.org/)
- [Xhprof](http://pecl.php.net/package/xhprof)
- [Mailcatcher](http://mailcatcher.me/)
- [MySQL](http://www.mysql.com/)
- [PostgreSQL](http://www.postgresql.org/)
- [Mongodb](http://www.mongodb.org/)
- [Redis](http://redis.io/)
- [Beanstalkd](http://kr.github.io/beanstalkd/)
- [Ngrok](https://ngrok.com/)
- [Node](http://nodejs.org/)
- [Bower](http://bower.io/)
- [Grunt](http://gruntjs.com/)

## Apps (Coming Soon) ##

Protobox has built in support for installing any of these applications:

- [Wordpress](http://wordpress.org/)
- [Magento](http://magento.com/)
- [Drupal](https://drupal.org/)
- [Laravel](http://laravel.com/)
- [Wardrobe CMS](http://wardrobecms.com/)
- [Lemonstand](http://lemonstand.com/)
- [Symfony](http://symfony.com/)
- [Symfony CMF](http://cmf.symfony.com/)
- [Sylius](http://sylius.org/)
- [Akeneo](http://www.akeneo.com/)
- [Oro CRM](http://www.orocrm.com/)
- [Prestashop](http://www.prestashop.com/)

## License ##

Protobox is licensed under the [MIT license](http://opensource.org/licenses/mit-license.php) and all third-party Puppet Modules are licensed under [Apache License v2.0](http://www.apache.org/licenses/LICENSE-2.0) or [MIT license](http://opensource.org/licenses/mit-license.php).

## Authors ##

Created by [Patrick Heeney](https://github.com/patrickheeney). Original code and concept based on [PuPHPet](https://puphpet.com).
