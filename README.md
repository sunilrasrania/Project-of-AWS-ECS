# Project-of-AWS-ECS
IN THIS PROJECTS WE WILL DEPLOY WEB APPLICCATION TO AWS ECS 

_**DEPLOY AN APPLICATION TO AWS ECS**_

In this project we deploy a application to Aws Ecs with the help of Aws ec2 | docker | FARGATE  |  IAM |  Load balancer | AWS ECR

### STEP-1 
 
IN THIS 1 STEP WE WILL LAUNCH A EC2 AND INSTALL DOCKER IN IT 

_install docker_

` sudo apt-get docker.io` 

`docker --version `   this command tell us docker version

`systemctl start docker`

`system status docker`

### STEP-2 

in this step we will build a docker image and containerized our application in it 

**go to terminol of our vm**

_create a directory in your machine_

`mkdir project`  (where project is our direc)

_go to this direc._

`cd project`

**create a Dockerfile & and index.html**

`vim Dockerfile`
`vim index.html`

**build dokcer image & run iamge**

`docker build -t project-image`   ( where -t stand for tag and projec-image is our docker image)

`docker run -d -p 80:80 --name project-container project-image`    (-d is detech mode  -p is port )

