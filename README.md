# Deploy 

The infra developer at kk corp building network stack using `terraform` for sandbox environment for their developers.

 ![KK Automation: VPC network stack](images/vpc.PNG)


1. ## Pre-requisites
  
   This demo, instructions, scripts and terraform template is designed to be run in `us-west-2`. With few modifications you can run it in other regions as well(_Not covered here_).

   - 🛠 Terraform Installed & Configured
   - 🛠 AWS CLI Installed & Configured 
   - 🛠 Git installed
   

1. ## Setting up the environment

   - Get the terraform code

     ```bash
     git clone https://github.com/krishdd2/terraform-aws-vpc
     cd terraform-aws-vpc
     ```

1. ##  Prepare the sbx environment to run `terraform` code

   
   ```bash
   # You should have terraform pre-installed
   # If you DONT have terraform installed
   wget https://releases.hashicorp.com/terraform/0.14.11/terraform_0.14.11_linux_amd64.zip

   # Make sure you in root user
   unzip terraform_0.13.0_linux_amd64.zip
   sudo mv terraform /usr/local/bin/
   ```

   The very first time you deploy terraform code  you’ll need to run `init` command.                          

   ```bash
   terraform init
   ```
 
1. ## Validate the terraform code
  
   You can validate the code by using below command

   ```bash 
   terraform validate
   ```
1. ## Generate the plan
   After successful validation, you can run generate the plan and review the components or resources generated by the plan.

   ```bash 
   terraform plan 
   OR
   terraform plan -out=tfplan.out
   ```
1. ## Apply/deploy the plan

   If you are good with the plan, next step is apply it, which actually creates the resources. 
    
   ```bash
    terraform apply 
    OR
    terraform apply tfplan.out
   ```
       
1. ##  Conclusion

   Here we have demonstrated how to create vpc and network related resources using terraform.

1. ## CleanUp

   If you want to destroy all the resources created by the terraform, Execute the below command

  
   ```bash
    terraform destroy
    OR 
    terraform plan -destroy -out=tfdestroyplan.out
	terraform apply tfdestroyplan.out
   ```

   This is not an exhaustive list, please carry out other necessary steps as maybe applicable to your needs.

##  Who is using this

This repository aims to show how to use terraform to create base network stack i.e vpc, subnets etc., in aws cloud to Infra developers or devops engineers or admins.

###  Help/Suggestions or Bugs

Thank you for your interest in contributing to our project. Whether it is a bug report, new feature, correction, or additional docu                          mentation or solutions, we greatly value feedback and contributions from our community. [Start here](/issues)



### 📚 References

1. [Terraform Docs: AWS resources VPC][1]
1. [Terraform Docs: AWS resources Subnet][2]



[1]: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc
[2]: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/subnet