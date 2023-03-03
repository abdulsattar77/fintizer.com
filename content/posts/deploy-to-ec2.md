---
author: "Abdul Sattar"
title: "Deploying to EC2 and Configuring Security Groups"
date: "2023-03-01"
description: "Manually deploying a website to EC2"
tags: ["DevOps"]
ShowToc: true
ShowBreadCrumbs: true
---

# INTRODUCTION

This is the mini project documentation of manual deployment of restaurant website where you can access the menu, reservation and information about the restaurant. The features offered by this website are booking a table along with your phone number, opening times, and contact details.

The designing of the website is done through HTML and internal CSS which we can obtain from the public Git repository. The link and the screenshot of that public repository is given in this documentation.

The deployment of the website is done through AWS. AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application. You can use the AWS Management Console or well-documented web services APIs to access AWS's application hosting platform.

Amazon Web Services, Inc. is a subsidiary of Amazon that provides on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered, pay-as-you-go basis. Often times, clients will use this in combination with autoscaling.

The services used in this project are Amazon Elastic Compute Cloud (Amazon EC2) and security groups.

The SSH of the EC2 instance is done through open-source terminal PuTTY. The configuration of EC2 is described clearly in this document using the Linux OS. PuTTY is a free and open-source terminal emulator, serial console, and network file transfer application. It supports several network protocols, including SCP, SSH, Telnet, rlogin, and raw socket connection. It can also connect to a serial port. The name "PuTTY" has no official meaning.

The installation and enabling of HTTPd server is done in PuTTY by using Linux command, then Git clone takes place followed by Git initialization. Once the code is cloned into HTTPd location and port 80 is enabled into security group inbound rules, then the public IP address of the EC2 instance is used to visit the website.

---

## Tools and technologies used 

<ol type="i">
  <li>Cloud provider - Amazon web services (AWS)
    <ol type="i">
      <li>EC2 instance (Linux OS)</li>
      <li>Security groups (inbound rules)</li>
    </ol>
  </li>
  <li>Git and Git Hub</li>
  <li>Httpd server software</li>
  <li>Terminal emulator – PuTTY</li>
</ol>

## Procedure 

1. AWS account setup 
2. launching an ec2 instance 
3. install putty and configure the instance 
4. updating and installing git and httpd softwares in the instance 
5. cloning the github repository of restaurant website files into html location  of httpd
6. configure the security group 
7. copy the public ip of the instance and cross check the website 

## Procedure in depth 

1. AWS account setup
    1. Visit the link shown below and create a free aws account by giving debit/credit  card and personal details 

[AWS Free Tier](https://aws.amazon.com/free/?trk=14a4002d-4936-4343-8211-b5a150ca592b&sc_channel=ps&s_kwcid=AL!4422!3!453325184782!e!!g!!aws&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all)

![ec2](../../images/ec2.png)

2. Launching an ec2 instance
    1. Search for the ec2 instance in the aws 
    2. Click on the instances and launch the instance 

![launchimage.png](../../images/launchimage.png)

Now give the name and select the operating system as amazon linux along with the free tier AMI 

Now select the CPU and ram basic free tier cpu is enough to launch this website 

Create a key pair if you don’t have one and make sure to select .ppk file 

Once the key pair is downloaded make sure to select the file 

Network settings 
Make sure to create security group option to allow ssh from anywhere this is very important because we use this to set our inbound rules  
Configure the free tier storage and finally launch the instance 

3.install putty and configure the instance 
Search the putty for windows or click on the link to download and install https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
Install the putty by reading all the terms and policies you will be seeing this type of interface 
 
Now copy the instance public ip and paste it in the host name 
 

 
Now go to the ssh – auth – credentials of the putty and browse the file which you have downloaded while launching instance 
 

Go to appearance and select the font size for the terminal in putty 
Type ec2-user in the terminal 







4. updating  and installing git and httpd softwares in the instance 
First of all update the instance 
 
use the following commands to install git and httpd software into the instance 
 
 

5.cloning the github repository of restaurant website files into html location of httpd
Visit the following link into the browser 
https://github.com/YaninaTrekhleb/restaurant-website
you will be directed to the github repository 
 
This repository contains the html and css files along with images of the restaurant website it is publicly available we can use it 
Copy the http link of this 
Now go to the terminal start the httpd and remove all file from this location var/www/html/.git  
Now clone the repository to the var/www/html/.git to this location 
 

6.configure the security group
Go to the aws console and search security group and edit the inbound rules to access the website from anywhere
Select the security group name in which our instance is present
  
Select the all ipv4 traffic and select all ports
7.copy the public ip of the instance and cross check the website 

Conclusion 
With this mini project one can understand how a website can be deployed manually using aws services .  

