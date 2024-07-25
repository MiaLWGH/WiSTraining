# WiS - Introduction to IT - LAB
## Part 1 - EC2
### Step 1: Getting Started with the AWS Management Console 
First of all, let's get familiar with AWS management console.
Please follow the instrustions in below tutorial:

https://aws.amazon.com/getting-started/hands-on/getting-started-with-aws-management-console/?ref=gsrchandson

### Step 2: EC2 key pairs 
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

### Step 3: Launch an EC2 instance 
Now, you are ready to launch your first EC2 instance. In this step, you will explore the lifecycle of an EC2 instance and try to connect to it. You will practice with both Windows and Linux instances.

![EC2](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/get-started-diagram.png)

![Instance lifecycle](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/instance_lifecycle.png)

#### Windows:
1. Launch a Windows instance from console. Please follow the steps in "Step 1: Launch an instance":

   Note:
   - Step 5: Choose Windows under Quick Start
   - Step 7: Choose your key
   - Step 8: Keep all default settings
   - The launching may take a few minutes. Wait unitl Status Check shows it passed both checks. 

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html

   When the instance is ready, can you find the following information? You can take a note of them. 
   - Instance ID
   - Public IPv4 DNS
   - Instance state
   - Instance type
   - AMI ID
   - AMI Name
   - Security groups
   - Root device type

2. Connect to your Windows instance:

   Note:
   - Please finish all steps in "Prerequisites". For macOS, you can find Microsoft Remote Desktop in Amazon's Self Service.
   - If you use default network settings, security group already allows traffic from 0.0.0.0/0 for port 3389.
   - Follow the steps in "Connect to a Windows instance using RDP and its IPv4 address"

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-rdp.html

3. Stop, Start and Reboot your Windows instance. Please follow the steps in "Manually stop and start your instances":
   
   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html
   
4. Terminate your Windows instance: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html

#### Linux:
1. Launch a Linux instance from console. Please follow the steps in "Step 1: Launch an instance":

   Note:
   - Step 5: Choose Amazon Linux under Quick Start
   - Step 7: Choose your key
   - Step 8: Keep all default settings
   - The launching may take a few minutes. Wait unitl Status Check shows it passed both checks. 

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html

   When the instance is ready, can you find the following information? You can take a note of them. 
   - Instance ID
   - Public IPv4 DNS
   - Instance state
   - Instance type
   - AMI ID
   - AMI Name
   - Security groups
   - Root device type
   
2. Connect to your Linux instance. 

   Read through the following documentation and make sure to set the permissions of your private key correctly:
   
   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-to-linux-instance.html

   For macOS user:

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-linux-inst-ssh.html

   Note:
   - Tranferring file using scp command is optional. 

   For Windows user:

   https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect-linux-inst-from-windows.html

   Note:
   - Follow section "Connect to your Linux instance from Windows with OpenSSH"

3. Reboot, Stop and Start your Linux instance.

   Questions:
   - After stop and start operations, can you still connect to the instance? Is there anything changed? How to reconnect?
      - Hint: pay attention to the "Public IPv4 DNS".

4. For Linux instance, there is a short cut to connect to it by using EC2 Instance Connect: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-tutorial.html#eic-tut1-task4

5. Terminate your Linux instance.
   
### Step 4: Launch an EC2 instance from AWS Systems Manager
There are many approaches to launch an EC2 instance and work on it. In this step, you will launch an EC2 instance from AWS Systems Manager. 
Please follow the instructions in below tutorial:

Note: 
- Step 4.e: Use following command:
```
sudo yum -y update
```

https://aws.amazon.com/getting-started/hands-on/remotely-run-commands-ec2-instance-systems-manager/?ref=gsrchandson&id=itprohandson

### Step 5: Linux basics
In this step, let's learn some basic Linux commands. 

1. Launch a Linux instance from console and connect to it. 

2. Collect system and hardward information:

   (1) Print system information using the command `uname`. View your network hostname using `uname -n` or `hostname`.

   (2) Print your username using the command `whoami`. 

   (3) Show information about your CPU architecture using command `lscpu`. 

   (4) Print memory usage by using `free`. 

   (5) Print disk usage by using `df -h`. 

