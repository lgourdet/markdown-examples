
![Terraform logo](https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/terraform/terraform.png)

# Terraform
Terraform is an open-source infrastructure as code (IAC) tool used to provision, manage, and automate infrastructure resources. Terraform uses declarative language to define the desired state of infrastructure resources, and then creates or updates them to match that state.

Terraform works with various cloud providers like Amazon Web Services, Microsoft Azure, Google Cloud Platform, and many others, as well as on-premise data centers.

Here are some code examples to give you a better idea of how Terraform works:

## Provider Configuration
Before you start using Terraform to create resources, you need to configure the provider, which is the cloud service you will be using. In this example, we will be using AWS as the provider:

> provider "aws" {  
>   region = "us-east-1"  
> }  


## Resource Configuration
Once you have configured the provider, you can start defining the resources you want to create. In this example, we will create an EC2 instance:

> resource "aws_instance" "example" {  
>   ami           = "ami-0c55b159cbfafe1f0"  
>   instance_type = "t2.micro"  
>   tags = {  
>     Name = "Example Instance"  
>   }  
> }  

In this example, we are creating an EC2 instance using an Amazon Machine Image (AMI) with the ID **"ami-0c55b159cbfafe1f0"** and the instance type **"t2.micro"**. We are also adding a tag to the instance to give it a name.

## Variable Configuration
Terraform allows you to define variables that can be used across your configuration files. This is useful when you want to reuse values across different resources or when you want to make your code more flexible. In this example, we will define a variable for the AMI ID:

> variable "ami_id" {  
>   default = "ami-0c55b159cbfafe1f0"  
> }  

You can then use this variable in your resource configuration:

> resource "aws_instance" "example" {  
>  ami           = var.ami_id  
>  instance_type = "t2.micro"  
>  tags = {  
>    Name = "Example Instance"  
>  }  
> }  

## Output Configuration
Finally, you can define output values that can be used in other Terraform configurations or as inputs for other systems. In this example, we will output the public IP address of the EC2 instance we created:

> output "public_ip" {  
>   value = aws_instance.example.public_ip  
> }  

With this output configuration, you can now use the value of the public IP address in other Terraform configurations or as an input for other systems.

## Terraform code creation steps
1. Identify the infrastructure components: Identify the infrastructure components needed to create your desired infrastructure. This may include resources such as EC2 instances, load balancers, security groups, and more.

2. Define the resources in Terraform code: Define each of the infrastructure components in Terraform code using the appropriate resource types and their corresponding attributes.

3. Configure the resource attributes: Set the appropriate attributes for each resource to configure it as desired. This may include things like instance type, security group rules, tags, and more.

4. Organize your code into modules: Group related resources into modules to make your code easier to manage and reuse. Modules can be organized by function, environment, or any other logical grouping.

5. Use variables to make your code reusable: Use variables to parameterize your code and make it more reusable. Variables can be defined at the module level or the root level of your Terraform configuration.

6. Use data sources to reference existing resources: Use data sources to reference existing resources in your infrastructure, such as an existing VPC or security group.

7. Generate the Terraform configuration: Once your code is written, use Terraform to generate the configuration for your infrastructure. Terraform will generate an execution plan that shows the changes that will be made to your infrastructure.

8. Apply the configuration: Once you have reviewed and approved the execution plan, apply the configuration to your infrastructure using the terraform apply command. This will create or update your infrastructure based on the Terraform code you have written.

## Conclusion
In conclusion, Terraform is a powerful tool for managing infrastructure resources in a declarative and flexible way. With Terraform, you can easily provision, manage, and automate infrastructure resources across various cloud providers and on-premise data centers.


*For more informations go to the [official website](https://www.terraform.io/)*
