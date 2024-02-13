---
title: "Day 45: Deploy WordPress website on AWS 🚀🔥"
datePublished: Tue Feb 13 2024 09:51:56 GMT+0000 (Coordinated Universal Time)
cuid: clsk6oyc7000n08l61x2ub0ox
slug: day-45-deploy-wordpress-website-on-aws
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707817851049/40b97191-f195-4602-8ad1-34b72158c095.webp
tags: cloud, aws, wordpress, web-development, cloud-computing, automation, 90daysofdevops, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, batch-5

---

Introduction: Welcome back to our journey of building and deploying a website! Today, on Day 45, we're diving into the exciting realm of deploying a WordPress website on Amazon Web Services (AWS). WordPress is one of the most popular content management systems, and AWS offers robust infrastructure for hosting dynamic web applications. By combining these two, we can create a scalable and reliable platform for our website.

Setting Up AWS: Before we start deploying our WordPress site, let's ensure we have an AWS account set up. If you don't have one yet, head over to the AWS website and create an account. Once you're logged in, let's navigate to the AWS Management Console to get started.

Launching an EC2 Instance: Our first step is to launch an EC2 (Elastic Compute Cloud) instance, which will serve as the server for our WordPress site.

1. Log in to the AWS Management Console.
    
2. Navigate to the EC2 dashboard.
    
3. Click on the "Launch Instance" button.
    
4. Choose an Amazon Machine Image (AMI) - select a WordPress AMI from the AWS Marketplace.
    
5. Select an instance type based on your requirements.
    
6. Configure instance details such as network settings, storage, and tags.
    
7. Configure security groups to allow HTTP and HTTPS traffic.
    
8. Review and launch the instance.
    

Setting Up WordPress: Once our EC2 instance is up and running, we'll proceed with setting up WordPress on it.

1. Connect to your EC2 instance using SSH (Secure Shell).
    
2. Install LAMP (Linux, Apache, MySQL, PHP) stack on your instance.
    
3. Download and install WordPress.
    
4. Configure Apache to serve your WordPress site.
    
5. Create a MySQL database and user for WordPress.
    
6. Configure WordPress to use the MySQL database.
    
7. Complete the WordPress installation by accessing your server's public IP address in a web browser.
    

Securing Your WordPress Installation: Security is paramount when deploying a website. Here are some essential steps to secure your WordPress installation on AWS:

1. Update WordPress, themes, and plugins regularly.
    
2. Configure proper file permissions.
    
3. Enable HTTPS using SSL/TLS certificates.
    
4. Limit access to wp-admin and sensitive files.
    
5. Implement strong passwords and enable two-factor authentication.
    
6. Install security plugins like Wordfence or Sucuri.
    

Scaling and High Availability: AWS offers scalability and high availability features that allow your WordPress site to handle increased traffic and maintain uptime. Here are some strategies to scale and ensure high availability:

1. Utilize AWS Auto Scaling to automatically adjust the number of EC2 instances based on traffic.
    
2. Implement a Content Delivery Network (CDN) like Amazon CloudFront to cache static content and reduce latency.
    
3. Set up Amazon RDS (Relational Database Service) for managed MySQL databases to improve database performance and reliability.
    
4. Configure Amazon Route 53 for DNS management and failover routing to distribute traffic across multiple regions.
    

WordPress serves as the content management system (CMS) for more than 30% of all websites on the internet. It may be used to manage e-commerce sites, discussion boards, and many other well-known things, but blogs are where it is most frequently utilized. You may learn how to set up a WordPress blog site by reading this guide.

## Task-01

### As WordPress requires a MySQL database to store its data, create an RDS as you did on Day 44

Visit the Amazon RDS interface. the *"Create database"* button.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEnkn8csPTr9Q/article-inline_image-shrink_1500_2232/0/1679387350105?e=1713398400&v=beta&t=sMgzpo7uLIwJx1jrMzjmwtv7p4EgxUwrDu0kmS-L1ro align="left")

