---
title: "🅳🅰🆈 10: Mastering Git and GitHub for DevOps Engineers: An Advanced Guide (Part 1)"
datePublished: Thu Nov 23 2023 04:59:22 GMT+0000 (Coordinated Universal Time)
cuid: clpaq4ujl000a08jx45rrcvnf
slug: 10-mastering-git-and-github-for-devops-engineers-an-advanced-guide-part-1
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1700715552941/abedf461-1c55-41a1-a9ac-5a4998407521.png
tags: github, git, 90daysofdevops, happy-learning, tws

---

GitHub is the main focus for many big companies and open-source project maintainers and contributors to showcase their contributions. Many people think Github is more of pulling requests and merging codes.

But that's not the case Github is more advanced than many people think. Today let's learn about a few more advanced concepts of GitHub such as

* Branching
    
* Revert & Reset
    
* Rebase & Merge
    

### What is Git Branching?

Think of Git as a tool that helps you keep track of changes in your code, like a time machine for your code. Branching is like creating a separate copy of your code that you can work on without affecting the original or main code.

Here's how it works:

1. **Main Branch (Master/Branch):** This is your main code, the one that's already working and stable. It's like the main story in a book.
    
2. **Creating a Branch:** When you want to work on a new feature, bug fix, or experiment with your code, you create a new branch. It's like writing a side story in the book, separate from the main story.
    
3. **Working in Your Branch:** You make changes in your branch, like adding new features or fixing a bug. These changes won't affect the main code because you're in your own branch.
    
4. **Switching Branches:** You can switch back and forth between the main branch and your branch, just like reading different parts of the book.
    
5. **Merging:** When you're happy with the changes you made in your branch and want to include them in the main code, you merge your branch back into the main branch. It's like adding your side story to the main story in the book.
    
6. **Conflict Resolution:** Sometimes, when merging, there might be conflicts if both the main branch and your branch have changed the same part of the code. You need to resolve these conflicts, just like editing a book to make sure everything flows smoothly.
    
7. **Deleting Branch:** After merging, you can delete your branch because it served its purpose, and its changes are now part of the main code. It's like removing the side story from the book since it's now part of the main story.
    

So, Git branching is like having multiple storylines in a book (your code) without messing up the main storyline. It helps you experiment and work on different things separately, and when they're ready, you can combine them into one cohesive story.

### What is Git Revert & Reset?

1. **Git Revert**:
    
    * Imagine you're working on a project and you make a mistake by committing some changes that you want to undo.
        
    * Git revert is like using an eraser on your changes. It creates a new commit that undoes the changes from a previous commit, but it doesn't remove the commit itself.
        
    * It's like saying, "I made a mistake, and I want to go back in time to fix it by creating a new change that cancels out the old one."
        
    * Other people working on the project won't be disrupted because the old commits still exist.
        
2. **Git Reset**:
    
    * Suppose you realize you made a mistake, and you want to completely remove a commit from the project's history.
        
    * Git reset is like a time machine that lets you go back and rewrite history. It erases commits and moves your branch pointer to a different point in the project's history.
        
    * It's like saying, "I want to pretend this mistake never happened, and I'm going to change the project's history to make it look like that."
        
    * Be careful with Git reset because it can disrupt collaboration if other people are also working on the project.
        

In simple language, Git revert is a way to undo a commit by creating a new one that cancels out the changes, while Git reset is a more powerful tool that lets you change the project's history by removing commits. Use Git revert for safer and collaborative undoing, and use Git reset with caution when you want to rewrite history.

### What is Git merge and rebase?

Git rebase and merge are two different ways to integrate changes from one branch into another in Git. Let me explain them in simple terms:

1. **Merge**:
    
    * Imagine you have a main road (main branch) and a side road (feature branch) that split from it.
        
    * When you want to bring the changes from the side road back onto the main road, you create a "merge." It's like adding a new lane to the main road that incorporates all the changes from the side road.
        
    * The side road still exists separately after the merge. It's like the side road is still there, but changes have been added to the main road.
        

**Key Point**: Merge keeps a clear history of both the main and feature branches but adds a merge commit to the history.

1. **Rebase**:
    
    * Instead of adding a new lane (like in merge), think of rebase as picking up your entire side road and placing it on top of the main road.
        
    * This makes it look like all the changes from the side road were made directly on the main road one after the other, without any additional merge commits.
        
    * The side road effectively disappears after a successful rebase; its changes are now part of the main road.
        

**Key Point**: Rebase creates a cleaner and linear history by "replaying" the changes on top of the main branch, but it can make the history less clear if used inappropriately.

In summary, merge preserves the history of both branches with a merge commit, while rebase creates a linear history by incorporating the changes from the feature branch onto the main branch as if they were made in sequence. The choice between them depends on your project's needs and your preference for how you want the history to look.

### Tasks

Add a text file called version01.txt inside the Devops/Git/ with “This is the first feature of our application” written inside. This should be in a branch coming from `master`, \[hint try `git checkout -b dev`\], switch to the `dev` branch ( Make sure your commit message will reflect as "Added new feature"). \[Hint use your knowledge of creating branches and Git commit

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715105345/b46e1c53-788f-4397-94d6-a1c5cfdd81c4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715139454/48e288fe-1e35-4dbc-bade-06763818f523.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715145756/598cbcac-d80d-4acb-9d18-c13c4c6a01ac.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715151128/a6721441-416e-439a-a839-c11ab0f69543.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715155518/b02caa4e-c6d3-47dd-a882-38e4dcd0fff7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715159714/fb0a8f13-c67e-49a2-a8e0-183069374082.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700715164370/45673453-5b28-4375-90f4-3bbe9a62cee5.png align="center")