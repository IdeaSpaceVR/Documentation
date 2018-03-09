# Installation

- [Server Requirements](#server-requirements)
- [Installing IdeaSpaceVR](#installing-ideaspace)

<a name="server-requirements"></a>
### Server Requirements

Make sure your server meets the following requirements:

* PHP >= 5.5.9
* OpenSSL PHP Extension
* PDO PHP Extension
* Fileinfo PHP Extension
* Mbstring PHP Extension
* Tokenizer PHP Extension
* GD Library or ImageMagick PHP Extension
* MySQL database (or MariaDB / Postgres)
* Apache web server (or NGINX) with mod_rewrite module enabled
* HTTPS protocol

>Using the HTTPS protocol is strongly recommended. In fact, it is needed if you want to use WebVR in a web browser. 

These PHP extensions are most likely pre-installed by your server hosting provider. In case of doubt, please ask your server administrator or contact your hosting provider. Detailed installation instructions for specific hosting provider can be found in the <a href="https://forum.ideaspacevr.org/category/4/help" target="_blank">IdeaSpaceVR Forum</a>.

<a name="installing-ideaspace"></a>
### Installing IdeaSpaceVR

1. <a href="/download">Download</a> and unzip the IdeaSpaceVR file. 
	>Important: if you copy the files to another directory, do not forget to copy the `.htaccess` file! This file is needed to run IdeaSpaceVR!

2. Create a database for IdeaSpaceVR on your server as well as a database user who has all privileges for accessing and modifying its tables.

3. Upload the IdeaSpaceVR files to the desired location on your web server.
  * If you want to have your IdeaSpaceVR installation in the root of your domain (e.g. `https://www.example.com`), move or upload all contents of the unzipped IdeaSpaceVR directory (excluding the IdeaSpaceVR directory itself) into the root directory of your web server.
  * If you want to have your IdeaSpaceVR installation in its own subdirectory on your website (e.g. `https://www.example.com/vr`), create the `vr` directory on your server and upload the contents of the unzipped IdeaSpaceVR package to the directory via FTP (or SFTP / SCP). 

4. Run the IdeaSpaceVR installation script by accessing the URL in a web browser. This should be the URL where you uploaded the IdeaSpaceVR files.
  * If you installed IdeaSpaceVR in the root directory, you should visit: `https://www.example.com`
  * If you installed IdeaSpaceVR in its own subdirectory called `vr` for example, you should visit: `https://example.com/vr`
  * (If you encounter a 404 Not Found error and you are using Apache2 as a web server, please make sure that the <a href="https://forum.ideaspacevr.org/topic/11/404-not-found-error-during-installation" target="_blank">mod_rewrite module is enabled and configured</a>.)

5. Server Requirements. This page informs you if your server meets the necessary software requirements to run IdeaSpaceVR. Some directories and files have to be writable by the web server and these are tested on this page as well.    

  ![IdeaSpaceVR Installation Server Requirements](/assets/documentation/images/ideaspace-installation-server-requirements.png "IdeaSpaceVR Installation Server Requirements") {.img-responsive}

  Directories within the `storage`, `bootstrap/cache` and `public/assets/user` directories must be writable by your web server. The files `config/database.php` and `config/app.php` must be writable by your web server as well.

6. Database Connection. You have to enter information related to your database. If you do not have this information at hand, please contact your server administrator.

  ![IdeaSpaceVR Installation Database Configuration](/assets/documentation/images/ideaspace-installation-database-config.png "IdeaSpaceVR Installation Database Configuration") {.img-responsive}

  The `db_prefix` parameter is useful for having multiple IdeaSpaceVR installations sharing one database.

7. Admin User Creation. Enter the username, e-mail address and password for the admin user of your installation. You will use the e-mail address and password to log in to IdeaSpaceVR.

  ![IdeaSpace Installation Admin User Creation](/assets/documentation/images/ideaspace-installation-admin-user-creation.png "IdeaSpace Installation Admin User Creation") {.img-responsive}

  After this step you are requested to log in. You can now start with the <a href="/documentation/{{version}}/configuration">configuration</a>.





