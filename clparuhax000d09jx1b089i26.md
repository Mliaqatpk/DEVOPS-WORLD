---
title: "🅳🅰🆈 11:Mastering Git and GitHub for DevOps Engineers: An Advanced Guide (Part 2)"
datePublished: Thu Nov 23 2023 05:47:17 GMT+0000 (Coordinated Universal Time)
cuid: clparuhax000d09jx1b089i26
slug: 11mastering-git-and-github-for-devops-engineers-an-advanced-guide-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700718402954/889fe3a9-166e-45ae-bf1f-dde43ddeb20f.png
tags: linux, github, git, tws

---

In part 1 we have covered with few concepts such as Git branching, Git revert, Git reset and many other concepts. Today let us see some more advanced concepts such as stash and resolving conflicts etc.

### What is Git Stash?

Git stash is a command that allows developers to temporarily save changes that have not been committed to a branch. It's particularly useful when you're working on a specific task but need to switch to another branch to address an urgent bug or tackle a different feature. Stashing your changes allows you to switch branches without committing to half-finished work.

To use Git stash, you first create a new branch and make some changes to it. Then you can use the command git stash to save those changes. This will remove the changes from your working directory and record them in a new stash. You can apply these changes later. git stash list command shows the list of stashed changes.

You can also use git stash drop to delete a stash and git stash clear to delete all the stashes.

### How to Use Git Stash:

Using Git stash is straightforward. Here's a step-by-step guide to get you started:

1. Make sure your current branch is clean (no uncommitted changes).
    
2. Use the command: `git stash` to save your current changes.
    
3. You can stash multiple times, creating a stack of stashes.
    
4. After stashing, your working directory is clean, and you can switch branches or perform other tasks.
    
5. To retrieve your stashed changes, use `git stash apply` followed by the stash reference (e.g., `git stash apply stash@{0}`).
    
6. Optionally, you can use `git stash pop` to retrieve the changes and remove the stash from the stack.
    

### Cherry-pick

Cherry-pick is a Git feature that allows you to choose and apply specific commits from one branch to another. This feature can be particularly useful when you need to pull in changes or fixes from another branch or repository without merging the entire branch.

### How to Cherry-Pick a Commit in GitHub:

Using cherry-pick in GitHub is straightforward. Here's a step-by-step guide:

1. First, ensure you are on the branch where you want to apply the cherry-picked commit.
    
2. Navigate to the repository on GitHub.
    
3. Locate the commit you want to cherry-pick and click on it to view the commit details.
    
4. Click on the "Copy SHA" button to copy the commit's unique identifier.
    
5. Return to your local repository and run the following command:
    

```plaintext
shellCopy codegit cherry-pick <commit-SHA>
```

Replace `<commit-SHA>` with the SHA-1 hash of the commit you copied.

1. Git will attempt to apply the changes from the selected commit to your current branch. If there are any conflicts, you'll need to resolve them manually.
    
2. After resolving conflicts, commit the changes.
    
3. Finally, push the updated branch to your remote repository on GitHub.
    

### Resolving Conflicts

Conflicts can occur when you merge or rebase branches that have diverged, and you need to manually resolve the conflicts before git can proceed with the merge/rebase. git status command shows the files that have conflicts, git diff command shows the difference between the conflicting versions and git add command is used to add the resolved files.

### Task 1

* Create a new branch and make some changes to it.
    

```plaintext
    git checkout -b feature
    git branch
    vim version01.txt
    git add .
```

Use git stash to save the changes without committing them.

```plaintext
    git stash
    git status
```

Switch to a different branch, make some changes and commit them.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718131333/e9bb3f75-c0ce-425b-9818-5533aa1b6826.png align="center")

Use git stash pop to bring the changes back and apply them on top of the new commits.

# **🔶 Task-02**

* In version01.txt of the development branch add the below lines after “This is the bug fix in the development branch” that you added in Day10 and reverted to this commit.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718292437/529ddcd2-12fb-49c3-8d53-279e2e4394ec.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718316242/519a7f81-fa9c-4881-8954-6ac724769b77.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718336259/ca34b95a-85d8-4c61-8f4d-21b1f5978eb7.png align="center")

# **🔶 Task-03**

* In the Production branch Cherry picked Commit “Added feature2.2 in development branch” and added the below lines in it.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718352201/ef6f994c-f978-4f0b-b765-00c4644b8b49.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700718361004/85646351-f76b-4c7d-8f89-6e0f57fd307a.png align="center")