<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a private network in AWS to launch and manage resources.
It’s useful because it gives control over networking and security, keeping resources isolated or internet-connected as needed.

### How I used Amazon VPC in this project

In today’s project, I used Amazon VPC to set up a private network, created a public subnet, added an internet gateway, and configured routes and security so my EC2 instance could be accessed from the internet.

### One thing I didn't expect in this project was...

One thing I didn’t expect in this project was how many layers of security (route tables, ACLs, and security groups) work together before traffic can even reach an EC2 instance.

### This project took me...

This project took me about 1 hour to complete, including setting up the VPC, subnet, internet gateway, route table, security group, and network ACL.

---

## Route tables

A route table is a set of rules that tells network traffic where to go.It decides how resources in your subnets communicate with each other, with other networks, or with the internet.

A subnet becomes public only if its route table has a rule that sends traffic (0.0.0.0/0) to an Internet Gateway (IGW).

Local route only → subnet stays private.

Local + IGW route → subnet can reach the internet.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target:
Destination : the IP address range the traffic wants to reach.
Target : where the traffic should go to get there (e.g., Internet Gateway, local VPC, NAT, etc.).

The new route in my route table had a destination of 0.0.0.0/0 (all IPv4 addresses) and a target of my Internet Gateway (igw-xxxx), which allows traffic from my subnet to reach the internet.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are virtual firewalls in AWS that control inbound and outbound traffic for your resources (like EC2 instances). They decide who can access your resource and what traffic it can send out.

### Inbound vs Outbound rules

Inbound rule : defines what kind of traffic is allowed into your resource (e.g., HTTP for websites, SSH for server access).
My security group’s inbound rules : allow traffic like HTTP (Port 80) so users can access my public website.

Outbound rule :defines what kind of traffic your resource is allowed to send out (e.g., web server requesting data from the internet).
My security group’s outbound rules : allow all outbound traffic so my resources can connect to external services.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are virtual firewalls at the subnet level that control inbound and outbound traffic. They check every data packet against rules before allowing it in or out, acting like traffic cops for your subnet.

### Security groups vs. network ACLs

Security groups work at the resource level and control traffic to individual resources (like EC2 instances).
Network ACLs work at the subnet level and control traffic for all resources inside a subnet.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, network ACLs allow all inbound and all outbound traffic.

By default, a custom network ACL starts with all inbound and outbound traffic denied.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

---

---
