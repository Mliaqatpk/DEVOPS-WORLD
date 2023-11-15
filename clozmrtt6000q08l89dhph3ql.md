---
title: "𝔻𝕒𝕪 𝟟: "𝕌𝕟𝕝𝕠𝕔𝕜𝕚𝕟𝕘 𝕃𝕚𝕟𝕦𝕩 ℙ𝕒𝕔𝕜𝕒𝕘𝕖 𝕄𝕒𝕟𝕒𝕘𝕖𝕞𝕖𝕟𝕥 𝕒𝕟𝕕 𝕊𝕪𝕤𝕥𝕖𝕞𝕔𝕥𝕝: 𝔸 ℂ𝕠𝕞𝕡𝕣𝕖𝕙𝕖𝕟𝕤𝕚𝕧𝕖 𝔾𝕦𝕚𝕕𝕖""
datePublished: Wed Nov 15 2023 10:39:48 GMT+0000 (Coordinated Universal Time)
cuid: clozmrtt6000q08l89dhph3ql
slug: 8j2uucdlzlwnzwqipcdn586iclwnzwm8j2vncdlz3wnzwg8j2vlpcdlzzwnzwa8j2vncdlzgg8j2vgcdlzrwnzwf8j2vpvcdlakg4osz8j2vkvcdlztwnzwc8j2vkvcdlzjwnzwwipcdlytwnzws8j2vncdlzlwnzwy8j2vlvcdlz7wnzww8j2vncdlaug8j2vkvcdlzwnzwvipcdlyrwnzwq8j2vppcdlaxwnzww8j2vnvcdlztwnzwl8j2vntog8j2uucdihilwnzwg8j2vnvcdlahwnzwj8j2vlvcdlznwnzww8j2vncdlatwnzwa8j2vpcdlzyg8j2uvvcdlabwnzwa8j2vlfcdlzyi
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700044587592/8adc7e99-aa3f-40ae-b433-b2b9c78ec6a2.png
tags: linux, learning, devops, trainwithshubham, tws

---

# 𝒲𝒽𝒶𝓉 𝒾𝓈 𝒫𝒶𝒸𝓀𝒶𝑔𝑒 𝑀𝒶𝓃𝒶𝑔𝑒𝓂𝑒𝓃𝓉?

Package management in Linux refers to the process of installing, updating, configuring, and removing software packages on a Linux-based operating system. It's a fundamental component of maintaining a Linux system and ensuring that the software installed on it is up-to-date, secure, and well-integrated.

Everything related to the management of those packages is called Package Management

## 𝓓𝓲𝓯𝓯𝓮𝓻𝓮𝓷𝓽 𝓣𝔂𝓹𝓮𝓼 𝓸𝓯 𝓟𝓪𝓬𝓴𝓪𝓰𝓮 𝓜𝓪𝓷𝓪𝓰𝓮𝓶𝓮𝓷𝓽 𝓣𝓸𝓸𝓵𝓼

Different Linux system comes with different package management tools such as YUM/DNF, RPM, APT, Flatpak, Snap etc

But, Today we will learn about YUM/DNF, RPM and APT Package Managers

𝓨𝓤𝓜/𝓓𝓝𝓕 𝓟𝓪𝓬𝓴𝓪𝓰𝓮 𝓜𝓪𝓷𝓪𝓰𝓮𝓻

Yum (Yellowdog Updater, Modified) is a package manager used in Red Hat-based Linux distributions like Red Hat Enterprise Linux (RHEL), CentOS, and Fedora. It simplifies the installation, updating, and removal of software packages. Yum automatically handles dependencies and connects to software repositories to fetch and manage packages. It's a command-line tool that makes software management more efficient in these Linux distributions.

* YUM is a primary package Management Tool for Redhat
    
* YUM performs dependency resolution when installing, updating and removing software packages
    
* YUM can manage packages from installed repositories in the system or from .rpm packages.
    

𝓗𝓸𝔀 𝓽𝓸 𝓾𝓼𝓮 𝓨𝓤𝓜 𝓲𝓷 𝓛𝓲𝓷𝓾𝔁?

We will look at some of the commands with the YUM package manager. commands such as install, remove, upgrade etc.

* How to install a package using YUM
    

```plaintext
yum install nginx -y
```

* How to remove the package using YUM
    
* ```plaintext
    yum remove nginx
    ```
    

* How to update a package using YUM
    