Make "MySQL" your engine type choice.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFl9IP24i0yTg/article-inline_image-shrink_1500_2232/0/1679387420333?e=1713398400&v=beta&t=VCx0iSB8IS8ulrSI_NLpttiGDb3a6L0faE7u7Ho4ueI align="left")

For the *"Database instance class"* template, select the *"Free tier"* option.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFNZRsTPjl7fA/article-inline_image-shrink_1500_2232/0/1679387506956?e=1713398400&v=beta&t=z3rZ2IU3ztN_iTq4VpCBpnZe4mW5-v-ylce8vFYj7v0 align="left")

Give the *"Database instance identification"* a unique name.

Set the *"Master username"* and *"Master password"* for the database.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEf85q3VZ6hhg/article-inline_image-shrink_1500_2232/0/1679387615016?e=1713398400&v=beta&t=T9qYLULARQXvtdOKl4kSAaOebKtohrwjJaTDU_LEcM8 align="left")

Configure the instance's *"Virtual Private Cloud (VPC)"* and *"Subnet Group"* settings. Maintain the default values for the other parameters.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGcuDtXF0etXw/article-inline_image-shrink_1500_2232/0/1679387685696?e=1713398400&v=beta&t=JWbOzhvMzRt63rqfv1F03ZMTF-2NBuHQpQ9w9rqR2cg align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQG6vmhlpxy96Q/article-inline_image-shrink_1500_2232/0/1679387709443?e=1713398400&v=beta&t=uZE9mbvNGrMn1Ic4paEkJfcJBcNhAm5QPC3FRTqMwUc align="left")

Choose *'Default VPC'*

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQHga7C8q99doA/article-inline_image-shrink_1500_2232/0/1679387796461?e=1713398400&v=beta&t=C8EV7YA_5uZAc61N9bwtQd6O9Zsq8ocWWi4G7HKvzIk align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFG41g_qx9U-w/article-inline_image-shrink_1500_2232/0/1679387836419?e=1713398400&v=beta&t=UhOpAoRoB3IoNGQ9GhmoiNzLcIEYpMNbs2iVCgfnPX8 align="left")

Click on *"create database"*

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGNsJTnpk_pFw/article-inline_image-shrink_1500_2232/0/1679387875595?e=1713398400&v=beta&t=LSdm-aBYdHEd8pcHH-tlRCnwLO5VhApc89wuhN935lo align="left")

The database was created.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQECgvKKWhNPKA/article-inline_image-shrink_1500_2232/0/1679387926384?e=1713398400&v=beta&t=tuANhW-X6s4O5a8FACNGrWGLdZ33tnrjSfdXmDRog3s align="left")

### To configure this WordPress site, you will create the following resources in AWS:

WordPress installation and hosting on an Amazon EC2 instance.

access the Amazon EC2 console. Choose a Linux AMI by clicking "Launch Instance."

Select a VPC and subnet, and then a kind of instance, such as t2.micro.

Set up security group rules so that incoming traffic is permitted on the correct port for the type of database you're using (e.g. port 3306 for MySQL).

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFqGYr0B4bu_g/article-inline_image-shrink_1500_2232/0/1679388061621?e=1713398400&v=beta&t=coicCSAIbtdujvQO_qgrez2DDVTUtVpnYoge2tDJtSk align="left")

### An Amazon RDS for MySQL database to store your WordPress data.

Choose the MySQL database you just established, navigate to the Connectivity & Security tab, and select the VPC security group. You may access the security group set up for your database using the console.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGAC7QJVmnpmg/article-inline_image-shrink_1500_2232/0/1679388146842?e=1713398400&v=beta&t=wfKi6aZ5NvrHjWFHUPLt1XGUE-CUtcI-4Y_1LXOMfWI align="left")

To modify the rules for your security group, select the Incoming Rules tab and then the Edit inbound rules button.

By changing the Type attribute to MYSQL/Aurora, the Protocol and Port range will be updated to the correct settings.

The security group that you used for your EC2 instance should be selected.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQH9ow4devSWdA/article-inline_image-shrink_1500_2232/0/1679388260186?e=1713398400&v=beta&t=T83tddSxmI5PZlt37gyWlBWeoz2bL706z2F36jGT4bU align="left")

