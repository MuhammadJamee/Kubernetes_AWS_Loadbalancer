## This guide is specifically for linux

Step-1 Install utilities

Install these packages 

aws cli 
kubectl 
kustomize
elkctl

Step-2 Configure AWS

Login your user with aws cli

$ aws configure

Enter access key
Enter secret key
Enter region which is 'us-east-2'
Enter formate type 'json'

Step-3 Create cluster

$ make create_cluster

this command will create the cluster and all the necessaries with it using eksctl utility. you can edit the settings and cluster type in cluster.yaml file

Step-4 Enable "Service account"

$ make enable_iam_sa_provider

Step-5 Make cluster-role (RBAC) alb ingress controller - default

$ make create_cluster_role

Step-6 Create IAM policy (its for aws load balancer controller - default)

$ make create_iam_policy

Step-7 Create service account (its for aws load balancer controller - default)

$ make create_iam_policy

Step-8 deploy certificate manager for https requests (optional)

$ make deploy_cert_manager

Step-9 Deploy ingress controller of AWS (default)

$ make deploy_ingress_controller

Step-10 Deploy ingress(it will work as reverse proxy) and applications

$ make deploy_application 

NOTE: aws load-balancer controller and alb ingress controller need to be install to EKS by aws. for more info check aws controller section.


## AWS controllers
https://docs.aws.amazon.com/eks/latest/userguide/aws-load-balancer-controller.html
https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html

## Others
https://www.learncloudnative.com/blog/2020-11-23-multiple-vs-gateway
https://www.youtube.com/watch?v=S8U7A-eGdOs&lc=z22oghm5itzvt5nwq04t1aokgw0wapnirjmrgpjw1i3bbk0h00410

## Install utilities

### kustomize
https://kubectl.docs.kubernetes.io/installation/kustomize/binaries/

curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash

### kubectl
https://kubectl.docs.kubernetes.io/installation/kubectl/binaries/

### aws cli
 $ sudo apt install aws_cli -y