* ```plaintext
    yum update nginx
    ```
    
    Since we have installed nginx just now, it is a fresh update therefore we cannot see any updates there, but if you're version of nginx is old then you can easily update it with the update command.
    
    * How to upgrade a package using YUM
        
        ```plaintext
        yum upgrade nginx
        ```
        
        The same goes for the upgrade part. It is the latest version we have just now installed therefore there are now current upgrades available.
        
    
    ### 𝓓𝓲𝓯𝓯𝓮𝓻𝓮𝓷𝓬𝓮 𝓫𝓮𝓽𝔀𝓮𝓮𝓷 𝓨𝓤𝓜 𝓤𝓟𝓓𝓐𝓣𝓔 & 𝓨𝓤𝓜 𝓤𝓟𝓖𝓡𝓐𝓓𝓔?
    
    Update: It will keep the old packages, so we can roll back to the previous one if the new one has issues.
    
    Upgrade: It will delete the old packages and will install the latest version.
    

### **How to check all the options of the YUM?**

```plaintext
yum -options
```

There are many more commands available further below.

The packages listed above can be updated to the latest version using the update command.

### How to check history using YUM

```plaintext
yum check-update
```

We use the `history` command to check all the past work that has been done related to the packages `history` command will show you the activity with the date and time.

### **Undo/Redo with YUM**

```plaintext
yum history undo/redo <id>
```

here, `undo` is also works for `rollback` to the previous update

This will undo the process of installing Nginx

### **Tips**

if you're using you're system as a normal user then you will have to use sudo commands before the yum commands.

If you're using it as a root user then you can directly use the commands without using the sudo command.

### RPM Package Manager

The RPM Package Manager, often referred to as RPM, is a package management system for Linux-based operating systems. It is primarily used in Red Hat, CentOS, Fedora, and other related distributions. RPM is responsible for:

1. **Packaging:** It creates software packages in the RPM format, which contain the software, metadata, and installation scripts.
    
2. **Installation:** RPM installs software packages on your system, managing dependencies to ensure that all required components are in place.
    
3. **Querying:** It allows users to query the system for installed packages, verifying package information and version details.
    
4. **Updates:** RPM can update software packages by replacing older versions with newer ones.
    
5. **Removal:** It removes packages from the system cleanly, making sure to address any dependencies affected by the removal.
    

* RPM Package Manager is also called RedHat package manager.
    
* using RPM you can install, uninstall and query individual software packages.
    
* RPM maintains a database of installed packages that enable powerful and fast queries.
    

### Limitation of RPM

* RPM cannot manage dependencies like the YUM package manager.
    

### How to use RPM

* How to install a package using RPM
    

```plaintext
rpm -i package-name
```

* \-i is used to install a package
    

To install an RPM file first you have to download a .rpm file from the web which you can easily do with the wget magic trick🪄

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698726712166/a410ee04-b523-463a-b048-0a6c59e6f573.png?auto=compress,format&format=webp align="left")

Once you see that the file is downloaded then you can use the rpm commands to install the .rpm file

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698726767372/7b7c2494-e4b4-4b63-af34-f0f7e0a59295.png?auto=compress,format&format=webp align="left")

You can now see that the file is installed without any issue with the rpm package manager.

* How to upgrade a package in RPM
    

```plaintext
rpm -U package-name
```

* here, capital -U is used to upgrade an RPM package manager
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698726881480/74c269ec-74db-4295-ba88-3c5fb5a85534.png?auto=compress,format&format=webp align="left")

You can see that the package we have installed is the most up-to-date package and that's why it has no pending upgrades.

### Another way to install with RPM and show the progress bar

```plaintext
rpm -ivh package-name
```

* \-i stands for install
    
* \-v stands for verbose
    
* \-h is used to show the hash rate (progress bar)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698726986013/9b609afe-f37c-4ce4-8c4e-a57c2669eb4a.png?auto=compress,format&format=webp align="left")

### How to delete a file using RPM

```plaintext
rpm -evh package-name
```

* \-e stands for erase (remove/uninstall)
    
* \-v stands for verbose
    
* \-h stands for the hash rate (progress bar)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727032526/33a9c3b4-636f-4531-81d4-292eeea09bba.png?auto=compress,format&format=webp align="left")

### Few more RPM commands

* To query all the installed packages
    

```plaintext
rpm -qa
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727065349/2a5a9597-05c3-4565-96dd-e1de44b0c2a8.png?auto=compress,format&format=webp align="left")

* To get more info about the package using RPM
    

```plaintext
rpm -qi package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727094001/b5d960fb-c744-4b8c-8b2f-17fad31a5b24.png?auto=compress,format&format=webp align="left")

* How to get info about a config file for a package
    

