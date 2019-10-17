## Era PosgreSQL Database Provisioning
This Calm blueprint deploys a production grade PostgreSQL database by calling Nutanix Era APIs. A minimum of Era Version 1.1.1 is required.

To use this blueprint, import into a Prism Central running >= Calm 2.7.1.2, and fill in the Credentials and Variables mentioned below.

##### Credentials
* era_creds: the admin account credentials for your Era Server
* db_server_creds: a private key that will allow SSH access to the Era provisioned Database

##### Variables
* era_ip: The IP address of your Era Server
* software_profile: The desired Software Profile of your Postgres DB Server
* compute_profile: The desired Compute Profile of your Postgres DB Server
* network_profile: The desired Network Profile of your Postgres DB Server
* database_parameter: The desired Database Parameters of your Postgres DB
* sla_name: The desired Time Machine SLA of your Posgres DB
* db_name_prefix: The prefix of the name of database (a timestamp will be appended to keep uniqueness within Era)
* db_password: The password for the "postgres" user of the database

##### Custom Actions
* GetSnapshotList: Running this action will provide a list of all snapshots of the database
* TakeSnapshot: Running this action will snapshot the database
