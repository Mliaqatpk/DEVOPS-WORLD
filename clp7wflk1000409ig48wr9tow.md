---
title: "🅳🅰🆈 8: 🅳🅴🆅🅾🅿🆂 🅴🅽🅶🅸🅽🅴🅴🆁🆂' 🅶🆄🅸🅳🅴 🆃🅾 🅶🅸🆃 🅰🅽🅳 🅶🅸🆃🅷🆄🅱: 🅴🅽🅷🅰🅽🅲🅴 🅲🅾🅻🅻🅰🅱🅾🆁🅰🆃🅸🅾🅽 🅰🅽🅳 🅴🅵🅵🅸🅲🅸🅴"
datePublished: Tue Nov 21 2023 05:32:23 GMT+0000 (Coordinated Universal Time)
cuid: clp7wflk1000409ig48wr9tow
slug: 8
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700544608301/914afe49-b44f-470d-b2be-049436ec7943.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1700544715100/78300b79-c90d-4f64-9b93-3069a9b2d3f5.jpeg
tags: github, git, devops, 90daysofdevops, tws

---

### **What is Git?**

Git is a vital tool in modern software development, offering developers the power to track and manage changes to their code efficiently. Created by Linus Torvalds, Git ensures the integrity of software projects and allows for seamless collaboration. It's a distributed version control system (DVCS) that provides a historical record of all code changes, empowers developers to work offline, and simplifies the process of merging code contributions from various team members. Git's speed, security, and open-source nature make it a cornerstone of DevOps and software development, with platforms like GitHub enhancing collaboration and enabling continuous integration and deployment.

### Aspects of Git

1. **Version Control:** Git tracks changes to files over time, allowing developers to see the entire history of modifications to a project. This makes it easy to revert to previous states, track who made changes, and understand when and why changes were made.
    
2. **Distributed:** Git is distributed, meaning that each developer working on a project has a complete copy of the repository. This allows them to work offline, make changes, and then synchronize (push/pull) their changes with other team members' copies.
    
3. **Branching:** Git makes it simple to create branches or divergent lines of development. Developers can work on new features, bug fixes, or experiments in isolated branches, which can later be merged into the main project when they are ready.
    
4. **Collaboration:** Git facilitates collaboration among multiple developers. They can work on different branches and merge their changes into the main project. Git hosting platforms like GitHub, GitLab, and Bitbucket offer tools for code review, issue tracking, and collaboration.
    
5. **Speed and Efficiency:** Git is designed to be fast and efficient. It only tracks changes, not entire files, and it uses a snapshot-based approach, making operations like branching and merging quick.
    
6. **Security:** Git employs cryptographic hashing to ensure the integrity of data. Each commit is identified by a unique hash, and changes to the codebase can be verified using these hashes.
    
7. **Open Source:** Git is open source, which means it is freely available and has a large community of users and contributors. It is widely adopted and supported on various operating systems.
    

To summarize it in short we can say that With Git, you can keep a record of who made changes to what part of a file, and you can revert to earlier versions of the file if needed. Git also makes it easy to collaborate with others, as you can share changes and merge the changes made by different people into a single version of a file.

### What is GitHub?

GitHub is an essential web-based platform for developers, offering a collaborative space to efficiently manage software projects. Leveraging the powerful Git version control system, it supplements Git's capabilities with an intuitive web interface and robust collaboration tools. Explore the key features of GitHub below:

1. **Git Hosting:** GitHub is where you can store and share your code, making it accessible from anywhere.
    
2. **Web Interface:** GitHub provides an easy-to-use website for managing your code, eliminating the need for complex Git commands.
    
3. **Collaboration:** It allows multiple people to work together on a project, sharing their changes and ideas.
    
4. **Issue Tracking:** GitHub's built-in system helps you keep track of tasks, bugs, and feature requests.
    
5. **Code Review:** You can propose and review code changes before merging them into the main project.
    
6. **Continuous Integration:** GitHub integrates with testing and deployment tools for automated code testing.
    
7. **Community:** GitHub is a hub for developers to follow, contribute, and collaborate on various projects.
    
8. **Documentation:** You can document your project and create wikis to share information easily.
    

### What is Version Control?

Version control is like a time machine for your files. It keeps track of changes you make to your work, so you can go back in time if something goes wrong. It's really helpful when many people are working on the same project.

