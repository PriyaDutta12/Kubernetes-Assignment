Click through AWS console to create EFS
login to AWS console and search for service _EFS_   

*specify the security group of your EC2-worker-nodes, to be applied to EFS as well*

# add amazon-efs-utils
install the package *amazon-efs-utils* on all worker nodes

ssh -i <<EKS-Assignment.pem>> ec2-user@<<ec2-workernode>> "sudo yum install -y amazon-efs-utils"
