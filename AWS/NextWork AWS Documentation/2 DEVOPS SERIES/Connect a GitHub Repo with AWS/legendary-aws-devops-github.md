<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a GitHub Repo with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-github)

**Author:** Mohammed Furqanuddin  
**Email:** mail2furqan01@gmail.com

---

## Connect a GitHub Repo with AWS

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_dd9d254e)

---

## Introducing Today's Project!

Today, I’m setting up Git and GitHub to store and track my web application’s code. This helps me learn version control, collaboration, and how code changes flow through a CI/CD pipeline.

### Key tools and concepts

Services I used were AWS EC2 for hosting the server and GitHub for storing and managing the source code. Key concepts I learned include Git version control, using repositories and branches, committing and pushing changes, and integrating GitHub into a CI/CD workflow.

### Project reflection

This project took me approximately a few hours to complete. The most challenging part was understanding Git authentication and setting up the GitHub token. It was most rewarding to see my local code successfully pushed and reflected in my GitHub repository.

I did this project because I wanted to learn how to use Git and GitHub in a real DevOps workflow and take another step toward building a complete CI/CD pipeline.

This project is part two of a series of DevOps projects where I’m building a CI/CD pipeline. I’ll be working on the next project soon as I continue progressing through the challenge.

---

## Git and GitHub

Git is a distributed version control system that helps manage and track changes in source code. I installed Git on my EC2 instance by updating the package manager and running sudo yum install git -y

GitHub is a cloud-based platform used to store and manage Git repositories. I’m using GitHub in this project to save my code online, track changes, and collaborate as part of a CI/CD workflow.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_efaadbf7)

---

## My local repository

A Git repository is a storage location where a project’s code and its version history are kept. It tracks all changes made to the code over time, allowing developers to manage, review, and collaborate on the project safely.

git init is a command that initializes a new Git repository in a folder, allowing Git to start tracking files and changes. I ran git init inside my web application project directory to begin version control for the project.

A branch in Git is a separate line of development that allows changes to be made without affecting the main codebase. After running git init, the terminal response showed that a new Git repository was initialized and the default branch was created (usually called master or main)

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was git add ., which adds all modified files to the staging area. A staging area is a place where changes are collected and reviewed before being permanently saved to the repository with a commit.

### git commit

The second command I ran was git commit -m "Updated index.jsp with new content", which saves the staged changes to the local Git repository along with a message describing what was changed.

### git push

The third command I ran was git push -u origin master, which uploads my local commits to the remote GitHub repository. Using -u sets the upstream branch so future pushes can be done with just git push

---

## Authentication

When I pushed my changes to GitHub, Git asked for my credentials because it needed to verify my identity and make sure I have permission to upload code to the remote repository.

### Local Git identity

Git needs my name and email because every commit must be associated with an author. This information helps identify who made changes to the code and allows teams to track, review, and manage contributions over time.

Running git log showed me the history of commits in my repository, including the commit messages, author details, and timestamps, which helped me verify that my changes were successfully committed.


![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

“GitHub authentication failed when I entered my password because GitHub no longer allows password-based authentication for Git operations and requires a Personal Access Token (PAT) instead

“A GitHub token is a secure, generated key used to authenticate access to a GitHub account. I’m using one in this project because GitHub requires tokens instead of passwords to securely push code to a repository.

“I set up a GitHub token by going to my GitHub account settings, navigating to Developer Settings, creating a new Personal Access Token, selecting the required permissions, and using the generated token to authenticate when pushing my code.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I updated the index.jsp file in the nextwork-web-project to see Git working in action. I couldn’t see the changes in my GitHub repository initially because the changes had not been committed and pushed yet.

I finally saw the changes in my GitHub repository after committing my updates locally and pushing the changes to the remote GitHub repository.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_6becb2bc)

---

## Setting up a READMe file

A README file is a document that explains what a project is about, how it works, and how to use it. It helps others understand the purpose and structure of the project when they view the repository.

A README file is a document that describes a project, including its purpose and usage. My README is written in Markdown because it is simple to write and allows text to be formatted clearly on GitHub. Special characters in Markdown, such as # for headings, * or - for bullet points, and ** for bold text, help structure and format the content.


My README file has 6 sections that outline the project overview, tools and technologies used, setup steps, how the application works, key learnings, and next steps in the DevOps challenge.

![Image](http://learn.nextwork.org/grateful_turquoise_kind_teaberry/uploads/aws-devops-github_c94976902)

---

---
