## Linux Task Manager Application with MySQL, Nginx, PHP, and HAProxy
This Calm blueprints deploys a fully functional task manager application.  It utilizes MySQL for the database, Nginx and PHP for the web application, and HAProxy for a load balancer.  It also includes day 2 operations like scale in, scale out, and upgrades.

To use this blueprint, import into a Prism Central running >= Calm 2.5.0.1, and fill in the Credentials and Variables mentioned below.  Once the Calm Application is running, access the Task Manager Application by opening the link provided on the Calm Application Overview page.

##### Credentials
* CENTOS: the private key of an SSH key pair to applied to the VMs that are created

##### Variables
* Database_name: the name of the MySQL database to be used by the application, must be 'homestead'
* INSTANCE_PUBLIC_KEY: the matching public key of the SSH key pair from the credentials section
* Mysql_password: the root password for the MySQL database
* Mysql_user: the username to access MySQL, must be 'root'
