# Udacity Devops-Capstone-Project

## Hello- World CI/CD deployment  


## Project Overview  
 In this project, I applied the skills and knowledge which was developed throughout the Cloud DevOps Nanodegree program. These include:

1)	Working in AWS
2)	Using Jenkins to implement Continuous Integration and Continuous Deployment 
3)	Building pipelines 
4)	Working with Ansible and CloudFormation to deployclusters 
5)	Building Kubernetes clusters 
6)	Building Docker containers in pipelines


## Steps of Project 
- Developing a CI/CD pipeline for microservices applications with rolling deployment.
- Developing Continuous Integration steps such as linting.
- Developing Contiguous Deployment like pushing the built Docker containers to the Docker repository.
- Deploying these Docker containers to a  Kubernetes cluster. 
- Used eksctl to create the Kubernetes cluster.
- Used the Jenkins pipline to deploy my Kubernetes cluster using Cloudformation.

## create Kubernetes cluster using AWS 

```shell
$ eksctl create cluster --name Mostafa_Devops --node-type t2.micro --region us-east-2

$ aws eks update-kubeconfig --name Mostafa_Devops

$ kubectl config use-context arn:aws:eks:us-east-2:653404899093:cluster/Mostafa_Devops

$ kubectl apply -f deploy.yml
```

## Creating Docker and Kubernetes locally 

#### **1-Docker Configuration**
-  Run the project using docker use this command `run_docker.sh` 
-  Upload Docker image is to docker via `upload_docker.sh`
-  Delete Docker image is via  `delete_docker.sh`


#### **2-Kubernetes Configuration**

-  Run the project using kubernetes use this command`run_kubernetes.sh`


## Requirements for running Jenkins Pipeline
## AWS steps
1)Log in to the AWS management console, as a Root user. Find and select the IAM (Identify and Access Management) service.

2) Click on "Group" menu item from the left sidebar. Create a new group and name it "jenkins", and attach the following policies:
  AmazonEC2FullAccess
  AmazonVPCFullAccess
  AmazonS3FullAccess.

3) Create an IAM user




### Install BlueOcean on Jenkins
1. "Blue Ocean" and other required plugins need to be installed. Logged in as an admin, go to the top left, click 'Jenkins', then 'manage Jenkins', and select 'Manage Plugins'.

2. Use the "Available" tab, filter by "Blue Ocean," select the first option ("BlueOcean aggregator") and install without a restart.

3. Filter once again for "pipeline-aws" and install, this time selecting "Download now and install after restart."

4. Once all plugins are installed, Jenkins will restart. If it hasn't restarted, run the following in the VM:
```
sudo systemctl restart jenkins
```
5. Verify everything is working for Blue Ocean by logging in. An "Open Blue Ocean" link should show up in the sidebar. Click it, and it will take you to the "Blue Ocean" screen, where we will have to add a project.

## Additional Steps to compelete the depolyment 
1. install tidy linter using this command `sudo apt-get install -y tidy`
2. install Amazon Web Services SDK and Docker Pipelines plugin
3. Add AWS credentials to jenkins which can be found in the following link : https://www.jenkins.io/doc/book/using/using-credentials/
4. Add docker credentials from to push the image to dockerhub using the following link : https://appfleet.com/blog/building-docker-images-to-docker-hub-using-jenkins-pipelines/
