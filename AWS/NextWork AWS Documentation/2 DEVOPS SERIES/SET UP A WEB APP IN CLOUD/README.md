<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, I will demonstrate how to set up and run a web application on AWS. I’m doing this project to learn how cloud infrastructure, deployment, and basic DevOps workflows work in a real environment.


This project is part one of a series of DevOps projects where I’m building a CI/CD pipeline. I’ll be working on the next project in the coming days as I continue this challenge.

“I did this project because I want to build real-world DevOps and cloud skills and strengthen my portfolio by working with AWS, CI/CD tools, and live server environments.

### Key tools and concepts

In this project, I learned key AWS services and DevOps concepts such as EC2 for running cloud servers, SSH for secure remote access, Apache Maven for building Java applications, and CI/CD basics for deploying and managing applications in the cloud.

### Project reflection

“This project took me approximately a few hours to complete. The most challenging part was configuring SSH and connecting VS Code to my EC2 instance. It was most rewarding to see my Java web application running and being able to edit it on a live cloud server.

One thing I didn’t expect in this project was how much effort was needed to configure secure SSH access and permissions, especially when connecting VS Code to an EC2 instance.

---

## Launching an EC2 instance

### What I did in this step

In this step, I will launch and configure an AWS EC2 instance to act as the server for my web application, because it provides a secure and scalable environment to host, develop, and run the app in the cloud

I started this project by launching an EC2 instance because it provides a cloud-based virtual server where I can host, develop, and run my web application in a secure and scalable environment.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SSH is a secure protocol used to remotely connect to and control a server over the internet. I enabled SSH so that I can safely access and manage my EC2 instance from my local computer.


### Key pairs

A key pair is a set of security credentials made up of a public key and a private key, used to securely connect to an EC2 instance without using a password.

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded a private key file (.pem) to my local computer, which is used to securely connect to my EC2 instance.


---

## Set up VS Code

### What I did in this step

In this step, I will install and set up Visual Studio Code and its terminal to connect to my EC2 instance, because it allows me to write, edit, and manage my web app files directly on the cloud server.

### What is VS Code?

VS Code is a lightweight and powerful code editor developed by Microsoft that is used to write, edit, and manage code. It also includes a built-in terminal and extensions that make development and remote server management easier.

I installed VS Code to write, edit, and manage my web application code and to connect to my EC2 instance through the terminal for deploying and maintaining the app.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is a command-line interface used to communicate with a computer or server by typing commands. The first command I ran for this project was cd C:\Users\furqan\OneDrive\Desktop\DevOps, which navigated me to the folder containing my EC2 key file.”

### Updating file permissions

I also updated my private key’s permissions by using the icacls command in the terminal to restrict access to the .pem file so that only my user account can read and use it

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will connect to my EC2 instance using SSH so that I can access the remote server and start setting up and running my web application.

### Connecting to EC2

To connect to my EC2 instance, I ran the command ssh -i nextwork-keypair.pem ec2-user@ec2-13-203-66-67.ap-south-1.compute.amazonaws.com, which used my private key to securely log into the server.

### This command required an IPv4 address

A server’s IPv4 DNS is a public web address provided by AWS that points to the server’s IPv4 IP address. It allows users and computers to find and connect to the EC2 instance over the internet.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I will install Apache Maven and Amazon Corretto 8 (Java) on my EC2 instance and verify the installations, because these tools are required to build, run, and manage Java-based applications in a DevOps environment.

### Why I'm using Maven

Apache Maven is a build automation and project management tool used for Java applications. It helps download dependencies, compile code, run tests, and package applications in a standardized way.

“Maven is required in this project because it manages the project’s dependencies, builds the application, and prepares it for testing and deployment as part of the CI/CD pipeline.


### Why I'm using Java

Java is a popular, platform-independent programming language used to build applications for web, mobile, and enterprise systems. It runs on a virtual machine, which allows Java programs to work on any operating system.

Java is required in this project because the web application we are building is written in Java, and it needs a Java runtime and compiler to build, run, and deploy the application on the EC2 server.

---

## Create the Application

### What I did in this step

In this step, I will run Maven commands in the terminal to generate a Java web application, because Maven can automatically create the project structure and files needed to build and run the app.

### Creating the Java web app

I generated a Java web app using the command mvn archetype:generate with parameters like groupId, artifactId, and the maven-archetype-webapp template, which created a ready-to-use Java web application project structure.

### Installing Remote - SSH

“I installed the Remote – SSH extension so that I can securely connect VS Code to my EC2 instance and work with my web app’s files as if they were on my local computer.

### SSH configuration details

The configuration file contained the EC2 instance’s IPv4 DNS as the host, the path to my private key file (nextwork-keypair.pem), and the username ec2-user, which allowed VS Code to connect to my EC2 instance using SSH.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code’s file explorer, I could see the files and folders of my EC2 instance, including the nextwork-web-project directory that contains my Java web application and its source files.

Two of the project folders created by Maven are src and webapp, which store the application’s source files and the web pages (such as index.jsp) that make up the Java web application.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I will connect Visual Studio Code to my EC2 instance using a remote SSH extension so that I can view, edit, and manage the Java web application files directly on the cloud server.


### Updating the web app

The index.jsp file is the main web page of the Java web application. It contains code that generates the content users see when they open the website in a browser

I edited index.jsp by opening it in VS Code through the Remote-SSH connection to my EC2 instance and modifying its contents directly in the editor, then saving the file to apply the changes on the server.


![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

In this secret mission, I will edit the index.jsp file directly using the terminal instead of an IDE, because it helps me practice working on remote servers using command-line tools like a real DevOps engineer.


### Terminal vs IDE

An alternative to using IDEs is editing files directly through the command line. To edit index.jsp, I ran the command nano index.jsp in the terminal, which allowed me to modify the file on my EC2 instance.

Compared to using an IDE, editing index.jsp in the terminal felt more manual and less visual, but it was useful for quick changes on a remote server. I’d be more likely to use an IDE when working on larger projects or when I need features like code suggestions and file navigation.

### Verifying my work

To verify my editing work in the terminal, I saved the changes to index.jsp and checked the file contents again. It was possible to see my changes in VS Code right away because both the terminal and VS Code were connected to the same EC2 server and were editing the same files.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-vscode_a3324ad41)

---

---
