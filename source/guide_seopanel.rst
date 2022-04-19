.. highlight:: console

.. spelling::
    owa

.. author:: Ledn <https://brettspielrat.de/>

.. tag:: lang-php
.. tag:: web
.. tag:: analytics
.. tag:: seo

.. sidebar:: Logo

  .. image:: 
      :align: center

##################
SEO Panel
##################

.. tag_list::

`SEO Panel`_ is an open source web analytics software Platform for SEO Optimazation of your websites.

----

.. note:: For this guide you should be familiar with the basic concepts of

  * :manual:`PHP <lang-php>`
  * :manual:`MySQL <database-mysql>`
  * :manual:`domains <web-domains>`

Prerequisites
=============

We’re using :manual:`PHP <lang-php>` in the stable version 7.2:

.. code-block:: console

 [isabell@stardust ~]$ uberspace tools version show php
 Using 'PHP' version: '7.2'
 [isabell@stardust ~]$

.. include:: includes/my-print-defaults.rst

Your website domain needs to be set up:

.. include:: includes/web-domain-list.rst

Installation
============

Create the database and download the `latest version`_ into the subdirectory ``seopanel`` under your :manual:`DocumentRoot <web-documentroot>`. After that you need to manage some privilegs.

.. code-block:: console

 [isabell@stardust ~]$ mysql -e "CREATE DATABASE ${USER}_seop"
 [isabell@stardust ~]$ cd /var/www/virtual/$USER/html/
 [isabell@stardust html]$ wget https://github.com/seopanel/Seo-Panel/releases/download/4.10.0/seopanel.v.4.10.0.zip
 [isabell@stardust html]$ unzip seopanel.v.4.10.0.zip
 [isabell@stardust html]$ rm seopanel.v.4.10.0.zip
 [isabell@stardust html]$ cd seopanel
 [isabell@stardust seopanel]$ chmod 666 config/sp-config.php
 [isabell@stardust seopanel]$ chmod 777 tmp/

Configuration
=============

Go to isabell.uber.space/seopanel/install/ and follow the steps to finish the installation.

Fill out your configuration settings:
 * Database Host: ``localhost``
 * Database Name: ``isabell_seop``
 * Database User: ``isabell``
 * Database Password: :manual_anchor:`credentials <database-mysql.html#login-credentials>`
 
Before you can go to your finished SEO Panel installation you have to change permissions of ``config/sp-config.php`` and delete the directory ``install`` for security reasons.

 .. code-block:: console

 [isabell@stardust seopanel]$ chmod 644 config/sp-config.php
 [isabell@stardust seopanel]$ rm -r install/
 
 After that you can visit your fresh SEO Panel and login with the following credentials:

 Username: spadmin

 Password: spadmin 
 
Before you start using it you should change the password in settings > my account
 
Updates
=======
.. note:: Check the update feed_ regularly to stay informed about the newest version.

Change the current seo panel directory name or move it to another place, e.g seopanel to seopanel_bak.

.. code-block:: console

 [isabell@stardust html]$ mv -r seopanel to seopanel_bak
 
 Than you can download and unzip the new version in the html directory.
 
 .. code-block:: console
 
    [isabell@stardust html]$ wget https://github.com/seopanel/Seo-Panel/releases/download/x.x.x/seopanel.v.x.x.x.zip
    [isabell@stardust html]$ unzip seopanel.v.x.x.x.zip
    [isabell@stardust html]$ rm seopanel.v.x.x.x.zip

Then you have to overwrite the config/sp-config.php with the config/sp-config-sample.php and modify the following sections of the file with your server and database settings of previous version of seo panel.

.. code-block:: console
 
    [isabell@stardust html]$ cd seopanel 
    [isabell@stardust seopanel]$ mv config/sp-config-sample.php config/sp-config.php
    
     # The web path or url to access seo panel through browser.
define('SP_WEBPATH', 'http://localhost/seopanel');

# DB settings - You can get this info from your web hosting provider.
# The name of the database for seo panel
define('DB_NAME', 'seopanel');

# DB database username
define('DB_USER', 'root');

# DB database password
define('DB_PASSWORD', '');

# DB hostname
define('DB_HOST', 'localhost');

Change the permissions on the tmp directory to be writable by all.
.. code-block:: console
 
    [isabell@stardust seopanel]$ chmod 777 tmp/
    
 8. Using your web browser visit the location you placed Seo Panel with the addition of install/upgrade.php

    e.g. http://www.yourdomain.com/seopanel/install/upgrade.php

9. Follow the steps and fill out all the requested information. 

 a. Remove install directory of seo panel

b. Copy all plugins from "plugins" folder of old seo panel folder to "plugins" folder of new Seo Panel. 

 
 .. author_list::
 
 

 

