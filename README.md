# automation-using-terraform
automation_using_terraform_task6
Deploy the WordPress application on Kubernetes and RDS for Storage | AWS | Terraform

Use_Case:- Write an Infrastructure as code using terraform, which automatically deploy the Wordpress application.

On AWS, use RDS service for the relational database for Wordpress application.

Deploy the Wordpress as a container either on top of Minikube or EKS or Fargate service on AWS

The Wordpress application should be accessible from the public world if deployed on AWS or through workstation if deployed on Minikube.

Task Description: I have written Infrastructure as code using terraform, which automatically deploy the Wordpress application. On AWS, I have used RDS service for the relational database for Wordpress application. Then I deployed the Wordpress as a container on top of Minikube, the Wordpress application is accessible to the public world.

Pre-requisite: AWS account

Minikube (Kubernetes) installed: https://kubernetes.io/docs/tasks/tools/install-minikube/

Terraform installed: https://learn.hashicorp.com/tutorials/terraform/install-cli

Kubernetes Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. Kubernetes is an open-source container-orchestration system for automating computer application deployment, scaling, and management. It was originally designed by Google and is now maintained by the Cloud Native Computing Foundation.

A Kubernetes cluster is a set of node machines for running containerized applications. If you’re running Kubernetes, you’re running a cluster. At a minimum, a cluster contains a control plane and one or more compute machines, or nodes. The control plane is responsible for maintaining the desired state of the cluster, such as which applications are running and which container images they use. Nodes actually run the applications and workloads.

For this task, I'll use Minikube, a tool that runs a single-node Kubernetes cluster in a virtual machine on your personal computer.

AWS RDS Amazon Relational Database Service (Amazon RDS) Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security, and compatibility they need. Amazon RDS is available on several database instance types - optimized for memory, performance, or I/O - and provides you with six familiar database engines to choose from, including Amazon Aurora, MySQL, Oracle Database, etc. web service that makes it easier to set up, operate, and scale a relational database in the AWS Cloud. It provides cost-efficient, resizable capacity for an industry-standard relational database and manages common database administration tasks.

We'll configure our Wordpress app deployed on our Minikube cluster to use RDS as its Database.

Minikube is an open-source tool that helps to run Kubernetes on a local computer. Before using minikube we need to start it so here I wrote terraform code to start minikube on my Local Computer.

Let’s start It will launch the Wordpress Application. Wordpress.tf file:-
![6](https://user-images.githubusercontent.com/66985251/92638825-89724500-f2f8-11ea-859b-e28d1e388545.jpg)
![5](https://user-images.githubusercontent.com/66985251/92639086-f5ed4400-f2f8-11ea-94ec-2fcea15f5efc.jpg)
2.It will create the RDS on top of AWS. databasesql.tf file:-
![4](https://user-images.githubusercontent.com/66985251/92639508-888de300-f2f9-11ea-933e-dd1a6f744544.jpg)
3.It will provide the IP to connect to Wordpress. main.tf files:- 
![3](https://user-images.githubusercontent.com/66985251/92639669-ca1e8e00-f2f9-11ea-9a8c-7e1dc0ae51c4.jpg)
After writing the terraform code. We have to run the command:

terraform init

terraform apply --auto-approve
![11](https://user-images.githubusercontent.com/66985251/92639950-2da8bb80-f2fa-11ea-9193-10e955f1553f.jpg)
If you get everything green then you are on the right track and everything works fine. Also, we have deployed WordPress as a container on the top of Minikube.
![10](https://user-images.githubusercontent.com/66985251/92640048-4f09a780-f2fa-11ea-943a-3a8286ed0903.jpg)
Now to get the IP for WordPress. In the command line type:

minikube ip

minikube service list

kubectl get all
![7](https://user-images.githubusercontent.com/66985251/92639788-f2a68800-f2f9-11ea-8adc-f0a403da4a38.jpg)
Now Open minikube-nodes-ip:40000 and proceed with installation wizard:-
![8](https://user-images.githubusercontent.com/66985251/92640209-94c67000-f2fa-11ea-82b7-5110898d9841.jpg)
![1](https://user-images.githubusercontent.com/66985251/92640326-c0495a80-f2fa-11ea-8bcc-8e0a5ab5ee7d.jpg)
![2](https://user-images.githubusercontent.com/66985251/92640389-d7884800-f2fa-11ea-8796-1ae7503c87a0.jpg)
Thanks Alot for Taking Your Time..