3. File system

   (1) Print the current working directory using the command `pwd`.

   (2) Create a new file called "lunch" using the command `touch lunch`. 

   (3) Verify this file has been created by using the command `ls` to list all the files in the current directory.

   (4) Write a list of foods such as "burger, salad, and sandwich" to the "lunch" file using the following command:
   ```
   echo "burger, salad, and sandwich" > lunch
   ```
   (5) Verify this by reading the file using the command `cat lunch`.

   (6) Delete the "lunch" file using the command `rm lunch`.

   (7) Create a new directory called "dinner" using the command `mkdir dinner`. Verify this new directory has been created using the command `ls` to list all the files in the current directory.

   (8) Create 2 more directories within the "dinner" folder using the command:
   ```
   mkdir dinner/entree dinner/dessert
   ```
   Verify the beginnings of this hierarchical tree structure using the `ls -R` command.

   (9) Create a variety of files within these new folders using the command:
   ```
   touch dinner/entree/turkey dinner/entree/fish dinner/dessert/cake dinner/dessert/pudding
   ```
   Verify the full hierarchical tree structure using the `ls -R` command.

   (10) Navigate into directory "dinner" using the command `cd dinnner`. Run `ls` to check the directories. Then, navigate into directory "dessert". 

   (11) Create a new file named "icecream" using command `nano icecream`. Please note that 'nano' is a user-friendly file editor. The command will open up a space where you can immediately start typing to edit file "icecream". Add whatever text you like. To save your written text, press 'CTRL + X', 'Y', and then 'ENTER'. This returns you to the shell with a newly saved "icecream" file. Verify the file content using the command `cat icecream`. 

   (12) Copy file "icecream" to the "~/dinner/entree/" directory using the command:
   ```
   cp icecream ~/dinner/entree/icecream
   ```

   (13) Navigate to previous directory using the command `cd ..`. Optionally, you can go back to home directory using the command `cd` or `cd ~`. Verify the file "icecream" is copied to directory "entree" using the command `ls -R`. 

   (14) Delete the dinner directory using the command `rm -r dinner`.

Some good Linux references for beginners:

[1] https://ubuntu.com/tutorials/command-line-for-beginners#8-hidden-files

[2] https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-basics#the-filesystem-hierarchy-standard

### Step 6: Hello World webserver
Now, let's make the EC2 instance that you played with in Step 5 into your first webserver. 

1. We are using an Apache server in this tutorial so for that we need to install httpd to run apache server. 'httpd' is Produced by Apache Foundation and it is a piece of software that listens for network requests and responds to them. Run the following commands on your instance:
```
sudo su
yum update -y
yum install httpd -y
```

2. Start and enable the httpd service:
```
systemctl start httpd
systemctl enable httpd
```

3. This command will create a directory /var/www/html. It is the default root folder of the web server. Before creating our HTML file first we need to change the ownership of this folder:
```
chown -R $USER /var/www/html
```

4. Now enter your content in /var/www/html/index.html:
```
echo "<h1>Hello World</h1>" > /var/www/html/index.html
```

5. Next, we need to make a change to the security group to allow the HTTP traffic from your laptop to go to the instance via port 80. A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. Go back to EC2 console and find the security group of your instance.
   - Click on the security group ID, which will lead you to the security group details page.
   - Click on button 'Edit inbound rules'.
   - Click on button 'Add rule'.
   - Choose 'HTTP' for 'Type', 'Anywhere-IPv4' for 'Source'.
   - Click 'Save rules'. 

