---
title: "Day 5: "Mastering Linux Scripting: Creating Directories and Backups with Bash""
datePublished: Thu Nov 09 2023 08:37:46 GMT+0000 (Coordinated Universal Time)
cuid: cloqxrsn700050al60s9r05v5
slug: day-5-mastering-linux-scripting-creating-directories-and-backups-with-bash
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699504532022/51dc93cc-a605-4a64-b1e6-a5bbd1e965bb.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1699519043438/8fb2ca99-4622-471a-a37d-32663f71efdf.png
tags: bash, devops, 90daysofdevops, tws

---

## How Many Ways To Create Directory In Linux ?

### **Linux mkdir Command Syntax**

## **How to Create a New Directory**

To create a directory in Linux, pass the directory’s name as the argument to the `mkdir` command. For example, to create a new directory `newdir`, you would run the following command:

```bash
mkdir [OPTION] [DIRECTORY]
```

You can verify that the directory was created by listing the contents using the [`ls` command](https://linuxize.com/post/how-to-list-files-in-linux-using-the-ls-command/) :

```plaintext
mkdir newdir
```

When providing only the directory name, without the full path, it is created in the current working directory.

```plaintext
ls -l
```

```bash
ouput
drwxrwxr-x 2 username username 4096 Jan 20 03:39 newdir
```

The current working directory is the directory from which you are running the commands. To change the current working directory, use the [`cd`](https://linuxize.com/post/linux-cd-command/) command.

To create a new directory in another location, you’ll need to provide the parent directory’s absolute or relative file path. For example, to create a new directory in the `/tmp` directory you would type:

```plaintext
mkdir /tmp/newdir
```

If you try to create a directory in a parent directory where the user does not have sufficient permissions, you will receive `Permission denied` error:

```plaintext
mkdir /root/newdir
```

```bash
mkdir: cannot create directory '/root/newdir': Permission denied
```

## **How to Create Parent Directories**

A parent directory is a directory that is above another directory in the directory tree. To create parent directories, use the `-p` option.

Let’s say you want to create a directory `/home/Malik/Music/Rock/Gothic`:

```bash
mkdir /home/Malik/Music/Rock/Gothic
```

If any of the parent directories don’t exist, you will get an error as shown below:

```bash
mkdir: cannot create directory '/home/Malik/Music/Rock/Gothic': No such file or directory
```

Instead of creating the missing parent directories one by one, invoke the `mkdir` command with the `-p` option:

```bash
mkdir -p /home/linuxize/Music/Rock/Gothic
```

When the `-p` option is used, the command creates the directory only if it doesn’t exist.

```bash
mkdir newdir
```

If you try to create a [directory that already exists](https://linuxize.com/post/bash-check-if-file-exists/) and the `-p` option is not provided, `mkdir` will print `File exists` error:

```bash
mkdir: cannot create directory 'newdir': File exists
```

## **How to Set Permissions when Creating a Directory**

To create a directory with specific permissions, invoke the `mkdir` commanf with the `-m` (`-mode`) option. The syntax for assigning permissions is the same as with the [`chmod`](https://linuxize.com/post/chmod-command-in-linux/) command.

```bash
mkdir -m 700 newdir
```

In the following example, we’re creating a new directory with `700` permissions, which means that only the user who created the directory will be able to access it:

When the `-m` option is not used, the newly created directories usually have either `775` or `755` permissions, depending on the [`umask`](https://linuxize.com/post/umask-command-in-linux/) value.

## **How to Create Multiple Directories**

To create multiple directories, specify the directories’ names as the command arguments, separated by space:

```bash
mkdir dir1 dir2 dir3
```

The `mkdir` command also allows you to create a complex directory tree with one command:

```bash
mkdir -p Music/{Jazz/Blues,Folk,Disco,Rock/{Gothic,Punk,Progressive},Classical/Baroque/Early}
```

## **Automate With Bash Scripting**

Bash script automation is like teaching your computer to do boring, repetitive tasks all by itself. It's like a super-smart assistant that follows your instructions. This means you can make your computer automatically do things like making copies of important stuff, keeping your computer healthy, and handling complicated data work. By using these automated scripts, people who manage computers can spend their time on more interesting and important jobs. It's like having a reliable helper that ensures things get done correctly, which is super helpful in the fast-paced world of technology.

with the above Bash script, you can easily automate the work of creating directories in Linux.

Now, let's see how this script works. To run this Bash script you have to give it executable permission.

### **Why give executable permission to Bash Scripts?**

When we create Bash scripts in Linux they come by default with just read and write permission. To make them executable as well, we have to use a certain command to them permission to become executable.

### **How to make the Bash Script executable?**

making the bash script executable is simple you just have to use the chmod command and write the permission for the file.

Now you can see that after using the chmod command the color of the shell script has changed to a different color which means that the script can be executed now.

here, 777 has its significance too. We will learn that in the upcoming posts.

Now that you have made the script executable. you can run it easily with the shell or the terminal of your Linux Operating System.

To run the script you can use

```bash
malik@DNS:~/scripts$ bash crdir.sh
```

This will execute the script and ask you for the inputs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699518948712/cc7214f7-129e-4e8a-9640-23bf09ae4a0f.png align="center")

You can see that the script has been executed. Now let's see if the script worked or not.

This Bash script is designed to create a series of directories with names based on user input. Let's break down the code step by step:

1. `# take the user input`: This is a comment indicating the purpose of the following code.
    
2. `echo "Enter the base name of the directory"`: This line displays a message asking the user to input the base name for the directories they want to create.
    
3. `read name`: The `read` command is used to capture the user's input and store it in a variable called `name`. This variable will be used as the base name for the directories.
    
4. `echo "Enter the starting number"`: This line asks the user to input the starting number for the series of directories.
    
5. `read start`: Similar to the previous step, the `read` command captures the user's input and stores it in a variable called `start`.
    
6. `echo "Enter the ending number"`: This line prompts the user to input the ending number for the series of directories.
    
7. `read end`: Again, the `read` command captures the user's input and stores it in a variable called `end`.
    
8. `# for loop for automation`: This comment explains the purpose of the upcoming for loop.
    
9. `for(( i=start; i<=end; i++ ))`: This is the beginning of a for loop that iterates from the `start` number to the `end` number. It will create directories with names based on the user's input.
    
10. `{`: The curly brace `{` denotes the start of a block of commands that will be executed for each iteration of the loop.
    
11. `mkdir $name$i`: This command creates a directory with a name composed of the base name (`$name`) and the current value of `i`. For example, if the user input "mydir" as the base name, and the loop is currently at `i=1`, it will create a directory named "mydir1."
    
12. `}`: The closing curly brace `}` marks the end of the block of commands executed for each iteration of the loop.
    
13. `done`: This signals the end of the for loop.
    
14. `echo "Directories have been created..."`: Finally, this line prints a message indicating that the directories have been successfully created.
    

In summary, this script takes user input for a base directory name, a starting number, and an ending number. It then uses a for loop to create a series of directories with names based on the user's input.

Now that we have completed the first task let's move to the other task which is to write a bash script to take a backup of the progress we have made till now.

### Why Taking Backup is Important in Linux

Linux backup is like making a copy of your important stuff on your computer. It's important because if something goes wrong, like your computer breaks or you accidentally delete something, you can get your stuff back from the copy. It's like a safety net for your computer so you don't lose your important things.

### Bash Script to take Backup

```bash
  GNU nano 6.2                                                                              backup.sh
#!/bin/bash
srcdir=/home/malik/scripts
dstdir=/home/malik/backups
timestamp=$(date "+%Y-%m-%d-%H-%M-%S")
echo " Taking Backup for  time stamp " $timestamp
final_File=$dstdir/Scrips-bakcup-$timestamp.tgz
tar czf $final_File -C $srcdir .
echo " Backup Completed..."






```

This Bash script is designed to create a backup of a directory. Let's break down the code step by step:

1. `#!/bin/bash`: This is called a shebang, and it indicates that the script should be interpreted by the Bash shell.
    
2. `Backup_dir="/home/sh/Desktop/Devops"`: This line defines the source directory that you want to back up. In this case, it's "/home/sh/Desktop/Devops."
    
3. `Backup="/home/sh/Desktop/Backup"`: This line specifies the destination directory where the backup will be stored. It's "/home/sh/Desktop/Backup" in this script.
    
4. `date=$(date + "%d-%b-%y")`: This line uses the `date` command to obtain the current date and store it in a variable called `date`. The format for the date is set to day-month-year, such as "09-nov-23."
    
5. `cp -r $Backup_dir $Backup/$date`: This is the command that creates the backup. It uses the `cp` command with the `-r` flag to copy the contents of the source directory (`$Backup_dir`) to the destination directory (`$Backup`) and appends the current date to the destination path, creating a folder with the backup date.
    
6. `echo "Backup created in $Backup/$date"`: Finally, this line simply prints a message indicating where the backup was created, using the values of the variables for the source directory, destination directory, and the current date.
    

So, in summary, this script makes a backup of the "Devops" directory on the user's desktop and stores it in a "Backup" directory with the current date as a subfolder within "Backup."

### Summary

In the world of technology, Bash scripting is like having a smart assistant for your computer. It helps you automate repetitive tasks, making your work more efficient and error-free. We've started with the basics and now we're diving into more advanced scripting.

One cool thing we can do with Bash scripts is create a bunch of folders without clicking around. You just tell the script a few things, like what to name the folders and how many you want, and it does the work for you. This is super helpful, especially when you have a lot of folders to create.

Another important thing we've learned is how to take a backup. Think of it like making a copy of your important files, so if something bad happens, you can get them back. It's like a safety net for your computer.

In the end, Bash scripting and automation are like having a handy assistant who does tasks for you, making your work easier and more reliable in the fast-paced world of tech.