# Getting Started

## About

> *ON_BOARD* enables Higher Education institutions to take students orientation to the digital model.

## Features
Check out the latest features [here](https://github.com/elvisblanco1993/on_board/releases/latest)

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

Enable rewrite
* <code>sudo a2enmod rewrite;</code>
* <code>sudo systemctl restart apache2;</code>

### Download
Download the latest version of *on_board* [here](https://github.com/elvisblanco1993/on_board/releases/latest).

Unzip <code>on_board.zip</code> on your root web directory.

### Permissions
Now let's make sure the correct folder permissions are set.

Navigate to *on_board*, and on a terminal window type in the following commands:

* <code>sudo chgrp -R www-data . </code>
* <code>sudo chown -R $USER:www-data storage</code>
* <code>sudo chown -R $USER:www-data bootstrap/cache</code>
* <code>chmod -R 775 ./storage</code>
* <code>chmod -R 775 bootstrap/cache</code>


### Configure your Virtual Host

Create or edit your current Virtual Host file and replace its contents with the following:

```
<VirtualHost *:80>
   ServerName yourdomain.com
   ServerAdmin webmaster@yourdomain.com
   DocumentRoot /your/web/directory/on_board/public

   <Directory /your/web/directory/on_board>
       AllowOverride All
   </Directory>
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

```
Replace */your/web/directory/on_board/public* and */your/web/directory/on_board* with the actual location of your instance folder.

### Install Dependencies
Open a terminal window on the root directory, and type:
* <code>composer install</code>
* <code>npm install</code>

### Enable Storage
* <code>php artisan storage:link</code>

### Environment Setup
Now is time to get your database and email systems connected to On_board.
To do this, first <code>cp .env.example .env</code>, then open **.env** on a code editor.

#### Database
> This step assumes you have created an empty database for your *on_board* instance, as well as a secure username and password.

1. On the **.env** file, look for the following code:

    <code>DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=root
    DB_PASSWORD=</code>
    * Then replace the information there with your own database connection.

After you have enter all the configuration information, we need to create the database structure.

* To do that, open a terminal on your project's root directory and run:
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
Set your app url by editing the <code>APP_URL</code> line on your **.env** file.

### Generate the application keys
* <code>php artisan key:generate</code>

#### Configure supervisor
Supervisor is a tool that ensures all notification queues are properly run without any user interaction.

To configure it please review the [official documentation](https://laravel.com/docs/8.x/queues#supervisor-configuration)

> Alternatively, you can initialize the built-in queue worker with <code>php artisan queue:work</code>

<hr>

#### Have a recommendation?

> Help us improve this documentation [here](https://github.com/elvisblanco1993/nboard-docs/pulls).