Enter your EC2 instance via SSH.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGOExV2xxAHdA/article-inline_image-shrink_1500_2232/0/1679388307833?e=1713398400&v=beta&t=VUd2XpAR7nP1RHmNL44ryop3IeNmm0w1of8Wd4hnOe8 align="left")

Install a MySQL client in your terminal to access the database by running the following command:

```plaintext
sudo apt install mysql-client-core-8.0
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQE6ryAPOvsIog/article-inline_image-shrink_1500_2232/0/1679388411096?e=1713398400&v=beta&t=-YI9yX7jyf23VW6Z9BtBSG9M_bSKXipNGID_Ki-Hgws align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQH1Hv1D-rOxIg/article-inline_image-shrink_1500_2232/0/1679388508853?e=1713398400&v=beta&t=F7XqqLevYy9sv_1IYjRMI_jRt7FkhiS-Frp_RqZ5ChA align="left")

Use the following command to connect to your MySQL database in your terminal. Substitute your master username and password for "user" and "password," which you specified when you created your Amazon RDS database. The RDS database endpoint for -h is the host.

```plaintext
mysql -h <rds-database-endpoint> -P <port-no> -u <user> -p <password>
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQE6kkxByO5e6g/article-inline_image-shrink_1500_2232/0/1679388543598?e=1713398400&v=beta&t=lpjHhjziuFAfraO9Q5LsC8sH5eb2ltC6mE0pkEHKk1s align="left")

Create a database user for your WordPress application, and then grant access to the WordPress database to the user.

Enter the commands below into your terminal:

```plaintext
CREATE DATABASE wordpress;
CREATE USER 'wordpress' IDENTIFIED BY 'wordpress-pass';
GRANT ALL PRIVILEGES ON wordpress.* TO wordpress;
FLUSH PRIVILEGES;
Exit
```

To protect your database, you ought to use a stronger password than WordPress-pass.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQE9DydRBi65ng/article-inline_image-shrink_1500_2232/0/1679388669754?e=1713398400&v=beta&t=mpbP22SbtIGEEO7E12N8GfwHMAFpSbAkbQBm2N4zacM align="left")

On your EC2 instance, you must operate a web server in order to run WordPress.

Run the following command in your terminal in order to install Apache on your EC2 instance:

```plaintext
sudo apt-get install apache2
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQESXQto2Sa3XQ/article-inline_image-shrink_1500_2232/0/1679388767593?e=1713398400&v=beta&t=U2pVcPOHxFKSDMIlRodrYvoBhWWgc0fDQ3nUfmRb_bY align="left")

In your terminal, type the following command to launch the Apache web server:

```plaintext
systemctl restart apache2
```

By accessing your ec2 instance's public IP, you may verify that your Apache web server is operational.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGoi1TN3dAQeg/article-inline_image-shrink_1500_2232/0/1679388896723?e=1713398400&v=beta&t=WWyavFn7rU-PUuy7ucQmCiiiE1YxhqNL8NA8RoPRRJ0 align="left")

**Set up the server and post your new WordPress app.**

Use the following commands in your terminal to first download and uncompress the software:

```plaintext
wget https://wordpress.org/latest.tar.g
tar -xzf latest.tar.gzz
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGbQWVr-vpfOw/article-inline_image-shrink_1500_2232/0/1679389036657?e=1713398400&v=beta&t=2H5RP5sjFGs2Qlualja5wcTV3Tkk9kVlGxlM-7u17To align="left")

With the ls command, you will notice a tar file and a directory called WordPress that contains the uncompressed contents.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEURD4YzODA0w/article-inline_image-shrink_1500_2232/0/1679389112845?e=1713398400&v=beta&t=2hgzxXFsjLdimyJmKFxBI5hIxJjr04mv3WecqdQ1k2Q align="left")

open the wp-config.php file

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGQkQFkxHUuDg/article-inline_image-shrink_1500_2232/0/1679389236221?e=1713398400&v=beta&t=0Vf7FP0D1d-Qy5YUgXedmr0IICU9VmvJViLoETRUyeg align="left")

