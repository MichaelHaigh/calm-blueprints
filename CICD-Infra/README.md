## CICD Infrastructure
This Calm blueprint deploys the basic infrastructure required to create a CI/CD pipeline:
* **Kubernetes** (Existing machine) - this Service utilizes VM Pre-create eScript tasks to make API calls into Prism Central, to find a Karbon Kubernetes cluster matching the **karbon_cluster_name** variable defined at launch. It also sets the content of the cluster’s kubeconfig as a variable, which will be later applied to the Workstation VM.
* **Gitea** (AHV) - this Service installs Gitea, which is a community managed lightweight code hosting solution. It first installs MySQL, as Gitea requires a backend DB to operate. It then creates self signed certificates, installs the Gitea service, and configures the repo which stores our application code.
* **Jenkins_Master** (AHV) - this Service installs Jenkins, a popular Continuous Integration server. It also trusts Certificate Authority (CA) generated during the Package Install of the **Gitea** Service.
* **Jenkins_Slave** (AHV) - this Service installs a Jenkins Slave, which is used for builds in our Jenkins pipeline. Meaning this is the node that is responsible for building a docker container based on the new application code, publishing tha container to DockerHub, and then deploying the new container to the Kubernetes cluster.
* **Workstation** (AHV) - this Service represents a “developer workstation,” and is where a user can make changes to their application code. It first installs necessary software (like git and kubectl), and then configures the kubeconfig based on the variable set in the **Kubernetes** Service. Finally, it clones the git repo configured in the **Gitea** Service.

To use this blueprint, import into a Prism Central running >= Calm 2.9.7, and fill in the Credentials and Variables mentioned below.

##### Credentials
* CENTOS: A private key that will allow SSH access to the CentOS VMs that run Gitea, Jenkins, and the Workstation.

##### Variables
* karbon_cluster_name: the name of an **already existing** Karbon Kubernetes cluster.
* gitea_password: the password that will be set for the Gitea "gitadmin" user (which is used for the UI and git over HTTPS).
