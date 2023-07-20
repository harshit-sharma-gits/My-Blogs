---
title: "A guide to SCM: Git and GitHub"
seoTitle: "Introductory guide to Git and GitHub"
seoDescription: "Learn about Source Code Management (SCM) by Git and GitHub"
datePublished: Wed Jul 05 2023 13:00:02 GMT+0000 (Coordinated Universal Time)
cuid: cljpq7vhk001i0amfgd1ieis0
slug: a-guide-to-scm-git-and-github
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688561359262/4267e2eb-f6f0-483a-b57b-0fd4fde5d7af.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1688561985294/27e698db-4e7d-47b4-afe1-b035a642237c.gif
tags: github, git, devops, hashnode, wemakedevs

---

## SCM: Source Code Management

Source code management (SCM), also known as version control and revision control, is the practice of tracking and managing changes made to software source code throughout its lifecycle. It involves using specialized tools and techniques to keep track of every modification made to the source code files of the project.

Some benefits of version control systems include:

1. Makes it easy to compare older versions of the source code and make corrections where necessary.
    
2. Saves developers a lot of time while working.
    
3. Makes it easier to collaborate with other devs efficiently while working on the same project together.
    
4. Easily track changes made to code, including who made the changes and when.
    
5. Makes recovery of a previous version of a code possible.
    
6. Minimizes the chances of errors and improves conflict resolution.
    
7. Speeds up the development process and increases productivity.
    
8. Makes it possible for devs to work from anywhere.
    
9. Different devs can work independently on their working copy in their branches before merging with the main file, after validation.
    
