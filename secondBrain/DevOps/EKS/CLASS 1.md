we have a chalenge with container, it is scalling, we don't have fault tolerent

kubernetes does not know how to launch a container, it just manage container, we have a way in kubernetes , horzentailer scalling, kubernetes has it's own loadbalance, called (svc it is a software base loadbalancer) , in kubernetes we have a way to ask insted of using internal software loadbalance we have config k8s to use other loadbalance developer by some other company , (software or hardware based ) 

In kubernetes word container called pod (it's almost like a container, pod also has some extra feature)

for setup externel loadbalance like (AWS ELB) we need to config driver in k8s for (ELB)


but eks give you pre configure drivers, for all the aws sevices, like ELB , EBS for networking VPC , IAM e.t.c 

the point is can we do it in vanela k8s , but it is very time consuming, that why we use EKS.

================================================

aws config 


aws eks help

ase eks list-cluster --region ap-south-1

we have third party tool called eksctl

eksctl --version

eksctl --help 

eksctl create cluster --name 


what is node group = container always launch in worker node, by default we have 2 worker node in eks , in eks they create a group and name it nodegroup , these nodegroups manage by AUTOSCALLING, service

in one cluster we can have multiple nodegroup, 

eks dont show master node because it fully manage service, 

===============================================

eksctl is only for launcing and configure eks 

eksctl delete clustoer --name 


kubeclt 

s:\\User\\usename\\.kube\\config -> kube config file, it container info and credential of  k8s clustor


kubeclt get nodes

kubeclt 

eksctl create cluster -h

eksctl create cluster --name  --region ap-south-1 --with-oidc --version 1.31 --nodegroup-name lw-ng node-type t2.xlarge
--node-min 3 --nodemax 5 --node-volume-size 40 --ssh-access --instance-name lw-ec2-eks  --asg-sccess 

=================================================

ku









