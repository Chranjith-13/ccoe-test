**Why Terraform?**

Terraform is a tool we use to deploy cloud infrastructure. This infrastructure can be as simple as a single computer in the cloud or as complex as hundreds of machines spinning up on demand for high-performance computing.

**Prerequisites**

Before running any commands for this example, you should install a few things:

-   [Terraform](https://www.terraform.io/downloads.html)
-   [AWS CLI](https://aws.amazon.com/cli/)

Once we are done with the pre requisites, we can then clone this repo by using below link:

```
https://github.com/Chranjith-13/ccoe-test.git

```
Once we are ready with the code, we can create a 3 Tier Architecture by following the below steps


**Command: Plan**

The  `terraform plan`  command creates and shows Terraform's execution plan. If we have not deployed anything yet, this will show all the resources Terraform plans to deploy. If you have deployed some resources, this plan will show what Terraform needs to deploy or change to get to the new configuration. If you have deployed everything, the plan will indicate that everything is up-to-date.

To look at the execution plan, run:

```
cd ccoe-test/
terraform init
terraform plan --var-file=your-variable file name

```

**Command: Apply**

The  `terraform apply`  command applies the changes to get to the desired configuration state. This behaviour is similar to the plan command. Every time you run  `terraform apply`, the plan will be displayed before prompting you to accept the actions.

To deploy the configuration, run:

```
cd ccoe-test/
terraform apply --var-file=your-variables file

```
**The code does the following:**

1.  Creates a VPC with the CIDR block provided in the region you want.
2.  Creates subnets for each layer.
3.  Creates an IGW and NAT gateway.
4.  Creates Route tables.
5.  Creates a RDS instance.
6.  Configures security group for Web layer.
7.  EC2 instances for webservers.
8.  Application load balancer.


**Next Steps**

If you want to connect to this EC2 instance and other resources, there are two options:

1.  Connect to it through the EC2 console or using AWS CLI validate the resources.

**Finally Tear-Down**

When you are ready to tear down the resources which we created earlier run:

```
terraform destroy --var-file=variable file name

```

and type  `yes`  when prompted.

If we want to skip the prompt, we can use --auto-approve tag for both apply and destroy commands
