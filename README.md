# WiS - Introduction to IT - LAB
## Part 1 - EC2
### Step 1: Getting Started with the AWS Management Console (15 min)
First of all, let's get familiar with AWS management console.
Please follow the instrustions in below tutorial:

https://aws.amazon.com/getting-started/hands-on/getting-started-with-aws-management-console/?ref=gsrchandson

### Step 2: EC2 key pairs (30 min)
To connect to an EC2 instance, you need a key pair. In this step, you will use EC2 console to create a key pair. 

![EC2 key pair](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/ec2-key-pair.png)

1. Read this documentation to understand EC2 key pairs: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html
2. Create a key pair using EC2 console. Please following the steps in "Create a key pair using Amazon EC2": 

   Note:
   - Step 5: Choose RSA as key pair type
   - Step 6: Choose .pem for key file format
   - Step 10: For macOS computer only. You need to run the command in Terminal. If you use Windows, skip this step.

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html
  
3. You shall be able to view your key pairs in your EC2 console. Open CloudShell and type in the following command to describe your key pairs:
   ```
   aws ec2 describe-key-pairs
   ```

### Step 3: Launch an EC2 instance (40 min)
Now, you are ready to launch your first EC2 instance. In this step, you will explore the lifecycle of an EC2 instance and try to connect to it. You will practice with both Windows and Linux instances.

![EC2](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/get-started-diagram.png)

![Instance lifecycle](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/instance_lifecycle.png)

* Windows:
1. Launch a Windows instance from console. Please follow the steps in "Step 1: Launch an instance":

   Note:
   - Step 5: Choose Windows under Quick Start
   - Step 7: Choose your key
   - Step 8: Keep all default settings
   - The launching may take a few minutes. Wait unitl Status Check shows it passed both checks. 

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html

   When the instance is ready, can you find the following information?
   - Instance ID
   - Public IPv4 DNS
   - Instance state
   - Instance type
   - AMI ID
   - AMI Name
   - Security groups
   - Root device type

3. Connect to your Windows instance:

   Note:
   - Please finish all steps in "Prerequisites". For macOS, you can find Microsoft Remote Desktop in Amazon's Self Service.
   - Security group allows traffic from 0.0.0.0/0 for port 3389 if you use default network settings.
   - Follow the steps in "Connect to a Windows instance using RDP and its IPv4 address"

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-rdp.html

4. Stop, Start and reboot your Windows instance. Please follow the steps in "Manually stop and start your instances":
   
   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html

   Question: When the instance is stopped, can you still connect to it?
   
11. Terminate your Windows instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html

* Linux:
1. Launch a Linux instance from console: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html
2. Connect to your Linux instance and upload a file to the instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-to-linux-instance.html
3. Stop, Start and reboot your Linux instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html
4. Terminate your Linux instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html

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


