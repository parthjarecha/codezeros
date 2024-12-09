##########################

Task 1: Simple Node JS Application Deployment on Docker container

1. Go to docker-nodejs-sample directory
2. Type below command in terminal to create docker image of the sample Application
docker build -t app .
3. Type below command to run the container from the image created
docker run --name app -p 3000:3000 -d app
4. Open browser and hit this url to check the Application
localhost:3000
5. After checking stop the container, run this command to get the container id of the app image and copy that id.
docker ps
docker stop <container_id>

##########################

Task 2: K8s Deployment

1. Go to kubernetes directory
2. Run below commands to create deploymentes and service  for nginx
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
3. Run this command to check all the deployments, services replicasets.
kubectl get all
4. Open browser and hit this url to check the nginx application
localhost

##########################

Task 3: Resource Provisioning and configuration management through terraform

I am not fimiliar with Ansible, so I have used Terraform end to end to deploy the Node JS application used in Task 1

1. Go to the root directory where main.tf file is located
2. AWS access should be pre configured, I have used the latest terraform version 1.10.0
3. Type below command to initialize the terraform code
terraform init
4. Type below command to check the plan
terraform plan
5. Type below command to create the resources
terraform apply -auto-approve
6. Wait for the resources till creation, copy the public_ip shown at the output 
7. Wait for atleast 5 min, hit the http public ip shared in browser.
8. After checking, run this command to destroy the resources created.
terraform destroy -auto-approve