```plaintext
rpm -qc package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727116649/13a9f123-2d0f-4642-a3e8-41a07140c621.png?auto=compress,format&format=webp align="left")

### DNF Package Manager

DNF (Dandified YUM) is a modern package manager primarily used in Red Hat-based Linux distributions like Fedora and CentOS. It serves as a command-line tool for installing, updating, and managing software packages on these systems. `dnf` is an improved and more user-friendly replacement for the older `Yum` package manager.

### Some dnf commands:

* How to list all the available packages in dnf
    

```plaintext
sudo dnf list available
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727210910/4d5e8cbe-d9e3-4067-9591-0765ac227ba9.png?auto=compress,format&format=webp align="left")

* How to list all the installed packages in dnf
    

```plaintext
sudo dnf list installed
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698727180749/9be86941-860d-48ba-830b-da6deb851e04.png?auto=compress,format&format=webp align="left")

* How to update a package using dnf
    

```plaintext
sudo dnf update
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728475903/bfb0943d-449f-4d48-9d7b-ea0a355b3318.png?auto=compress,format&format=webp align="left")

* How to upgrade a package using dnf
    

```plaintext
sudo dnf upgrade
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728537862/8cb74777-3a59-459a-ab57-fb21ff0206d5.png?auto=compress,format&format=webp align="left")

* How to install a package using dnf
    

```plaintext
sudo dnf install package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728621721/d70d7957-c391-4e99-8f9c-66a90f21c495.png?auto=compress,format&format=webp align="left")

* How to remove a package using dnf
    

```plaintext
sudo dnf remove package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728702264/7ffacb3a-c22a-4438-83b1-a3c0f98361ff.png?auto=compress,format&format=webp align="left")

* How to get info about a package
    

```plaintext
sudo dnf info package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728756810/a166160b-a0db-4683-82e7-9d9a674baa97.png?auto=compress,format&format=webp align="left")

* How to search a package using dnf
    

```plaintext
sudo dnf search package
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728799502/67262418-3d8b-41f5-9d27-1430446618ba.png?auto=compress,format&format=webp align="left")

Moving ahead, let's see about the APT package manager.

### APT Package Manager

**APT (Advanced Package Tool)** is a package management system used in Debian-based Linux distributions, such as Debian and Ubuntu. It simplifies the installation, updating, and removal of software packages. APT manages a vast repository of pre-compiled software packages, making it easy for users to access and maintain their systems with a few simple commands. It handles dependencies, ensuring that all required components for a particular software package are installed. APT is known for its reliability, and it is often used through commands like `apt-get` and `apt`.

* APT is also known as the Advance Packaging Tool.
    
* APT is very similar to YUM commands.
    
* APT is generally used for Debian systems like Ubuntu, Kali Linux etc.
    

### Some APT Commands:

* How to install a package using apt
    

```plaintext
apt install package-name
apt-get install package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728928866/aacfa1bf-4325-4cad-a757-184ef2a1f7bc.png?auto=compress,format&format=webp align="left")

Since I'm using Ubuntu as my main system and Ubuntu is Debian-based system that is why it uses apt package manager and it's amazing. To see what I have installed see below.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729016580/587437f6-efa4-4738-a227-3a13ff94d274.png?auto=compress,format&format=webp align="left")

Isn't this cool 😎 you can do many more things like this with the apt package manager.

* How to remove a package using apt
    

```plaintext
apt remove package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698728899954/f330c662-8d8b-4a16-b6fb-5f2c242cd29b.png?auto=compress,format&format=webp align="left")

* How to remove dependencies of a removed package
    

```plaintext
apt autoremove
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729120572/7df60eb4-8015-46d0-91c5-6fd7a0a1c365.png?auto=compress,format&format=webp align="left")

* How to update the repository
    

```plaintext
apt update
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729160498/987d8e4b-7e8a-4da8-826a-07b461108910.png?auto=compress,format&format=webp align="left")

* How to search for an app in the cache
    

```plaintext
apt-cache search package-name
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729298108/dab95fd4-de97-4615-808a-6396f0a4b3b7.png?auto=compress,format&format=webp align="left")

## Practical Tasks:

1. ### How to install Docker on the system using the package manager?
    

### What is Docker?

Docker is a platform for developing, shipping and running applications in containers. Containers are lightweight, isolated environments that package an application and its dependencies, making it easy to deploy and run the same software consistently across different environments. Docker simplifies software development, testing, and deployment by providing a standardized way to package and manage applications.

To perform this task we will use the apt package manager. Since I'm using Ubuntu 23.10. The APT package manager is my default package manager.

