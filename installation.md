# Installation

- [Installation](#installation)
    - [Server Requirements](#server-requirements)
    - [Installing IdeaSpace](#installing-ideaspace)
    - [Configuration](#configuration)

<a name="installation"></a>
## Installation

<a name="server-requirements"></a>
### Server Requirements

Make sure your server meets the following requirements:

<div class="content-list" markdown="1">
- PHP >= 5.5.9
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- MySQL database (or Postgres / SQLite / SQL Server)
</div>

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

<a name="configuration"></a>
### Configuration

#### Directory Permissions

After installing IdeaSpace, you may need to configure some permissions. Directories within the `storage` and the `bootstrap/cache` directories should be writable by your web server or IdeaSpace will not run. 

