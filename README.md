# Getting Started

## About

> It is very important for every institution to educate it’s new coming students about the school’s policies and procedures, as well as to engage them into what is going to be their future student life. On_Board helps institutions accomplish just that, by providing an open source and robust platform where you can deploy the most amazing virtual orientations, simple and easy.

## Features

* Custom orientation styling.
* Sections of type video, rich text, and assessments.
* Student invitation tool.
* Admin and Advisor dashboards.
* Email notification system.

## Installation


### Pre-requisites
Before you begin with the installation, please review your system and make sure the following software is installed. 
**This particular guide was designed around an Ubuntu Server configuration.**
* Apache web server
* PHP 7.3+
* MySQL, MariaDB
* composer
* npm
* redis, php-redis
* supervisor *(if running Laravel Horizon)*

### Apache Setup
Open a terminal window and run:
* <code>sudo apt install php libapache2-mod-php php-mbstring php-xmlrpc php-soap php-gd php-xml php-cli php-zip php-bcmath php-tokenizer php-json php-pear apache2</code>
* <code>sudo apt install composer npm redis redis-php supervisor</code>

Enable rewrite
* <code>sudo a2enmod rewrite</code>
* <code>sudo systemctl restart apache2</code>

### Download
Grab the latest version of On_Board from our [website](nboard.app) or from the [Github](https://github.com/elvisblanco1993) repository.
Once downloaded, unzip <code>onboard.zip</code> on your web directory.

### Permissions
Now let's fix make sure the correct folder permissions are set.

Open a terminal window inside the application root directory and run the folling commands.

* <code>sudo chgrp -R www-data . </code>
* <code>sudo chmod -R 775 ./storage</code>


### Install Dependencies
Open a terminal window on the root directory, and type:
* <code>composer install</code>
* <code>npm install</code>

### Environment Setup
Now is time to get your database and email systems connected to On_board.
To do this, first <code>cp .env.example .env</code>, then open **.env** on a code editor.