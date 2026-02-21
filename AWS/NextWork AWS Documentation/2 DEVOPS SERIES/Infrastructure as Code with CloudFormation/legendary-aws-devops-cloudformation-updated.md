<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Infrastructure as Code with CloudFormation

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-cloudformation-updated)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_bd8b836b)

---

## Introducing Today's Project!

In this project, I will demonstrate how to build a CI/CD pipeline on AWS.
I’m doing this project to learn CI/CD practically, understand deployment automation, and gain real-world DevOps experience

### Key tools and concepts

In this project, I worked with services such as AWS CloudFormation, CodeBuild, CodeDeploy, CodeStar Connections, EC2, S3, IAM, and CodeArtifact to build a complete CI/CD pipeline. Through this, I learned key concepts like Infrastructure as Code, managing resource dependencies with DependsOn, troubleshooting CloudFormation errors and rollbacks, resolving IAM circular dependencies, using parameters to make templates reusable, and understanding how region-specific resources affect deployments.

### Project reflection

This project took me approximately 3–4 hours  to complete. The most challenging part was troubleshooting CloudFormation errors, especially resolving IAM dependency and circular reference issues. The most rewarding part was successfully deploying the CI/CD infrastructure using a reusable CloudFormation template and understanding how all the AWS services worked together end to end.

This project is part six of a series of DevOps projects where I’m building a CI/CD pipeline. I’ll be working on the next project soon, where I’ll continue expanding the pipeline and deepen my understanding of advanced DevOps concepts and AWS services.

---

## Generating a CloudFormation Template

The IaC Generator is an AWS tool that automatically converts existing AWS resources into a CloudFormation template.

 I#t works in three simple steps:

 #Scans your current resources

# Generates an IaC template

Lets you review and reuse it to deploy infrastructure quickly and consistently

A CloudFormation template is a text file (YAML or JSON) that defines AWS infrastructure as code. It tells AWS what resources to create and how they should be configured.

The resources that I could add to my template include EC2 instances, IAM roles, S3 buckets, CodeBuild, CodeDeploy, security groups, and networking components.

The resources I couldn’t add to my template were IAM instance profiles and roles that were already managed by another CloudFormation stack, because the IaC Generator does not allow importing resources that are already controlled by an existing stack to avoid conflicts.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_0495b046)

---

## Template Testing

Before testing my template, I deleted the existing CI/CD resources from my AWS account, because removing them ensures there are no conflicts and allows me to confirm that the CloudFormation template can successfully recreate the infrastructure from scratch.

I tested my template by deploying it using CloudFormation with new resources.
The first deployment resulted in a CREATE_FAILED error due to two issues: a region mismatch caused by a hardcoded CodeStar Connection HostArn pointing to us-west-2 while deploying in ap-south-1, and an IAM dependency issue where CloudFormation tried to attach policies to the CodeBuild service role before the role was fully created. After removing the hardcoded HostArn, the stack was able to proceed correctly.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_f56730fd)

---

## DependsOn

To resolve the error, I added the DependsOn attribute to the IAM policy resources, ensuring that the CodeBuild service role was created first.
The DependsOn attribute means CloudFormation waits for the specified resource to finish creating before starting the dependent resource, preventing timing and dependency errors.

The DependsOn line was added to four IAM managed policies: the CodeBuild base policy, CloudWatch logs policy, CodeConnections policy, and the CodeArtifact consumer policy.
This ensures the CodeBuild service role is created first before any policies are attached.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_f0df8018)

---

## Circular Dependencies

I gave my CloudFormation template another test, but this time I ran into a circular dependency error. This happened because multiple IAM roles, policies, and instance profiles were configured to depend on each other, creating a loop that CloudFormation could not resolve during resource creation.

I fixed my CloudFormation template by removing the IAM policy references from the ManagedPolicyArns section of the CodeBuild IAM role, which eliminated the circular dependency and allowed CloudFormation to create the resources successfully

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_e6fd85ed)

---

## Manual Additions

In a project extension, I manually defined two additional resources in my CloudFormation template:

A CodeBuild Project – to build the application artifacts.

A CodeDeploy Deployment Group – to deploy the application to EC2 instances.

Before saving the template, I replaced all placeholder values with the actual logical resource IDs from my CloudFormation template.
This included updating the references for the CodeBuild service role, S3 bucket, CodeDeploy role, and CodeDeploy application, ensuring that all resources correctly point to existing definitions and the stack can deploy without errors.

Parameters are inputs you provide when deploying a CloudFormation template.
They make the template flexible and reusable, so values like the GitHub repo owner and name can be changed without editing the code.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_1cee0428)

---

## Success!

I could verify all the deployed resources by visiting the Resources tab in the CloudFormation stack, where AWS lists every resource created as part of the deployment along with their status.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-cloudformation-updated_bd8b836b)

---

---
