<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create a VPC, set up a public subnet, and attach an internet gateway.

### What is Amazon VPC?

Amazon VPC is a private network in AWS.
It’s useful because it lets you control IPs, subnets, routing, and security for your resources.


In today’s project, I used Amazon VPC to create my own private network, divide it into a subnet, and connect it to the internet with an Internet Gateway.

### Personal reflection

This project took me about 40 minutes to complete. 

One thing I didn’t expect in this project was that every AWS account already comes with a default VPC and subnets, so I could launch resources right away without creating one from scratch.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, we’re creating our own Virtual Private Cloud (VPC), which will act as the foundation for all the networking resources we build in AWS.

### How VPCs work

VPC's are our Own Private Network inside AWS where you can run and secure resources like servers,database and Apps.

### Why there is a default VPC in AWS accounts

AWS provides a default VPC in every account so you can quickly launch resources (like EC2 instances) without needing to set up networking from scratch. It ensures you have a ready-to-use network environment with subnets, routing, and internet access.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

An IPv4 CIDR block is a range of IP addresses that you assign to your VPC.
It defines the “address space” your VPC can use for its resources (like EC2 instances or subnets).

---

## Subnets

### What I did in this step

In this step, we’re creating subnets inside our VPC to divide the network into smaller sections. This helps us organize where different resources (like servers, databases, or apps) will live and how they’ll connect.

### Creating and configuring subnets

Subnets are smaller sections of a VPC’s IP range used to organize and connect resources.
In the default VPC, there’s already one subnet per Availability Zone so you can launch resources right away.

### Public vs private subnets

A subnet is public only if it has a route to an Internet Gateway. Without that, it’s private.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 addresses.
This setting makes sure new resources (like EC2 instances) get a public IP, so they can be reached from the internet.

---

## Internet gateways

### What I did in this step

In this step, we’re attaching an Internet Gateway to our VPC, which allows resources in public subnets to send and receive traffic from the internet.

### Setting up internet gateways

Internet gateways connects the VPC and the Internet. The Internet gateway are the key to making applications available on the Internet.

In this step, we’re attaching an Internet Gateway to our VPC, which allows resources in public subnets to send and receive traffic from the internet.


![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

### Exploring CloudShell and CLI

### Debugging my setup

### Comparing CloudShell vs AWS Console

---

---
