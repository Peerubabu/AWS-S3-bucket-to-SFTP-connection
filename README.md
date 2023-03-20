# AWS-SFTP-Connection---S3-Bucket
This repo Creates a solution to agencies to upload data from SFTP Connection to S3 buckets on daily or weekly uploads, where file types are CSV, Excel, JSON. 
The file size would be 20KB to 50MB. Due to nature of data, each agency wants to upload 1-24 files in each batch. Agencies are in different geographical locations.
network latency for upload can be an issue. Everyone in each agency will share the same SFTP user you create for that agency.

Following resources will be created by the repo :
•	First, let’s set up the necessary resources in Terraform. We’ll need to create a SFTP server for each agency, as well as S3 bucket to store the upload files. (As of now in this document am trying with only single agency)
•	Next, we’ll need to create an IAM user for each agency to access the S3 bucket. (Created IAM user only for single Agency)
•	Now that we have the necessary resources set up, we can create a code in terraform to facilitate the transfer of files from the SFTP server to the S3 bucket.

Step – 1: Create S3 Bucket in eu-west-1
Step -2: Create SFTP user account and IAM Service role with right permissions.
Step – 3:  Creates SFTP Connection to S3. (Transfer files between SFTP clients and S3).{AWS transfer for SFTP} 
This project uses terrform workspaces.

Terraform commands to run & apply the changes.

#initialize workspace
terraform init -backend-config=backends/dev-env.tf

#create / change workspace
terraform workspace new "dev"
#terraform workspace select "dev"

#plan and apply
terraform plan
terraform apply
