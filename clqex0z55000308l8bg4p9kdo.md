---
title: "Day 24 Task - 90daysofdevops : Complete Jenkins CI/CD Project"
datePublished: Thu Dec 21 2023 08:03:06 GMT+0000 (Coordinated Universal Time)
cuid: clqex0z55000308l8bg4p9kdo
slug: day-24-task-90daysofdevops-complete-jenkins-cicd-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703145731384/0c7b5521-8667-4ee5-904c-be3398dd81bb.png
tags: aws, jenkins, jenkins-devops, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge

---

## Task-01

* Fork [this](https://github.com/LondheShubham153/node-todo-cicd.git) repository: To Fork Repository Go To location of Project then there is FORK option on top right side. Click on it you will able to fork Project.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145161647/c2438ace-abff-4adf-b6ff-fdb9a2c4047e.png align="center")
    

![Github Webhooks to Trigger Jenkins Pipeline](https://hashnode.com/utility/r?url=https%3A%2F%2Fcdn.hashnode.com%2Fres%2Fhashnode%2Fimage%2Fupload%2Fv1693051291218%2Ffa415447-b736-4384-b877-e01645690a1c.png%3Fw%3D1200%26h%3D630%26fit%3Dcrop%26crop%3Dentropy%26auto%3Dcompress%2Cformat%26format%3Dwebp%26fm%3Dpng align="left")

* Create a connection to your Jenkins job and your GitHub Repository via GitHub Integration : Connection to your Jenkins Job with GitHub projects **You can done through GitHub Hook : Go to project settings -&gt; click on webhook -&gt; Add webhook**
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145204758/f9cf0932-1a7c-4161-b067-f7f8211e57b1.png align="center")
    
    * Now for Installing GitHub Integration plugin in Jenkins
        
    * Open your jenkins dashboard.
        
    * Click on the Manage Jenkins button on your Jenkins dashboard
        
    * Click on Manage Plugins
        
    * Install GitHub Integration plugin
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145307780/09f4b17e-6499-4225-a6c4-edb114cb4149.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145448290/df37a66d-fa4e-49cb-8ada-04674cf212c4.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145607811/7063ac73-322c-4293-ac29-edb9ce8a44b6.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145623313/493f5cbb-c80c-4b0b-894e-0ef75d67e215.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703145641388/793cfea7-55e0-4995-98ee-1f182c3b18b5.png align="center")
    
    ### Task-02
    
    * In the Execute shell run the application using Docker compose
        
    
    ![](https://media.licdn.com/dms/image/D4D12AQHywNLFNWDgfw/article-inline_image-shrink_1500_2232/0/1701062077124?e=1708560000&v=beta&t=Ulcuf2uZO1iw2uC6RKe2tvogdQG-cZgKJjh4iLrFm_0 align="left")
    
    * You will have to make a Docker Compose file for this Project
        
    
    **NOTE : Install the docker compose on your server ( like for ubuntu - docker-compose install -y)**
    
    * After build you can check console output.
        
    
    ![](https://media.licdn.com/dms/image/D4D12AQFqR_S9rfYhTg/article-inline_image-shrink_1500_2232/0/1701062736826?e=1708560000&v=beta&t=y0JtL2O4K63MTPnI93fbmQf8AjxN2IfgybsFO1krlns align="left")