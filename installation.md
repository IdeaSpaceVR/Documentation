# Installation

- [Server Requirements](#server-requirements)
- [Installing IdeaSpace](#installing-ideaspace)
- [Configuration](#configuration)

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
* MySQL database (or Postgres / SQLite / SQL Server)
* Apache web server (or NGINX)

These PHP extensions are most likely pre-installed by your server hosting provider. In case of doubt, please ask your server administrator or contact your hosting provider. Detailed installation instructions for specific hosting provider can be found in the <a href="https://forum.ideaspacevr.org/category/4/help" target="_blank">IdeaSpace Discussion Forum</a>.

<a name="installing-ideaspace"></a>
### Installing IdeaSpace

1. Download and unzip the IdeaSpace package.

2. Create a database for IdeaSpace on your web server as well as a MySQL (or your preferred database) user who has all privileges for accessing and modifying it.

3. Upload the IdeaSpace files to the desired location on your web server.
  * If you want to have your IdeaSpace installation in the root of your domain (e.g. `http://www.example.com`), move or upload all contents of the unzipped IdeaSpace directory (excluding the IdeaSpace directory itself) into the root directory of your web server.
  * If you want to have your IdeaSpace installation in its own subdirectory on your website (e.g. `http://www.example.com/vr`), create the `vr` directory on your server and upload the contents of the unzipped IdeaSpace package to the directory via FTP (or SFTP / SCP). 

4. Run the IdeaSpace installation script by accessing the URL in a web browser. This should be the URL where you uploaded the IdeaSpace files.
  * If you installed IdeaSpace in the root directory, you should visit: `http://www.example.com`
  * If you installed IdeaSpace in its own subdirectory called `vr` for example, you should visit: `http://example.com/vr`

5. Database Connection. You have to enter information related to your database. If you do not have this information at hand, please contact your server administrator.

  ![IdeaSpace Installation Database Configuration](/assets/documentation/images/ideaspace-installation-database-config.png "IdeaSpace Installation Database Configuration") {.img-responsive}

  The `db_prefix` parameter is needed for multiple IdeaSpace installations sharing one database.

6. Admin User Creation. Enter the username, e-mail address and password for the admin user of your installation. You will use the e-mail address and password to log in to IdeaSpace.

  ![IdeaSpace Installation Admin User Creation](/assets/documentation/images/ideaspace-installation-admin-user-creation.png "IdeaSpace Installation Admin User Creation") {.img-responsive}

  After this step you are requested to log in. That's it!

<a name="configuration"></a>
### Configuration

#### Directory Permissions

After installing IdeaSpace, you may need to configure some permissions. Directories within the `storage` and the `bootstrap/cache` directories should be writable by your web server or IdeaSpace will not run. 