There are 2 types of version control that are mainly used they are

* Centralized version Control (CVS)
    
* Decentralized Version Control (DVCS)
    

### **Centralized Version Control:**

Centralized version control is like having a single, central hub where all your project's files and their histories are stored. Imagine a library where everyone borrows and returns books from the same place. Here's how it works:

1. **Central Repository:** There is a central server where all project files and their versions are kept. It's like the main library where all the books are stored.
    
2. **Checkout:** When a team member wants to work on a project, they "check out" a copy of the files from the central repository. It's like taking a book out of the library.
    
3. **Editing:** They can edit these files on their computer and save their changes.
    
4. **Commit:** Once they are done, they "commit" their changes back to the central repository. It's like returning the book to the library.
    
5. **Conflict:** If two people make changes to the same file at the same time, there can be conflicts that need to be resolved.
    

### **Distributed Version Control:**

Distributed version control is like having your copy of the entire library and being able to make changes. Each person has a library with all the books. Here's how it works:

1. **Local Copies:** Everyone has a complete copy of the project's files and their history on their computer. It's like having your library at home.
    
2. **Commit:** Every Team member can make changes and "commit" them to their local copy. It's like making notes or highlighting in your books.
    
3. **Push and Pull:** They can share their changes with others by "pushing" and "pulling" from each other's libraries. It's like sharing your book annotations with friends and borrowing their notes.
    
4. **Conflict Resolution:** If there are conflicts between changes, they can be resolved by merging the different versions.
    
5. **Backup:** Since everyone has a copy, there's a backup if the central repository or someone's computer crashes. It's like having copies of the books at different places.
    

Distributed version control gives each team member more independence and flexibility, while centralized control relies on a central hub for coordination.

### Why do we use a Distributed Version Control System over a Centralized Version Control System?

We use a Distributed Version Control System (DVCS) over a Centralized Version Control System (CVCS) for several reasons:

1. **Work Anywhere:** With DVCS, you can work on your code even without the internet, while CVCS often needs an internet connection.
    
2. **Speed:** DVCS is usually faster for common tasks like saving your changes, making new branches, and combining changes. CVCS can be slower because it relies on a central server.
    
3. **Backup:** In DVCS, everyone has a full copy of the project, so it's like having multiple backups. In CVCS, if the central server has problems, the project could be in trouble.
    
4. **Flexible Teamwork:** DVCS lets team members work on their own without causing trouble for others. You can even experiment with your code separately. CVCS requires more coordination to avoid conflicts.
    
5. **Branching and Merging:** DVCS makes it easier to create different versions of your code and merge changes. CVCS can be more complicated in this regard.
    
6. **Large Teams and Long Distances:** DVCS is better for big teams and when team members are far apart because everyone has their complete copy of the project.
    
7. **Security:** Even if the central server is hacked in DVCS, your work is safe on your computer. In CVCS, if the central server is compromised, it's riskier.
    

In summary, while both DVCS and CVCS have their use cases, DVCS provides more flexibility, resilience, and efficiency, making it a preferred choice for many modern software development teams, particularly those working on large and distributed projects.

* Sign up on GitHub
    
* Create a new repository in GitHub
    
* Clone a new repository on your local system
    
* Make some changes to a file in the repository and commit them to the repository using Git.
    
* Push the changes back to the repository on GitHub
    
    ### **How to do a basic git setup?**
    
    open your terminal and paste the following commands
    

```plaintext
git config --global user.name "your username"
git config --global user.email "your email"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700544358187/c131ed21-ef7e-4ded-9ba7-f3a56ddcbbee.jpeg align="center")

Create Repo

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700544381179/d9da7799-c15f-4b6c-ad65-a29b12d5c0e9.jpeg align="center")

Make Some changes and commit

```plaintext
git add *

# using * at the end will add everything to the stack to push to main repo
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700544391803/7c6774ec-3468-4a36-aa71-77f73fc7c07e.jpeg align="center")

```plaintext
git commit -m " Messeage/Comment" 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700544405611/3bcc7fe3-0bfa-4485-b38f-cae6218ea5d7.jpeg align="center")

```plaintext
git push orgin main 
```

Changes are Pushed to github

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700544415557/cc009853-6edd-4ecf-96fe-87da0aae87b6.jpeg align="center")