10. Provides an overview of the work done over a period.
    
    ![5 Version Control Software (Source Code Management Tools)](https://media.licdn.com/dms/image/C4D12AQFO7AwRh6ytUA/article-cover_image-shrink_600_2000/0/1616360367059?e=2147483647&v=beta&t=wrgpgoGbX1524p1_Z2ozdxy7dgNhkTGsH4YhGnRiXaA align="left")
    

## Types of VCS (Version Control Systems)

### **Local version control system**

This is the simplest type of version control system. It has a local repository on your computer, where it stores all changes made to a file (revision history) in a patch. To see all the changes made to the file, you will need to add up all the patches before you can access it.

### **Centralized version control system**

In this system, the main server or central repository stores all files and provides access to multiple branches for different people in the development team. The central server tracks all the changes, information, commit messages, and users in the project. Every team member can change their working copy in their branch before merging with the main branch after validation.

The downside is that if anything happens to the central repository or main server without proper backup, you can lose the entire history and everything you and the team have been working on.

### **Distributed version control system**

This system solves the major problems of centralized control systems.

In decentralized or distributed version control systems, there are several repositories. Every team member has a personal copy of the files and complete history in their local repository.

Here, there is no need to worry about the main repository crashing because everyone on the project will have a backup of the source file(s), so if anything happens, any team member can easily send a copy to members or update the central files repository.

## Git

![How to set up access to private Git™ repositories – Wissenschaft Integrated  Limited](https://www.wissenschaft.com.ng/wp-content/uploads/2021/02/git_banner-1024x265.png align="left")

Git is the most widely used open-source **Distributed Version Control System** worldwide. It enables programmers to manage code repositories, track changes, and collaborate with teams in real-time.

### Essential Git commands

* `git init`: Initializes a new Git repository in the current directory.
    
* `git clone [repository]`: Creates a local copy of a remote repository.
    
* `git add [file(s)]`: Adds file(s) to the staging area, preparing them for the next commit.
    
* `git commit -m "[message]"`: Records the changes in the staging area and creates a new commit with a descriptive message.
    
* `git push`: Pushes local commits to a remote repository, updating the remote branch with the latest changes.
    
* `git pull`: Retrieves and merges the latest changes from a remote repository into the local branch.
    
* `git branch:` Lists all branches in the repository.
    
* `git checkout [branch]`: Switches to the specified branch.
    
* `git merge [branch]`: Integrates changes from the specified branch into the current branch.
    
* `git status`: Shows the current state of the repository, including modified, staged, and untracked files.
    

### Sample Git Workflow

![5 types of Git workflows that will help you deliver better code | Buddy:  The DevOps Automation Platform](https://buddy.works/blog/images/gitflow.png align="left")

Let's have a sample workflow on How to use Git in your project. We will try to keep it as simple as possible.

* **Installing Git**
    
    Before starting with Git, you must have it installed on your system. You can install it by following the instructions given on the official Git site: [Git - Downloads (](https://git-scm.com/downloads)[git-scm.com](http://git-scm.com)[)](https://git-scm.com/downloads)
    
* **Configuring Git**
    
    After installing Git, it's essential to configure your identity, including your name and email address. Open a terminal or command prompt and enter the following commands, replacing the placeholders with your information:
    
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "your.email@example.com"
    ```
    
* **Verifying the Installation**
    
    To verify that Git has been installed successfully, open a terminal or command prompt and run:
    
    ```bash
    git --version
    ```
    
    If your installation was successful, then you will get the version number for the Git installation.
    
* Initializing the repository
    
    Now you have Git installed, let's use it on a project. We can initialize the repository with Git using this command:
    
    ```bash
    git init
    ```
    
* Now you may proceed to add the files for your project. After this, it's time to do your first commit. Let's add the files to the staging area and commit them using these commands:
    
    ```bash
    git add .
    ```
    
    *(This is going to add all of your files to the staging area)*
    
    ```bash
    git commit -m "YOUR_COMMIT_MESSAGE_HERE"
    ```
    
    Wow, you have made your first commit. You can similarly add more commits to your repo. And if you want to take a look on the commits you've made, you can use this command:
    
    ```bash
    git log
    ```
    
    *(This is going to list all your commits along with their commit IDs and Messages)*
    

## GitHub: Basics

![Vulnerable GitHub Actions Workflows Part 1: Privilege Escalation Inside  Your CI/CD Pipeline](https://www.legitsecurity.com/hs-fs/hubfs/Frame%201%20(1).png?width=1575&name=Frame%201%20(1).png align="left")

GitHub, a web-based hosting service built on top of Git, offers a powerful platform for version control, collaboration, and project management.

### **Forking a Repository**

To get started, visit the repository's URL ([**https://github.com/dotslashbit/git\_and\_github\_tutorial/tree/main**](https://github.com/dotslashbit/git_and_github_tutorial/tree/main)) and click on the "Fork" button in the top-right corner. This creates a copy of the repository under your GitHub account, allowing you to freely experiment without affecting the original project.

### Cloning a Repository

Once you've forked the repository, you'll want to work on it locally. Clone the repository using the following command in your terminal:

```bash
git clone https://github.com/<your-github-username>/git_and_github_tutorial.git
```

Replace `<your-github-username>` with your actual GitHub username. This command downloads a copy of the repository to your local machine.

### Making Changes

Open the repository in your preferred code editor. In the cloned repository, locate the [`README.md`](http://README.md) file and add your name to the list of contributors. Save the changes.

### Committing Changes

After making modifications, stage and commit the changes using the following commands:

```bash
git add README.md
git commit -m "Add my name to the contributors list"
```

### Pushing Changes to Your Repository

Push the committed changes to your forked repository on GitHub:

```bash
git push origin main
```

### Creating a Pull Request

* Now that the changes are pushed to your forked repository, you can open a pull request to propose merging those changes into the original repository.
    
* Visit your repository on GitHub and click on the "New pull request" button. Select the main repository (`dotslashbit/git_and_github_tutorial`) as the base branch and your forked repository as the compare branch.
    
* Provide a descriptive title and comment, then click on "Create pull request" to submit it.
    

### Reviewing and Merging a Pull Request

The project maintainers will review your pull request, provide feedback, and discuss any necessary changes. Once approved, they can merge your changes into the main repository.

Connect with me:

🔗 **LinkedIn:** [**https://www.linkedin.com/in/harshit-sharma--/**](https://www.linkedin.com/in/harshit-sharma--/)

🔗 **My YouTube Channel:** [**https://www.youtube.com/c/CoderBuddy?sub\_confirmation=1**](https://www.youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [**https://github.com/harshit-sharma-gits**](https://github.com/harshit-sharma-gits)