Modify the following lines in the database configuration:

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEHQ9ZmJM9svA/article-inline_image-shrink_1500_2232/0/1679389310219?e=1713398400&v=beta&t=Har9rjkQxnCtyyMh5-4VJhEva3PGe2QWQ0jHB4DtCVA align="left")

1. **DB\_NAME**: your RDS database name
    
2. **DB\_USER:** The name of the user you created in the database in the previous steps
    
3. **DB\_PASSWORD**: The password for the user you created in the previous steps
    
4. **DB\_HOST**: The hostname of the database means your database endpoint
    

The Authentication Unique Keys and Salts configuration area is the second one that needs to be set up.

You can substitute the following text for everything in that section:

Make sure to create the following details with [https://api.wordpress.org/secret-key/1.1/salt](https://api.wordpress.org/secret-key/1.1/salt)

```plaintext
define('AUTH_KEY',         'Z9-CmDhIDuNlO8t5EM[+xf-[`VJ)_A>qknjR>Kat$2a6=oYF_-|%H+4MkJW^!t9x');
define('SECURE_AUTH_KEY',  '(sIg&e-5bk|&=ruFb0LLF,P$&kFS_L+B]ovbC@wEN`@mE~V q?TWzMvz;v3ZGnF1');
define('LOGGED_IN_KEY',    'ZA(ia@)uP7i#Z.=$`jBZPv|IUW=6|;+xuTcPCYR+f.U[i((;nS,!?0z!ifYY$O=F');
define('NONCE_KEY',        'c3k|3LBocTe%J#-|Lnl%8eL,TD3,nV-AU|Y(M*|Vy:##dJT{KMNzDu*J7e9:xbX=');
define('AUTH_SALT',        '+mRr-[sDf-KsN&i;*qVjUkDV=A-n.&]G~oVH&J0M,taM,1>vkjjuOiQm6RIhUmmo');
define('SECURE_AUTH_SALT', 'dmOHiQah U<_Z+np}D>i=~0f[5hv509+E/8WNymuQ5P/-j#h&TO>tY5HHM$qG,Pt');
define('LOGGED_IN_SALT',   '=X|}omdoywp,j.1eq;z0dmK],|*s1FJ5kf<Q7+-qr jX/VgOub++FgBX8E,8<}r2');
define('NONCE_SALT',       '/dNw0(+[W.@-8|kXMppSKv0e1>@P_|b05y-GS^!Hb`!Xj0Z+L-VGm|? K9`krU/1');
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFGM-djmLXHzQ/article-inline_image-shrink_1500_2232/0/1679389600747?e=1713398400&v=beta&t=-7iSHpLgRWH9WoR7dxtELLr-oFxMW51TYPSI5ncnyyQ align="left")

Make sure you have replaced the text with the text you have created.

Installing WordPress application dependencies comes first. Activate the following command in your terminal.

```plaintext
sudo apt install php libapache2-mod-php php-mysql -y
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGj_dAd5NM87A/article-inline_image-shrink_1500_2232/0/1679389737972?e=1713398400&v=beta&t=IryxzZt2pu39g6wV46PbEAA7zHFUO7QaoopZmQbwf0o align="left")

Copy your WordPress application files into the /var/www/html directory used by Apache.

```plaintext
sudo cp -r wordpress/* /var/www/html/
```

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGXyrkCfoMlUQ/article-inline_image-shrink_1500_2232/0/1679389788914?e=1713398400&v=beta&t=dzwmKDB-EAtGblL0NG7UUq_as8bWt0fcJaAeJrvmlBQ align="left")

Finally, restart the Apache web server

```plaintext
systemctl restart apache2
```

The WordPress welcome page should be visible if you navigate to *"ec2-public-ip/wp-admin/".*

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEK1-HKDsVB-g/article-inline_image-shrink_1500_2232/0/1679389856836?e=1713398400&v=beta&t=amlN7DYorV5QJzC-Z26Od1RlDLZUK24tv1vrWTkJzFU align="left")

I appreciate you continuing to read; I hope you learned something. ❤️🙌