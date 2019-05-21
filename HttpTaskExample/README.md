## HTTP Task Example

This is an example blueprint showcasing how to use Calm HTTP Tasks.  Under the **Create** Action of the **PC** Service, the following HTTP Tasks are executed:
* **POST** to list all current subnets, and set two variables which will be used in the following call
* **POST** to create a new subnet with the VLAN tag getting pulled from a runtime Profile Variable, the resulting Subnet UUID is set to a variable to be used in the following two calls
* **GET** to validate that the subnet was created as expected

Under the **Delete** Action of the **PC** Service, the following HTTP Task is executed:
* **DELETE** to delete the subnet that was previously created

To use this blueprint, import into a Prism Central running >= Calm 2.6.0.4, and fill in the Credential mentioned below.

##### Credentials
* **Dummy**: Calm requires at minimum one credential, but for HTTP Tasks the credentials are instead provided directly within the form body. Fill in any value for the "Password" field, as this credential is not used.
* **HTTP Tasks**: Instead, in each of the above **4** HTTP Tasks, in the Basic Authentication section of the form, provide the Prism Central admin password.


