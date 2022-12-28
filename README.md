# Automate Terraform with GitHub Actions

This repo is a companion repo to the [Automate Terraform with GitHub Actions tutorial](https://developer.hashicorp.com/terraform/tutorials/automation/github-actions).

Automate Terraform with GitHub Action 

This project is inspired by this [blog](https://developer.hashicorp.com/terraform/tutorials/automation/github-actions?in=terraform%2Fautomation#aws_secret_access_key)

### Prerequisite:

Create an account in [Terraform cloud](https://app.terraform.io/session).

Create an [AWS account](https://aws.amazon.com/account/) & Then create IAM security authentication and save the secret access key and access key id.

Create a [GitHub account](https://github.com/join).


### Follow these steps to execute this project:
### 1. Setup terraform cloud: 

Go to the Create a new Workspace page and select "API-driven workflow".  Name your workspace gh-actions-demo and click "Create workspace".
![workspace ](https://user-images.githubusercontent.com/115537106/209766151-87679c63-e277-442c-8bb7-9f79cb79ac7e.png)

### 2.  add the following as Environment Variables for your “gh-actions-demo": 

AWS_ACCESS_KEY_ID 

AWS_SECRET_ACCESS_KEY 

Put your access_key_id & secret_access_key in environment variables & & put it in sensitive 
![access key   secret key](https://user-images.githubusercontent.com/115537106/209766280-5412926b-434f-4439-ba88-c42b7257190f.png

### 3. Create API Token: 

go to the Tokens page in your Terraform Cloud User Settings. Click on "Create an API token" and generate an API token named GitHub Actions.

![token](https://user-images.githubusercontent.com/115537106/209768609-132f1349-1da2-4895-9477-4ff733e621e6.png)
 
Copy this token & save somewhere 


### 4.Setup a GitHub repository: 

Forked this repo. 

Go to the settings of the forked repo. Click on the secrets then action click on “new repository action”  

Name: TF_API_TOKEN 

In the secret copy the API token. 

![github secret](https://user-images.githubusercontent.com/115537106/209768698-a281cb61-04b4-42af-afd4-7e351240c403.png)


### Then follow these commands: 

$ git clone https://github.com/YOUR-USER-NAME/learn-terraform-github-actions 

$ cat .github/workflows/terraform.yml 

$ git checkout -b 'update-tfc-backend' 

In the main.tf file put the name of the your organization 

$ git add main.tf 

$ git commit -m 'Point backend to correct TFC org and workspace' 

$ git push 

 

Navigate to your pull request. Your PR will trigger the Terraform Actions workflow. When the workflow completes, it will add a comment with the outcome of each step and a speculative plan. 

You can track the status of the apply job through GitHub Actions 
![github action terraform1](https://user-images.githubusercontent.com/115537106/209768805-cd0e011b-e555-49ed-8685-b54f3b3788b3.png)

Expand the "Terraform Apply" step. Terraform should have created the two resources and displayed the EC2 instance's address. 

![github action terraform](https://user-images.githubusercontent.com/115537106/209768841-83dcd4e0-cf97-4345-80f2-13d0fc8b490e.png)
 

Whatever web address you will get copy this address & run at the terminal with curl command. 

You will get “Hello world” as an output. 

![last output](https://user-images.githubusercontent.com/115537106/209768876-04659e07-1f28-4892-9221-81f1abd6a635.png)

 

 
