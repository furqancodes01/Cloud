<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Deploy a Web App with CodeDeploy

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codedeploy-updated)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-27)

---

## Introducing Today's Project!

I’m learning AWS CodeDeploy to understand how to automate application deployments in a reliable and safe way. Instead of deploying code manually, CodeDeploy helps release new versions automatically, handle rollbacks if something fails, and make deployments faster, consistent, and stress-free as part of a CI/CD pipeline

### Key tools and concepts

Services I used:
I used AWS services like EC2, CloudFormation, CodeBuild, CodeDeploy, CodeArtifact, S3, IAM, and CodeConnections, along with GitHub.

Key concepts I learned:
I learned CI/CD basics, Infrastructure as Code, automated builds and deployments, dependency management, IAM permissions, artifact storage, rollbacks, and troubleshooting deployment issues in a real-world setup.

### Project reflection

This project took me approximately 3–4 hours to complete. The most challenging part was configuring the deployment environment and troubleshooting build and deployment errors, especially around server setup and permissions. It was most rewarding to see the application successfully deployed and running, confirming that the CI/CD pipeline worked end to end.

This project is part five of a series of DevOps projects where I’m building a CI/CD pipeline. I’ll be working on the next project soon, continuing to build and improve the pipeline step by step as I progress through the challenge.

---

## Deployment Environment

I launched an EC2 instance and a VPC to create a secure and controlled environment where my application can run. The EC2 instance provides the server needed to host the web app, while the VPC allows me to define networking components like subnets and security groups, ensuring proper isolation, security, and connectivity. This setup is required for CodeDeploy to deploy and manage the application on the instance.

Instead of creating the EC2 instance and VPC manually, I used AWS CloudFormation because it automates resource creation. When I need to remove them, I can just delete the CloudFormation stack and everything is cleaned up easily.

The CloudFormation template creates all the basic resources needed to run the application. This includes an EC2 instance to host the app, network resources like a VPC, subnet, route table, and Internet Gateway to provide connectivity, security groups to control access, and IAM roles so the instance can work with services like CodeDeploy. These resources are included to make sure the app runs securely and can be deployed automatically.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-5)

---

## Deployment Scripts

Scripts are small programs that run commands automatically. They help set up and manage the server without doing everything manually. To set up CodeDeploy, I wrote scripts to install required software like Tomcat and Apache, configure the server, and prepare it to run my web application during deployment.

The install_dependencies.sh script installs the software required to run the application. It installs Tomcat and Apache (httpd) and configures Apache to route web traffic to the Tomcat server. This ensures the server has all the necessary dependencies set up before the application is deployed.

The start_server.sh script starts the services needed to run the application. It starts Apache (httpd) and Tomcat, making sure the web server and application server are running so the deployed web app is accessible to users.

The stop_server.sh script safely stops the services running the application. It checks whether Apache (httpd) and Tomcat are running and, if they are, stops them. This ensures the server is cleanly shut down before a new deployment starts, preventing conflicts during the deployment process.

---

## appspec.yml

appspec.yml is a file used by AWS CodeDeploy to manage how an application is deployed. I wrote it to tell CodeDeploy where to place the app files and which scripts to run during deployment.

The key sections are files, which defines where the app is copied, and hooks, which run scripts to install dependencies and start or stop the server.

I updated buildspec.yml to make sure all the files needed for deployment are included in the build artifact. By adding the application WAR file, appspec.yml, and the deployment scripts, CodeDeploy can access everything it needs to deploy the app correctly.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-12)

---

## Setting Up CodeDeploy

A CodeDeploy application is the main container that represents what you want to deploy, such as a web app or service. It acts as a top-level definition for your deployments.

A deployment group defines how and where that application is deployed. It specifies the target servers (like EC2 instances), deployment settings, and configurations such as IAM roles and load balancing.

CodeDeploy needs an IAM role so it has permission to interact with other AWS services during a deployment. To set up a deployment group, the IAM role allows CodeDeploy to access EC2 instances, read build artifacts from S3, run deployment scripts, and manage the deployment process securely.

Tags are helpful for identifying and organizing AWS resources. I used tags to let CodeDeploy easily find and target the correct EC2 instance during deployment. By assigning a specific tag to the EC2 instance, CodeDeploy knows exactly where to deploy the application without manually selecting servers.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-18)

---

## Deployment configurations

The deployment configuration controls how CodeDeploy releases the application to instances. It affects the speed of deployment and how downtime is handled.

I used CodeDeployDefault.AllAtOnce, so the application is deployed to all instances at the same time. This makes the deployment faster and simpler, which works well for a small setup or learning project.

A CodeDeploy Agent is a small service that runs on the EC2 instance. In order to connect CodeDeploy with the server, the agent communicates with AWS CodeDeploy, receives deployment instructions, runs the deployment scripts, and reports the deployment status back to CodeDeploy.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-20)

---

## Success!

A CodeDeploy deployment is the process of deploying a specific version of an application to servers. A deployment group defines where and how the app is deployed, while a deployment is the actual run that pushes the app.

A revision location is where CodeDeploy gets the application files to deploy. It tells CodeDeploy which version of the app to use and where it is stored.

My revision location was an Amazon S3 bucket, which contained the build artifact created by CodeBuild.

To check that the deployment was a success, I visited the public URL of my EC2 instance in a web browser. I saw the web application load successfully, which confirmed that CodeDeploy deployed the application correctly and the server was running as expected.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_val-27)

---

## Disaster Recovery

This means the deployment will fail because the script contains a command that doesn’t exist or isn’t available on the EC2 instance. When CodeDeploy runs the same script during deployment, it will hit a “command not found” error, causing the deployment to fail.

I enabled rollbacks with this deployment, which means that if the deployment fails, CodeDeploy will automatically revert to the previous working version of the application. This helps prevent downtime and ensures the application remains stable even if something goes wrong during deployment.

When my deployment failed, the automatic rollback restored the last stable version of the application because it prevents downtime and keeps the service available. To actually recover from the failure, I’d have to analyze logs, fix the root cause, and redeploy a corrected version. In production environments, automatic rollbacks are essential to minimize impact on users, maintain reliability, and ensure safe, controlled deployments.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-codedeploy-updated_rollback-validation-upload)

---

---
