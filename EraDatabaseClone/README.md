## Era Database Clone
This Calm blueprint allows for the creation and lifecycle management of Era Database Clones.  It is aimed at developers who need to clone production databases for development, troubleshooting, and testing.

To use this blueprint, import into a Prism Central running >= Calm 2.6.0, and fill in the Credentials and Variables mentioned below.

##### Credentials
* era_creds: The admin account credentials for your Era Server.  The DBA should provide these credentials at time of blueprint import, which will be encrypted and securely stored, and will not be available for developers.
* db_server_creds: A private key that will allow SSH access to the Era provisioned Database.  It is recommended to provide a default private key, but left as runtime so a developer can specify their own key if desired.

##### Variables
* source_db_name: This should be left blank, but left as runtime, so a developer can specify the name of the source database at application launch.  If left blank, or an incorrect name is given, the application will intentionally fail early, and provide a list of valid database names for the developer.
* source_snapshot_id: This should be left blank, but left as runtime, so a developer can specify the UUID of the snapshot they wish to use for the database clone.  If left blank, the most recent snapshot will be automatically chosen.  If an incorrect UUID is provided, the application will intentionally fail early, and provide a list of valid snapshot UUIDs for the developer.
* cloned_db_name: This should be left blank, but left as runtime, so a developer can name the database clone.  If left blank, the cloned database will default to \<source-db-name>\_Clone\_\<YYMMDDHHMM>.
* cloned_db_public_key: In conjunction with the "db_server_creds", this allows SSH access to the Cloned DB Server.  It is recommended to add a default matching public key, but leave the field as runtime, so a developer can specify their own key if desired.
* era_ip: The IP address of your Era Server.  This should be configured at the time of blueprint import, and then left alone.

##### Custom Actions Available
* Get Parent Snapshot List: When this action is run, a list of Snapshot times and UUIDs of the clone's parent will be provided.  This is useful when running the **Refresh Clone** action.
* Refresh Clone: When this action is run, the cloned database will be refreshed to a newer snapshot.  Optionally provide a snapshot UUID (which can be gathered from the **Get Parent Snapshot List** action), if left blank, the clone will be refreshed to the most recent snapshot.
