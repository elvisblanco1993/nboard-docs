# Getting Started

## About

> It is very important for every institution to educate it’s new coming students about the school’s policies and procedures, as well as to engage them into what is going to be their future student life. On_Board helps institutions accomplish just that, by providing an open source and robust platform where you can deploy the most amazing virtual orientations, simple and easy.

## Features

* :heavy_check_mark: Custom orientation styling.
* :heavy_check_mark: Sections of type video, rich text, and assessments.
* :heavy_check_mark: Student invitation tool.
* :heavy_check_mark: Admin and Advisor dashboards.
* :heavy_check_mark: Email notification system.

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
* <code>sudo apt update && sudo apt upgrade -y;</code>
* <code>sudo apt install php libapache2-mod-php php-mbstring php-xmlrpc php-soap php-gd php-xml php-cli php-zip php-bcmath php-tokenizer php-json php-pear apache2;</code>
* <code>sudo apt install composer npm redis php-redis supervisor;</code>

Configure your Virtual Host

```
<VirtualHost *:80>
   ServerName thedomain.com
   ServerAdmin webmaster@thedomain.com
   DocumentRoot /home/elvis/Projects/NBOARD/public

   <Directory /home/elvis/Projects/NBOARD>
       AllowOverride All
   </Directory>
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

```
Enable rewrite
* <code>sudo a2enmod rewrite;</code>
* <code>sudo systemctl restart apache2;</code>

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

#### Database
> This step assumes you have created an empty database for your on_board instance, as well as a secure username and password.

1. On the **.env** file, look for the following code:

    <code>DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=root
    DB_PASSWORD=</code>
    * Then replace the information there with your own database connection.

2. After you have enter all the configuration information, we need to create the database structure.

3. To to that, open a terminal on your project's root directory and run:
    * <code>php artisan migrate</code>
    * <code>php artisan db:seed</code>

#### SMTP
Find the following section on your **.env** file and enter your SMTP configuration settings.
<code>
MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS=null
</code>

#### App Url
Set your app url by editing the <code>APP_URL</code> line on your **.env**