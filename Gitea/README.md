## Gitea
This Calm blueprint deploys a fully funciton Gitea git server.  It uses MySQL as the backend database, generates self signed certificates for HTTPS, installs Gitea, and does basic Gitea setup, including creating an admin user (gitadmin).

To use this blueprint, import into a Prism Central running >= Calm 2.9.8, and fill in the Credentials and Variables mentioned below.

##### Credentials
* CENTOS: A private key that will allow SSH access to the CentOS VM that runs Gitea and MySQL.

##### Variables
* GITEA_PASSWORD: the password that will be set for the Gitea "gitadmin" user (which is used for the UI and git over HTTPS).
* MYSQL_PASSWORD: the password that will be set for the MySQL "root" user.
