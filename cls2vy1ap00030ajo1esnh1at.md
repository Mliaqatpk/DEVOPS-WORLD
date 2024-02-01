---
title: "Day 42: IAM Programmatic access and AWS CLI 🚀 ☁"
datePublished: Thu Feb 01 2024 07:18:59 GMT+0000 (Coordinated Universal Time)
cuid: cls2vy1ap00030ajo1esnh1at
slug: day-42-iam-programmatic-access-and-aws-cli
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706771752464/f6af3b1b-d248-433a-a12f-3485a4ab724a.png
tags: cloud, aws, cloud-computing, automation, devops, aws-lambda, automation-testing, devops-articles, 90daysofdevops, 90daysofdevops-chanllenge, 90daysofdevops-devops-projectdevelopment-nonitbackground-github-docker-cloudplatforms-ec2-aws-elasticbeanstalk-lambdafunctions-devopspipelines-terraform-jenkins-docker-devsecops-scm-git-gitlab-bitbucket-buildtools-griddle-maven-ant-msbuild-monitoringtools-prometheus-grafana-ansible-ai-chatgpt-valueaddition-realworldproblems, 90daysofdevopschallenge, 90, batch-5, 92

---

![CLI-Your-Way:-Getting-Programmatic-Access-with-IAM-and-AWS-CLI](https://miro.medium.com/v2/resize:fit:875/1*ZNnqWKKUK5P56ROUDmJ2jQ.jpeg align="left")

### IAM Programmatic access

In order to access your AWS account from a terminal or system, you can use AWS Access keys and AWS Secret Access keys.

### AWS CLI

The AWS Command Line Interface (AWS CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can control multiple AWS services from the command line and automate them through scripts.

The AWS CLI v2 offers several new features, including improved installers, new configuration options such as AWS IAM Identity Center (successor to AWS SSO), and various interactive features.

### Task-01

**Create AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY from AWS Console.**

* Open the Amazon Management Console and log in.
    
* At the top right corner of the console, click on your username, and then choose "Security Credentials" from the drop-down list.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGTZjw2bdTwsA/article-inline_image-shrink_1500_2232/0/1678947335732?e=1712188800&v=beta&t=71yUSMn-BuBJMS8QKgjC1cWAj6ONQGiz-U_U89-TVv8 align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGk6onELr_kKA/article-inline_image-shrink_1500_2232/0/1678947378283?e=1712188800&v=beta&t=oT5cGAMSw8m_VE07h7GoK57i0wYSSSe0T433k3vRYcc align="left")

* Click on the "Access keys (access key ID and secret access key)" section.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQElsAtXP4JfZA/article-inline_image-shrink_1500_2232/0/1678947418776?e=1712188800&v=beta&t=5t_dOGmVzAkIZAms72V0HfcFr61iujQOX0yuGLV2VpE align="left")

* Simply select "Create Access Key."
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQHebuYN5FXUQQ/article-inline_image-shrink_1500_2232/0/1678947484611?e=1712188800&v=beta&t=KkKWbXLWylDINDXoa8WStrxQ0wXq-xfCh4bTpCrV5UE align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGt90b96K-Fww/article-inline_image-shrink_1500_2232/0/1678947494247?e=1712188800&v=beta&t=D6KqysoL0cYW9t1WCIocs4CoXSV4uVQ7NxR21Z1jfqk align="left")

* You will see both your secret access key and access key ID. Make sure to save the CSV file with your access key information in a safe place after downloading it.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEAAv0MoiBMCg/article-inline_image-shrink_1500_2232/0/1678947554880?e=1712188800&v=beta&t=w7z7QKov3z1knAOfiSB1dBRlUZizbJY9WstA76pZZCM align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQG7YoUqBlnwoA/article-inline_image-shrink_1500_2232/0/1678947578715?e=1712188800&v=beta&t=PdYHYrlZPzUkUT3oWJsOKWJx0Igi2YS3_WKtDDPkNt0 align="left")

### Task-02

Setup and install AWS CLI and configure your account credentials

Install the AWS CLI by following the instructions for your operating system: [https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFFNr9k0DRQ0A/article-inline_image-shrink_1500_2232/0/1678947615231?e=1712188800&v=beta&t=bD6CJARrySe0p6-CVGausW66IXN0gKcdUtjm33Ya8IE align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFTilbtS7--0g/article-inline_image-shrink_1500_2232/0/1678947634729?e=1712188800&v=beta&t=AVvGSXpq9kHiJfEKiOyXEBh8UjCLgSL2PERVJ1C-Vow align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQF7o0mRXI1-dQ/article-inline_image-shrink_1500_2232/0/1678947655929?e=1712188800&v=beta&t=JPbm0MUFDlI-SC8mIAVNhzlbyK8Nv80v57YpjKX6t_8 align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFPc-gzGU8_VA/article-inline_image-shrink_1500_2232/0/1678947672332?e=1712188800&v=beta&t=uGkgUguB-_3w61z530LK_uMZA9skvB5YsBAkScT6UuI align="left")

* Verify the aws-cli version
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQH4JU4SE38flg/article-inline_image-shrink_1500_2232/0/1678947754174?e=1712188800&v=beta&t=5P6awU5SUF_TjcS8qdx-Z26F4tuirPqMObf_UuUm3gU align="left")

Open a terminal or command prompt after installing the Amazon CLI, then enter the following command to set up your account credentials:

Your AWS Access Key ID and Secret Access Key must be entered when requested. The access key and secret key from the downloaded csv file should be copied and pasted. Input for your default region and output format will also be requested. Select an appropriate output format and the region that is nearest to your location.

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEl0xwY-Ro7zQ/article-inline_image-shrink_1500_2232/0/1678947823590?e=1712188800&v=beta&t=Gd3MiUG9uAiFZLeUSXxYuHwQTIMLAzPcHO66NzjF4A0 align="left")

* After setting up your default settings and entering your credentials, you may execute the following command to see if the CLI is operational:
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFzitspHXk6Mg/article-inline_image-shrink_1500_2232/0/1678947881274?e=1712188800&v=beta&t=9FVtmf7Zi0tcL1GPh_8dy6X2FxJCg6bNje8ufOSbfr8 align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQE7wlPaBP1mPg/article-inline_image-shrink_1500_2232/0/1678947894558?e=1712188800&v=beta&t=Q32KJUCrKboZ4-Ki7WmZyMuu8LW2-Y6NpB1Ydpy0Wws align="left")

Your default S3 bucket's contents should be listed by this command. Now that the Amazon CLI has been installed and set up, you may set up your account credentials.

This concludes the article; Please respond and offer your thoughts.🎯🎉🔥

![](https://miro.medium.com/v2/resize:fit:875/1*w5SPoGGLJzdw3H9BxyOx8A.jpeg align="left")