#Use eksctl to create EKS cluster

Display available options and properties:


eksctl create cluster --help


##Creation

create cluster by using yaml config file:

eksctl create cluster -f eks-assignment.yaml


##Post-install check

eksctl also creates the config file for _kubectl_. This means we can immediately check:

kubectl get nodes

-----
