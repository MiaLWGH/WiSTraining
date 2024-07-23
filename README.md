# WiS - Introduction to IT - LAB
## Part 1 - EC2
### Step 1: Getting Started with the AWS Management Console (15 min)
First of all, let's get familiar with AWS management console.
Please follow the instrustions in below tutorial:

https://aws.amazon.com/getting-started/hands-on/getting-started-with-aws-management-console/?ref=gsrchandson

### Step 2: EC2 key pairs (30 min)
![EC2 key pair](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/ec2-key-pair.png)

1. Read: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html
2. Create a key pair using console: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html
3. View your key pair in console: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/describe-keys.html

### Step 3: Launch an EC2 instance (40 min)
![EC2](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/get-started-diagram.png)

1. Launch a Windows instance from console: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html
2. Launch a Linux instance from console: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html

![Instance lifecycle](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/instance_lifecycle.png)

3. Stop, start and reboot your Windows and Linux instance respectively: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html
4. Connect to your Windows instance and upload a file to the instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connecting_to_windows_instance.html
5. Connect to your Linux instance and upload a file to the instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-to-linux-instance.html
6. Terminate both instances: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html

### Step 4: Launch an EC2 instance from AWS Systems Manager (20 min)
There are many approaches to launch an EC2 instance. In this step, you will launch an EC2 instance from AWS Systems Manager. 
Please follow the instructions in below tutorial:

https://aws.amazon.com/getting-started/hands-on/remotely-run-commands-ec2-instance-systems-manager/?ref=gsrchandson&id=itprohandson

### Step 5: Linux basics (15 min)
In this step, let's learn some basic Linux commands. 

0. Launch a Linux instance from console. 

1. Collect system and hardward information

(1) Print system information using the command `uname`. Try `uname -s`, `uname -n`, `uname -v`, `uname -r`, `uname -m` and `uname -a`. 

(2) Gather vast information about your hardward components using command `sudo lshw`. To print a summary of your hardware infomration, run `sudo lshw -short`. 

(3) Show information about your CPU architecture using command `lscpu`. 

(4) Print block devices by their assigned name using command `lsblk`. 

(5) Print memory usage by using `free`. 

(6) Print disk usage by using `df -h`. 

3. File system

(1) Using the command line, create a new file called `lunch` using the command `touch lunch`.
Optionally, you can verify that this file has been created by using the command `ls` to list all the files in the current directory.

(2) Write a list of foods such as `burger, salad, and sandwich` to the `lunch` file using the following command:
`echo "burger, salad, and sandwich" > lunch`
Optionally, you can verify this by reading the file using the command `cat lunch`.

(3) Delete the `lunch` file using the command `rm lunch`.

(4) Using the command line, create a new directory called `dinner` using the command `mkdir dinner`.
Verify that this new directory has been created using the command `ls` to list all the files in the current directory.

(5) Create 2 more directories within the `dinner` folder using the command:
`mkdir dinner/entree dinner/dessert`
Verify the beginnings of this hierarchical tree structure using the `ls -R` command.

(6) Create a variety of files within these new folders using the command:
`touch dinner/entree/turkey dinner/entree/fish dinner/dessert/cake dinner/dessert/pudding`
Verify the full hierarchical tree structure using the `ls -R` command.

(7) Delete the dinner directory using the command `rm -r dinner`.

### Step 6: Hello World webserver (30 min)
Now, let's make the EC2 instance that you played with in Step 5 into a simple Hello World webserver. 
The following blog shows how to build the webserver from scratch:

https://medium.com/@rj03012002/deploy-your-first-hello-world-application-on-aws-ec2-instance-e474028964a9

Could you please try to make it work on the running instance?

## Part 2 - Networking
![VPC](https://d1.awsstatic.com/getting-started-guides/vpc-with-nat.7ad78b23ba91be288afdf8a0d836820add439d44.png)
### Step 1: Create a VPC with one public subnet and one private subnet

### Step 2: Create two security groups

### Step 3: Launch an EC2 instance in each subnet

### Step 4: Collect network information and test reachability

### Step 5: Add an Internet Gateway

### Step 6: Add a NAT Gateway


