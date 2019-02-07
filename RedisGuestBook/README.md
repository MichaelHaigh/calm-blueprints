## Era PosgreSQL Database Provisioning
This Calm blueprint deploys a [PHP Redis Guestbook](https://kubernetes.io/docs/tutorials/stateless-application/guestbook/) onto Kubernetes. This is a standard "Getting Started With Kubernetes" stateless application, so if you're just getting started with Calm+Kubernetes, it's a great place to start. 

To use this blueprint, import into a Prism Central running >= Calm 2.6.0, at which point it can be immediately launched, as there are no credentials or variables required.  To access the guestbook, run 'kubectl get svc' to get the port that the 'guest-book-service' is exposed on, and then point your browser at http://<K8S-Node-IP>:port.
