# Create external service 

kubectl apply -f mysql-externalservice

kubectl get service

# Connect to RDS Database using kubectl 

## Note - same step can be done from AWS RDS Console 

kubectl run -it --rm --image=mysql:8.0.35 --restart=Never mysql-client -- mysql -h usermgmtdb.cn2ue0s4c9kv.us-east-1.rds.amazonaws.com -u dbadmin -pdbpassword11

mysql> show schemas;
mysql> create database usermgmt;
mysql> show schemas;
mysql> exit


# deploy all 

kubectl apply -f  foldername 

# List Pods
kubectl get pods

# logs 
kubectl logs -f <pod-name>

# Access application 

kubectl get nodes -o wide
http://<Worker-Node-Public-Ip>:31231/usermgmt/health-status


# Delete all 
kubectl delete -f foldername

# Verify
kubectl get all