1. Set up Docker's `apt` repository.
    

```plaintext
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

To install docker on your system you can use the following commands. These are not just some random commands but are from Docker's official website.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729547212/f55075d5-fa2e-460f-994d-1daa3b6f423a.png?auto=compress,format&format=webp align="left")

1. Install the Docker packages.
    

```plaintext
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698729641348/0346ee0b-46f0-4472-93ec-28cc74cfe14a.png?auto=compress,format&format=webp align="left")

1. Verify that the Docker Engine installation is successful by running the `hello-world` image.
    

```plaintext
sudo docker run hello-world
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698730007771/d52e3479-a8fe-4171-b2c5-0d3e68b3c3cd.png?auto=compress,format&format=webp align="left")

If you see this output, then you have successfully installed and started the Docker engine.

1. ### How to install Jenkins on the system using the package manager?
    

Jenkins is like a digital assistant for software developers. It helps them build and release their software more easily. Think of it as a robot that can automatically do repetitive tasks, like testing the code and sending it to the server when it's ready. This saves time and makes sure everything works smoothly in the software development process.

To install Jenkins on our system will do:

1. Check if you already have <mark>JAVA</mark> installed on your system
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698730317678/b58b5ec1-6162-4d70-847b-8928dd181d8d.png?auto=compress,format&format=webp align="left")

1. Start by importing the GPG key. The GPG key verifies package integrity but there is no output
    

```plaintext
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698731743167/5c27c789-767b-4e32-9c60-39bac159b7de.png?auto=compress,format&format=webp align="left")

1. Add the Jenkins software repository to the source list and provide the authentication key:
    

```plaintext
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698731773854/70859571-7f0e-46f3-8fe1-dae772cae6f7.png?auto=compress,format&format=webp align="left")
    
    Update Your System
    

```plaintext
sudo apt-get update
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698731802671/ce6f6c4c-3e63-4aa6-9a5a-80b29546b102.png?auto=compress,format&format=webp align="left")

1. Install Jenkins
    

```plaintext
sudo apt-get install jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698731900140/1eae104f-b188-4d69-8e36-76fd0d582b89.png?auto=compress,format&format=webp align="left")

As you can see above, Jenkins has been successfully installed on our system.

### What is Systemctl?

Systemctl is a command in Linux used to manage system services. It allows you to start, stop, restart, enable, disable, and check the status of services, making it a crucial tool for controlling and monitoring system processes and daemons.

### What is Systemd?

Systemd is a system and service manager in Linux that handles the startup, management, and control of system processes and services. It's a replacement for the traditional System V init system and provides features like parallel startup, service dependencies, logging, and more.

### Some commands of Systemctl:

1. `systemctl start service-name`: Start a specific service.
    
2. `systemctl stop service-name`: Stop a specific service.
    
3. `systemctl restart service-name`: Restart a specific service.
    
4. `systemctl status service-name`: Check the status of a service.
    
5. `systemctl enable service-name`: Enable a service to start at boot.
    
6. `systemctl disable service-name`: Disable a service from starting at boot.
    
7. `systemctl list-units --type=service`: List all active services.
    
8. `systemctl list-unit-files --type=service`: List all available services.
    

Note: To enable all these services you need to have admin rights.

### Systemctl Tasks:

1. check the status of the Docker Service in your system
    

```plaintext
systemctl status docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698732336052/021987bd-23b6-4c40-8b12-3f8045706148.png?auto=compress,format&format=webp align="left")

1. stop the service, Jenkins
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698732412392/686870cb-8c48-4f4a-a3a0-996e1848cf5f.png?auto=compress,format&format=webp align="left")

you can see that the jenkins service is active on our system and now let's stop the Jenkins service

```plaintext
systemctl stop jenkins
systemctl status jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698732479945/395a2f2c-1a05-412d-b163-3d3e602aa455.png?auto=compress,format&format=webp align="left")

Congratulations 🎉 you have now understood the concepts of package manager and systemctl commands in Linux. You have also learned how to start and stop a service and also how to check the status of that service.

### Summary

Explains package management in Linux, specifically focusing on YUM/DNF, RPM, APT, and DNF package managers. It covers the basics of each package manager, including installation, removal, updates, and other common commands. The text also briefly introduces Docker and Jenkins installation processes and provides practical examples of using systemctl to manage system services.

In summary, package management is essential for installing, updating, and removing software packages in Linux. Various package managers like YUM/DNF, RPM, APT, and DNF are available, each with its own set of commands and functionalities. The text also introduces systemctl as a tool for managing system services.