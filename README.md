# 3.4_Docker-Container
https://docs.google.com/presentation/d/1BH51favR8PCQT766_82vKT9Jhlptf5ZCvg2KoU84LRo/edit?usp=sharing

## Learn to build a node application with docker and deploy to AWS EC2

### Creating a web application using node
- Create Github repository.
- Clone repository locally.
- Run npm init - Initialize a new Node.js project by creating a package.json.
- Run npm install express - Installs the Express framework in your Node.js project.
- Write the code for index.js
- Test your code - node index.js (view the website url on browser)
- Push the source code into Github repository using feature branch and merge to main branch.
- Pull the source code to local main branch.

### Run on local host
- docker build -t <my-node-app>
- docker images
- docker run -dp 8080:8080 <my-node-app>
- docker ps
- curl localhost:8080

### Deploy to AWS EC2
- Setup a EC2 with security group allow custom TCP port 8080.
- sudo su
- yum update -y
- yum install git -y <=Install git
- yum install docker -y <=Install docker
- systemctl start docker <=start docker services
- systemctl status docker <=Check docker status
- git clone <Github repository>
- docker build -t mysampleapp . 
- docker run -d -p 8080:8080 <my-node-app>:latest
- curl http://<public-ip>:8080
