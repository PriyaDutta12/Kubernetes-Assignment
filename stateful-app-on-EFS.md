#Create namespace

kubectl create namespace ns-eks-assignment


#Create storage
The steps to execute are:  

1. Add RBAC to access EFS
2. Create EFS provisioner  
replace your *EFS-ID* and *EFS-DNS name* in file _create-efs-provisioner.yaml_
3. Create PVCs

The corresponding commands are:  

kubectl apply -f create-rbac.yaml --namespace=ns-eks-assignment
kubectl apply -f create-efs-provisioner.yaml --namespace=ns-eks-assignment
kubectl apply -f create-storage.yaml --namespace=ns-eks-assignment


# Deploy mysql
## Create secret which stores mysql pw, to be injected as env var into container

kubectl create secret generic mysql-pass --from-literal=password=eks-assignment-mysql-pw --namespace=ns-eks-assignment

check:

kubectl get secrets --namespace=ns-eks-assignment


## Launch mysql deployment

kubectl apply -f deploy-mysql.yaml --namespace=ns-eks-assignment

## checks
* persistent volumes
* persistent volume claims
* pods

kubectl get pv --namespace=ns-eks-assignment
kubectl get pvc --namespace=ns-eks-assignment
kubectl get pods -o wide --namespace=ns-eks-assignment


# Deploy wordpress

kubectl apply -f deploy-wordpress.yaml --namespace=ns-eks-assignment


get URL of the app:


Go to AWS console => EC2

------


