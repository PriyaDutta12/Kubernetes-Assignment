# Setup Guestbook App

## Redis master
Deploy the master Redis pod and a _service_ on top of it:

kubectl apply -f redis-master.yaml
kubectl get pods
kubectl get services


## Redis slaves
Deploy the Redis slave pods and a _service_ on top of it:

kubectl apply -f redis-slaves.yaml
kubectl get pods
kubectl get services


## Frontend app
Deploy the PHP Frontend pods and a _service_ of type **LoadBalancer** on top of it, to expose the loadbalanced service to the public via ELB:

kubectl apply -f frontend.yaml

Some Checks:

kubectl get pods -o wide 
Kubectl describe node 
Kubectl describe service
Check the AWS Management Console to verify that the ELB creation.

## Access from outside the cluster
Get the public DNS of the frontend service LoadBalancer (ELB)

Copy the name and paste it into your browser.
