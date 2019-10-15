## Harbor Deployment
This Calm blueprint deploys a 1.9.0 Harbor Server in HTTPS mode with self signed certificates, and optionally installs Notary, Clair, and ChartMuseum.

To use this blueprint, import into a Prism Central running >= Calm 2.7.1.2+, and fill in the credentials and secret variables mentioned below.

##### Credentials
* CENTOS: Enter in an SSH Private Key which will be used to authenticate into the deployed CentOS based Harbor VM

##### Variables
* docker_compose_version: This blueprint has been tested and known to work with 1.24.1. Feel free to modify this value, but there's no guarantee that this blueprint will work on any other version than 1.24.1.
* harbor_version: This blueprint has been tested and known to work with 1.9.0. Feel free to modify this value, but ther
e's no guarantee that this blueprint will work on any other version than 1.9.0.
* postgres_db_password: Enter in any value which will then be set as the internal PostgreSQL Database password.
* harbor_admin_password: Enter in any value which will then be set as the Harbor admin password. This value can later be changed via the Harbor UI.
* install_notary: If set to 'true', Notary (content trust) will be installed.
* install_clair: If set to 'true', Clair (vulnerability scanning) will be installed.
* install_chartmuseum: If set to 'true', ChartMuseum (helm chart repository) will be installed.
