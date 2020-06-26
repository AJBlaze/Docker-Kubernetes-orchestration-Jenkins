## Readme


# General info

  - This project includes the following steps:
        - Containerize the dynmaic website, it is converted to war file 
        - Deploying the containerized application on EKS (kubernetes platform from amazon aws)
        - Integrate the CI/CD pipeline with Kuberneted and using automation tool Jenkins
  - I used eclipse as an IDE to work on this project, indeed you need it(IDE) to open the file and understand it.
  - You can use the link of part 2 mentioned below to see the output of the project.
  - Included in this zip submission is a video demonstrating all the work, and the source code that was developed.
  - index.html in "WebContent", is the dynamic project output
 

# Executables and installation/setup instructions(including references)
 - Eclipse IDE for Java EE Developers  [use this link to download eclipse](https://www.eclipse.org/downloads/packages/release/kepler/sr2/eclipse-ide-java-ee-developers)
 - Visual studio code [use this link for visual studio code](https://code.visualstudio.com/)
 - AWS- EC2, EKS.(https://aws.amazon.com/)
 - Kubernetes (This can be directly installed on the aws)
 - Docker(This can be directly installed on the aws)
 - Jenkins(https://jenkins.io/)
 
# Source code files - all the source codes required to replicate the project are in the zip file. Below files are used for CI/CD and jenkins
 - Dockerfile
 - Deployment.yaml
 - Service.yaml
 - pom.xml


# Steps to repliicate my project
# Most of the steps are done on aws, which is an online web cloud service
- For this part of the project, the first thing to do is setting up docker on your system and then registering on docker hub. After that is done, docker was used to containerize the war file and then to create an image which will be uploaded to docker hub.
- Second part of the project included setting up a Kubernetes cluster on EKS and running an EC2 instance with Jenkins installed on it.
- https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html, here is the link that can be used to get more info on the EKS on aws
- Once the Kubernetes cluster and Jenkins was setup on AWS, Jenkins was used to automate the CICD pipeline. A GitHub repository was set up along with a Webhook to Jenkins which allowed any pushes to the Github repo to automatically trigger a build on Jenkins.
The Jenkins build then works as follows:
1. Creates the war file using Maven commands
2. Pushes the image to docker hub repository.
3. Use Kubectl, Deployment.yaml and Service.yaml to get the latest image from the docker hub registry and push it onto the EKS cluster.

# note

- You'll have to change the git repository url and other urls in the project respectively.

