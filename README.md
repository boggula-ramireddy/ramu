5.wget https://get.jenkins.io/war-stable/2.387.2/jenkins.war
5.qa.wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.55/bin/apache-tomcat-9.0.55.tar.gz
unzip.tar -zvxf apache-tomcat-9.0.55.tar.gz
ln -s /opt/apache-tomcat-9.0.55/bin/startup.sh /usr/local/bin/tomcatup
5.qa.# vi tomcat-users.xml
Add below lines between <tomcat-users> tag
<role rolename="admin-gui"/>
<role rolename="manager-gui"/>
<role rolename="manager-script"/>
<role rolename="manager-jmx"/>
<role rolename="manager-status"/> 
<user username="admin" password="admin" roles="admin-gui,manager-gui,manager-script,manager-jmx,manager-status"/>
<user username="deployer" password="deployer" roles="manager-script"/>
<user username="tomcat" password="s3cret" roles="manager-gui"/>

6.# curl -fsSL https://get.docker.com -o get-docker.sh ( this will download shell script in the machine)
# sh get-docker.sh  ( This will execute the shell script, which will install docker )
docker run --name myjenkins  -p 7070:8080    -d   jenkins/Jenkins

 docker run  --name  mydb  -d  -e MYSQL_ROOT_PASSWORD=ajay007  mysql:5
 docker  exec   -it  mydb  bash

 7.sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
 sudo chmod +x /usr/local/bin/docker-compose
docker-compose  --version docker pull httd
vim docker-compose.yml
---
version: '3'

services:
 mydb:
  image: mysql:5
  environment:
   MYSQL_ROOT_PASSWORD: ajay007

 apache:
  image: httpd
  ports:
   - 6060:8080
  links:
   - mydb:mysql


 php:
  image: php
  links:
   - mydb:mysql
   - apache:tomcat
...
docker-compose up -d
docker ps -a





8.sudo apt-get update
sudo apt-get install docker.io -y
sudousermod -aG docker $USER &&newgrp docker
// For Minikube&Kubectl
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

$ sudo snap install kubectl --classic
$ minikube start --driver=docker
minikube status
kubectl get pods
kubectl get svc
kubectl get svc
minikube service hello-node  

9.
