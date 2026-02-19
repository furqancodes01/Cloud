<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a secure, isolated virtual network in AWS, and it is useful because it lets you control networking, separate public and private resources, and securely manage your cloud infrastructure.

### How I used Amazon VPC in this project

In today’s project, I used Amazon VPC to create a custom network with public and private subnets, route tables, security groups, and network ACLs, allowing me to securely launch and manage EC2 instances within the VPC.

### One thing I didn't expect in this project was...

One thing I didn’t expect in this project was that the default route table and network ACL are automatically applied to new subnets, so I had to create dedicated ones to truly keep the private subnet isolated.

### This project took me...

This project took me around 1 to 1.5 hours to complete, including setting up the VPC, creating public and private subnets, configuring route tables, security groups, and network ACLs.

---

## Setting Up Direct VM Access

To directly access your EC2 instance means connecting to it remotely (usually via SSH for Linux or RDP for Windows) so you can manage, configure, and run commands on the instance as if you were using it locally.

### SSH is a key method for directly accessing a VM

SSH stands for Secure Shell – a protocol used to securely access and manage remote machines like EC2 instances. 

### To enable direct access, I set up key pairs

A key pair in AWS is a set of security credentials (public key + private key) used to securely access EC2 instances without using a password

A private key's file format means the type of file that stores the private key used to securely access an EC2 instance.

My private key's file format was .pem.

---

## Launching a public server

I had to change my EC2 instance's networking settings by assigning it to the correct subnet, attaching a security group, and configuring its public IP so it could communicate properly within my VPC and be accessible from my local machine.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because it needs tighter security and restricted access, allowing only authorized traffic (like from the public server) while blocking direct access from the internet.

My private server's security group's name is NextWork Private Security Group, and its source is the NextWork server’s security group, which means only the public server can send traffic to the private server, keeping it isolated from the internet.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I used the VPC wizard to quickly create a VPC with public and private subnets, route tables, an internet gateway, security groups, and network ACLs, saving time .

A VPC resource map is a visual representation of all the resources in your VPC, such as subnets, route tables, internet gateways, NAT gateways, security groups, and EC2 instances.

My new VPC has a CIDR block of 10.0.0.0/16. It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPCs are isolated from each other, so overlapping IP ranges don’t cause conflicts unless the VPCs are connected.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: one or two public subnets. This was because the VPC wizard I used only allows creating up to two public subnets by default during setup.

The setup page also offered to create NAT gateways, which are used to allow instances in private subnets to access the internet for updates or downloads while blocking inbound traffic, keeping private resources secure.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-ec2_8ee57662)

---

---