6. Copy the 'Public IPv4 DNS' of your instance, and type `http://Public-IPv4-DNS-of-your-instance` in your broswer. You shall be able to see:

   ![example](https://github.com/MiaLWGH/WiSTraining/blob/main/Screenshot1.png?raw=true)

   Well done! You have deployed your first hello world web server on your EC2 instance!

7. Next, let's make more fun by customizing the website as you like :)

   In previous steps, we have learned how to edit files in Linux. Let's make some some changes to the 'index.html' file.

   (1) Read the file:
   ```
   cat /var/www/html/index.html
   ```
   You shall see only one line for now, which is a heading with `<h1>` tag. 

   (2) Edit the file to add a subheading and a paragraph on your website:
   ```
   nano /var/www/html/index.html
   ```
   In the space, let's add a subheading and a paragraph with `<h2>` and `<p>` tags. For example:
   ```
   <h1>Hello World</h1>
   <h2>About Me</h2>
   <p>Welcome to my website! My name is Mia. This is my first website!</p>
   ```
   You can edit the contents to anything you like. To save your written text, press 'CTRL + X', 'Y', and then 'ENTER'.

   (3) Refresh your website, do you see the updates?

   (4) Edit the index.html file again to add an image and a link with `<img>` and `<a>` tags. For example:
   ```
   <h1>Hello World</h1>
   <h2>About Me</h2>
   <p>Welcome to my website! My name is Mia. This is my first website!</p>
   <img src="https://a0.awsstatic.com/libra-css/images/logos/aws_logo_smile_1200x630.png" width="400px"/>
   <p>Below is AWS website</p>
   <a href="https://aws.amazon.com/">Link</a>
   ```
   To replace the image, you need to change the value for 'src'. To change the image size, please try to change the value of 'width'. To change the link, please change the value of 'href'. After saving the changes, refresh your website to check the updates.

   My website is like below:

   ![screenshot](https://github.com/MiaLWGH/WiSTraining/blob/main/Screenshot%202024-07-25%20at%2021-23-35%20.png?raw=true)

**Show us your creative website! Have fun!**

References:

[1] https://medium.com/@rj03012002/deploy-your-first-hello-world-application-on-aws-ec2-instance-e474028964a9

[2] https://www.w3schools.com/html/html_basic.asp

> [!NOTE]
> After you finish all above steps, please terminate your instance.


## Part 2 - Networking Basics

In this part of the lab, we are going to launch two EC2 instances into the same VPC with Linux, and get familiar with some useful networking commands.

### Step 0: Get to know your default VPC

1. First of all, let's get to know how VPC works. Please read through the following documentation:

   https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html

2. Go to VPC console, can you find the following information for your default VPC?
   - VPC ID
   - IPv4 CIDR
   - Main route table and routes in it

3. How many subnets do you have in your default VPC?
   - Can you find the subnet IDs?
   - What is the difference in their IPv4 CIDR?
   - Can you find the route table? What are the routes?

### Step 1: Launch two EC2 instances in your default VPC

1. Launch two Linux instances in your default VPC (You do not need to change anything in network settings, just pay attention to the VPC ID). Please name your instances with "server1" and "server2". Make sure to select your key pair. 

   If you forget how to launch an EC2 instance, please refer to Step 3 in Part 1.

   Note: By default, a new security group will be created when you launch a new instance. So your two instances should have different security groups. 

3. Open two terminals on your laptop and SSH to both instances. 

### Step 2: Check hostname and test reachability

1. Print the instance IP address using the command `hostname -I` on both instances. For example, I have the following IPs:
   ```
   # server1
   [ec2-user@ip-172-31-14-165 ~]$ hostname -I
   172.31.14.165

   # server2
   [ec2-user@ip-172-31-0-41 ~]$ hostname -I
   172.31.0.41
   ```
> [!NOTE]
> In the following lab, I use above IPs as examples. Please replace the IP addresses by yours in commands. 

2. Command 'ping' is used to test the reachability of a host on an IP network. On server1, try to "ping" server 2. For example, the command will be like:
   ```
   ping -c 5 172.31.0.41
   ```
   You need to replace the IP address by the IP address of your server2. The '-c 5' means 5 counts of results. Can you do the same on server2 to ping server1?

3. As the subnets are public subnets, you can also ping a website directly. On either of your server, run command `ping google.com -c 5`. Do you see any difference in the results?

4. Nslookup (stands for “Name Server Lookup”) is a useful command for getting information from the DNS server. You can find the IP address of 'google.com' using command:
   ```
   nslookup google.com
   ```
   You shall be able to find the IP address under 'Non-authoritative answer:'.

5. Nslookup can also perform a reverse DNS lookup. Try the command with the IP address of your server2. For example:
   ```
   nslookup 172.31.0.41
   ```

6. In networking, understanding the path that data packets take from one point to another is crucial for diagnosing and troubleshooting connectivity issues. Traceroute is a command-line tool used in Linux to track the path that data takes from your computer to a specified destination. It shows you each "hop" that the data packet makes along its journey. This includes the different servers or devices it passes through, and how long each step takes. Try command:
   ```
   traceroute google.com
   ```
   Do you see the IP address you found in 4. in the traceroute results?

### Step 3: Telnet and Packet Capture
In this step, we are going to use 'telnet' command to check if port 22 (SSH) is responsive at the other machine. At the same time, we will use 'tcpdump' command to capture the packets, which will reveal more secrets in networking. 

1. Install telnet on both instances:
```
sudo yum install telnet -y
```

2. Telnet to port 22 from server1 to server2. For example:
```
telnet 172.31.12.143 22
```
You shall be able to see the following result if it works:
```
[ec2-user@ip-172-31-14-165 ~]$ telnet 172.31.0.41 22
Trying 172.31.0.41...
Connected to 172.31.0.41.
Escape character is '^]'.
SSH-2.0-OpenSSH_8.7
```
You can get out from the command by pressing 'ENTER'. 

3. On server2, run the following 'tcpdump' command to capture packets. For example:
```
sudo tcpdump -A host 172.31.14.165
```
Then switch to server1 and run the telnet command. For example:
```
telnet 172.31.0.41 22
```
Observe the terminal of server2, you shall be able to see some packages like below:
```
[ec2-user@ip-172-31-0-41 ~]$ sudo tcpdump -A host 172.31.14.165
dropped privs to tcpdump
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on enX0, link-type EN10MB (Ethernet), snapshot length 262144 bytes
14:38:56.294578 IP ip-172-31-14-165.ap-southeast-2.compute.internal.47218 > ip-172-31-0-41.ap-southeast-2.compute.internal.ssh: Flags [S], seq 4044145633, win 62727, options [mss 8961,sackOK,TS val 2834667800 ecr 0,nop,wscale 7], length 0
E..<#.@...p........).r....................#....
............
14:38:56.294618 ARP, Request who-has ip-172-31-14-165.ap-southeast-2.compute.internal tell ip-172-31-0-41.ap-southeast-2.compute.internal, length 28
.........*`......)..........
14:38:56.294718 ARP, Reply ip-172-31-14-165.ap-southeast-2.compute.internal is-at 02:46:2c:0f:44:05 (oui Unknown), length 42
.........F,.D......*`......)..............
14:38:56.294725 IP ip-172-31-0-41.ap-southeast-2.compute.internal.ssh > ip-172-31-14-165.ap-southeast-2.compute.internal.47218: Flags [S.], seq 1607214832, ack 4044145634, win 62643, options [mss 8961,sackOK,TS val 1392008710 ecr 2834667800,nop,wscale 7], length 0
E..<..@........).......r_.&.........g;....#....
R.^.........
14:38:56.295140 IP ip-172-31-14-165.ap-southeast-2.compute.internal.47218 > ip-172-31-0-41.ap-southeast-2.compute.internal.ssh: Flags [.], ack 1, win 491, options [nop,nop,TS val 2834667801 ecr 1392008710], length 0
E..4#.@...p........).r......_.&.....&......
....R.^.
14:38:56.304151 IP ip-172-31-0-41.ap-southeast-2.compute.internal.ssh > ip-172-31-14-165.ap-southeast-2.compute.internal.47218: Flags [P.], seq 1:22, ack 1, win 490, options [nop,nop,TS val 1392008720 ecr 2834667801], length 21: SSH: SSH-2.0-OpenSSH_8.7
E..I..@....!...).......r_.&.........gH.....
R.^.....SSH-2.0-OpenSSH_8.7

14:38:56.304629 IP ip-172-31-14-165.ap-southeast-2.compute.internal.47218 > ip-172-31-0-41.ap-southeast-2.compute.internal.ssh: Flags [.], ack 22, win 491, options [nop,nop,TS val 2834667811 ecr 1392008720], length 0
E..4#.@...p........).r......_.'.....&Y.....
...#R.^.
```
On server1, press 'ENTER' to stop telnet. On server2, press 'CTRL+C' to stop tcpdump. 


### Step 4 (Optional): Hop from one to another

1. Transfer your private key file to server1 using scp command:
```
scp -i path-to-keypair path-to-keypair ubuntu@<Private IP EC2 #1>:~
```

2. SSH to server2 from server1 and observe the traffic.


