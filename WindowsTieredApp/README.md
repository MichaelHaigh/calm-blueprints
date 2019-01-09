## Windows Tiered Application with MSSQL and MSIIS
This Calm blueprints deploys a fully functional [BugNET](https://github.com/dubeaud/bugnet) application.  It creates two Windows 2012 R2 server VMs, one for the database tier (MSSQL), and another for the web tier (MSIIS and Web PI).

To use this blueprint, import into a Prism Central running >= Calm 2.5.0.1, and fill in the Credentials and Variables mentioned below.  You must bring your own generalized Windows Server 2012 R2 Disk Image, which will be specialized with an unattended answer file during deployment.  Once the Calm Application is running, access the BugNET Application by opening the link provided on the Calm Application Overview page.

##### Credentials
* WIN_VM_CRED: the Administrator account credentials for the two Windows VMs, which will be applied via Sysprep
* SQL_CRED: the MSSQL credentials, which get applied during MSSQL install

##### Variables
* DbName: The name of the database that is created for the BugNET application to use
* DbUsername: The username of that database
* DbPassword: The password of that database, must conform to typical password requirements (8 characters long, upper, lower, special, number)
