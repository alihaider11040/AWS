# AWS Fargate & ECS Fundamentals

## Step-01: Pre-requisite
- Ensure we have a VPC in our region where we are creating the Fargate or ECS clusters.
    - VPC Name: fargate-vpc

## Step-02: ECS Cluster Types & Create a cluster
- We have 3 types of clusters
    - Fargate Cluster (Serverless)
    - ECS EC2 - Linux Cluster
    - ECS EC2 - Windows Cluster
- Create Fargate Cluster
- Create ECS EC2 Linux Cluster
![ECS Cluster Types](/otherfiles/images/01-ECS-Cluster-Types.png)

## Step-03: Cluster Features

<img src="https://github.com/stacksimplify/aws-fargate-ecs-masterclass/blob/master/otherfiles/images/03-ECS-Cluster-Features.png" width="1600" height="500">

## Step-04: Task Definition
- Task Defintion - Introduction
**Task Definition Parameter List**
<img src="https://github.com/stacksimplify/aws-fargate-ecs-masterclass/blob/master/otherfiles/images/02-ECS-TaskDefintion-ParameterList.png" width="2000" height="500">

- Create a simple Task Definition
    - Task Definition: nginx-app1-td        
    - **Docker Image:** stacksimplify/nginxapp1:latest

## Step-05: Service
- Create a simple ECS service using the 
- **Configure Service**
    - Launch Type: Fargate
    - Task Definition: nginx-app1
    - Service Name: nginx-app1-svc
    - Number of Tasks: 1
- **Configure Network**
    - VPC: fargate-vpc
    - Subnets: us-east-1a, ust-east-1b (subnets from both regions)
    - Security Group: Inbound Port 80
    - Auto Assign Public IP: Enabled    
    
## Step-06: Task
- Understand more about a Task
- Create a simple task
- Delete a task from Service **nginx-app1-svc** and wait for 5 minutes, task gets automatically recreated. 