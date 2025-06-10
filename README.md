<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Vijay Pratap Singh Hada  
**Email:** vijaypratapsinghhada9@gmail.com

---

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to install Terraform and configure it, configure aws credentias and upload files in Terraform. The goal is to understand how things work behind the scenes and create S3 Buckets in Terraform 

### Tools and concepts

Services I used were AWS S3, AWS IAM, and AWS CLI. Key concepts I learnt include infrastructure as code, Terraform providers, resources, configuration files, and the Terraform workflow (init, plan, apply).

### Project reflection

This project took me approximately 45 minutes for the hands-on work and another 45 minutes for writing the documentation, totaling about 90 minutes.

I did this project today to help you learn how to use Terraform to create and manage an S3 bucket on AWS.

---

## Introducing Terraform

Terraform is a tool that uses code to create and manage cloud infrastructure across different providers like AWS, Azure, and GCP, making it easier to build and update resources consistently.

Terraform is one of the most popular tools used for infrastructure as code (IaC), which is a way to manage and set up your IT infrastructure using code files instead of doing it manually. This helps build things the same way every time, makes repairs and rebuilding faster, and allows others to create identical copies easily.

Terraform uses configuration files to describe your desired infrastructure. `main.tf` is the main blueprint file where you write the code to define your cloud resources.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in blocks, which helps organize the code better. The advantage of doing this is that each block handles a specific part of your setup, making it easier to read, manage, and change things without affecting the rest of your infrastructure.

### My main.tf configuration has three blocks

The first block indicates that we are using AWS as our cloud provider. The second block provisions an S3 bucket, which is a storage container. The third block manages the public access settings for the S3 bucket, ensuring it is not publicly accessible.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

For my project extension, I visited the official Terraform documentation to learn how to customize S3 buckets. The documentation shows how to configure the bucket, set its properties, and manage interactions with other AWS services.

I chose to customize my bucket by adding a "tags" block with an "Environment" tag set to "Dev". This is because adding tags helps organize and identify resources. When I launch my bucket, I can verify my customization by checking the tags associated with the bucket in the AWS console.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_ffe757cd3)

---

## Terraform commands

I ran `terraform init` to set up my Terraform project. This command downloads necessary plugins like the AWS provider, prepares where Terraform will store its state file (which tracks the current state of my infrastructure), handles any reusable code components (modules), and creates a lock file to ensure consistent versions.

Next, I ran `terraform plan` to see exactly what changes Terraform will make to my infrastructure based on my code. This command shows me what resources will be created, updated, or deleted before anything is actually changed in my cloud environment.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

When I tried to plan my Terraform configuration, I received an error message that says "Error: failed to get shared config profile, myprofile" because Terraform does not have the necessary credentials to access my AWS account and create the resources defined in the configuration.

To resolve my error, first I installed AWS CLI, which is a tool that lets me manage AWS services from my terminal. Instead of using the web console, I can use text commands to interact with AWS, which is needed for Terraform to create resources from my computer.

I set up AWS access keys to give Terraform and the AWS CLI permission to interact with my AWS account. These keys act like a password for programmatic access, allowing Terraform to create and manage resources on my behalf.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_7j8k9l0m)

---

## Lanching the S3 Bucket

The sequence of running terraform init, plan, and apply is crucial because init first sets up the project by getting necessary plugins and preparing the state file. Then, plan shows you exactly what changes will be made before anything happens. Finally, apply carries out those planned changes in your cloud environment.

The sequence of running `terraform init`, `plan`, and `apply` is crucial because `init` first sets up the project by getting necessary plugins and preparing the state file. Then, `plan` shows you exactly what changes will be made before anything happens. Finally, `apply` carries out those planned changes in your cloud environment.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to define the S3 object I want to upload to the bucket. This block tells Terraform which bucket to put the object in, what to name the object within the bucket, and where to find the local file to upload.

We need to run terraform apply again because I've made changes to the Terraform configuration file by adding a new resource block to upload an image. Running apply ensures these changes are put into effect in my AWS environment, creating the new S3 object in my bucket.

To validate that I've updated my configuration successfully, I went to the AWS S3 console, found my bucket, and checked inside to see if the image.png file was uploaded. I then downloaded the file from the console to make sure it was the correct image.

![Image](http://learn.nextwork.org/blissful_yellow_calm_donkey/uploads/aws-devops-terraform1_9o0p1a2s)

---

---
