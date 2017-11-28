# Create-Bastion-Host-to-access-your-AWS

Reference:
http://justsomestuff.co.uk/theblog/2017/01/15/using-a-bastion-host-to-access-your-aws-ec2-instances/

Create an Bastion host Instance.
1.	In the AWS Services menu, Click EC2
2.	Click Launch Instance
3.	In the row for Amazon Linux AMI 2017.09.1(HVM), SSD volume type Click Select
4.	Confirm that the t2.micro instance type is selected
5.	Click Configure Instance Details
6.	Click Add storage
7.	Click Add Tags
8.	Click Add Rule make sure to open the SSH port 22 in inbound rule
9.	Click Review and Launch
Create Your VPC
10.	In the AWS Services menu, Click VPC
11.	Click Start VPC Wizard
12.	In the navigation pane , Click VPC with Public and Private Subnets.
13.	Click Select
14.	Configure the Setting 
15.	Click Create VPC
16.	In the success message Click OK

Create Private Instance
17.	Create an Ec2 Instance 
18.	Auto public IP assignment change to disable
19.	security configuration step for the inbound rules open the SSH port and force it to listen only to First Instance 
20.	launch the instance.

Finally, we can deploy an instance into the private subnet. For security purposes, we need to ensure that:
21.	This instance uses a different key pair than the key pair used to access the bastion host instance
22.	Note If you are using PuTTY as your SSH client, you will need to convert this file to PPK format in order to use it to log in to your private instance later
23.	Start puttygen and select “Load”
24.	Select your .PEM file.
25.	Putty will convert the .PEM format to .PPK format.
26.	Select “Save Private Key”
27.	In the EC2 Management Console, in the navigation pane, click Instances. Select the instance Internal Server and make a note of the private IP address.
28.	ssh ec2-user@<private-ip-address>
Reference:
http://justsomestuff.co.uk/theblog/2017/01/15/using-a-bastion-host-to-access-your-aws-ec2-instances/
https://www.youtube.com/watch?v=J64PbhirYS0&t=778s


