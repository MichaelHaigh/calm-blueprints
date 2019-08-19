## Era Server Deployment
This Calm blueprint deploys a 1.1.0.1 Era Server, configures the admin password, registers Era to the underlying Prism Element cluster, and configures default network profiles.

To use this blueprint, import into a Prism Central running >= Calm 2.7+, and fill in the credentials mentioned below.

##### Credentials
* EraAdmin: enter any password of your choice, which will be set as the Era UI Admin password
* pe_creds: enter in the underlying Prism Element's administrator credentials
* EraCLI: enter in an SSH Private key, which allows SSH access to the Era Server
