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

`vim Dockerfile`    **IN THIS PROJECTS I WROTE TWO DOCKER FILE WE CAN USE ONE OF THEM**
`vim index.html`

**build dokcer image & run iamge**

`docker build -t project-image`   ( where -t stand for tag and projec-image is our docker image)

`docker run -d -p 80:80 --name project-container project-image`    (-d is detech mode  -p is port )

**THIS WILL CREATE CONTAINER**


 ### STEP-3 

**in this step we will create repo using ecr in aws**

after carefully creation our repo in ecr we will log in our ecr repo in our docker terminal and for this we will use push command from the ecr repo. 

`for login we should these step`

first we have to create iam role and policies to connect with our ternimal.

in this we give permission **admin role** **AmazonEC2ContainerRegistryFullAccess**

 

### step-4                                            

in this step we will configure aws access in the ternimal

go to ternimal paste aws `access key & and access password`

### step-5 

in  this step we will aunthticate our docker client to our registry

with `push`commands in our ecr repo

##### step-6

in this step we will create load balancer (application load balancer) 

this will help us to distrubuted our traffic across our task .

##### step-7 

in this step we will do task defination and cluster 

for creating task defination role 

we have to create a role of in our IAM

in role in choose esc (elastic service container task)

**permission** `amazone ecstas excustion role and policy`

after carefullly do these step in our IAM 


in the task defination we have to paste our url of ecr-repo (copy from push commands of repo)

after all of these step we will create ecs cluster 

in the creation of cluster 

we will create service in this we will choose ecs-task-def (name of our task def.)

create new target group . 

**with this if we copy the DNS of our load balancer we can access our website with ip address**

for more security we can do ssl configure that will secure our website .


****`thank you`****
