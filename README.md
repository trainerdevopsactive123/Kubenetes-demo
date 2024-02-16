# Points 

1. Create AWS RDS in private subnet of EKS cluster 
2. EKS nodes are running in Public Subnet
3. Create Security group for AWS RDS - port 3306
4. Create DB subnet group from AWS RDS Console in private subnet 



## Create security group

VPC - Security group - Security group name 
select eks vpc 
Add inbond port - 3306 


##  Create DB subnet group 

AWS RDS - Subnet group - Create DB subnet group - Availability Zones - select the private subnet - create 


## Create RDS 

AWS RDS - Databases - create database - standard create - Mysql - go with default Engine Version - In template use free tier 
In DB instance identifier enter " usermgmtdb " 
In Master username  " dbadmin  " 
In Master password  " dbpassword11 "    # echo "ZGJwYXNzd29yZDEx" | base64 --decode  # base64 


In VPC - select - EKS # same VPC where EKS cluster is deployed 
DB subnet group - created in above step "Create DB subnet group "
Public access - no 
In VPC security group (firewall)  - created in above step   " Create security group " 
create db 




