---
title: "Very First CI/CD Project using Azure, Jenkins, and Docker"
seoTitle: "Building a CI/CD Pipeline Project."
seoDescription: "Making a DevOps CI/CD Project using Microsoft Azure, Jenkins and Docker."
datePublished: Mon Jul 03 2023 11:41:02 GMT+0000 (Coordinated Universal Time)
cuid: cljmsikx0000n09k2hftbe2vn
slug: first-cicd-project-using-azure-jenkins-and-docker
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688383887896/aaab81ee-8d67-41ff-bfba-be0d24de6a44.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1688384325143/848467ec-7440-400f-9eed-c124cb1b2a43.gif
tags: azure, devops, jenkins, ci-cd, wemakedevs

---

Okay, so hear me out! If you're learning DevOps, then you might have already gone through much of a hassle regarding what are the different software that we use in DevOps, what functions they perform, and what not! But, all this really didn't make sense right?

It is because you don't know how to run them all together, to achieve something. Let me help you to make sense of CI/CD. We are going to make a CI/CD Project!

But first, let's talk about, what is CI/CD.

## What is CI/CD?

CI/CD is an essential part of DevOps, in which we try to maximise the development time, by automating the Operations tasks. Such as testing, Code Delivery, Building, and Deployment. Let's break CI/CD into two parts, and you're guessing correctly, they're **CI** and **CD**.

**CI** stands for **Continuous Integration**. A good CI means, the new code changes to an app are regularly built, tested and merged to a shared repository. Continuous Integration ensures that the new code is "integrated" continuously.

Whereas, **CD** stands for **Continuous Delivery** OR **Continuous Deployment**. Many times these terms go hand-in-hand, but these are different. **Continuous Delivery** takes over during the final stages of **CI.** With Continuous Delivery, the software is built with a proper environment so that it can be deployed to production at any time. Then we can either trigger the deployment manually, or we can use something known as **Continuous Deployment.** Continuous Deployment ensures that the software is continuously deployed into production without the interference of humans (or with minimal interference).

It basically boils down to the following steps:

* Merging
    
* Building
    
* Testing
    
* Releasing/Deployment
    

Now there are many tools that can be used to build a successful CI/CD pipeline. But for this tutorial, we are going to use these:

* Git/GitHub
    
* Jenkins
    
* Microsoft Azure
    
* Docker
    

Let's go through each of the tools once to establish what are they going to contribute to our CI/CD Pipeline.

### Git/GitHub

For SCM (Source Code Management) we are going to use the most widely used tools Git and Github. Git is a Distributed VCS (Version Control System) and GitHub is the place where we can store our shared repository where all the code can be pushed to. If you're going through this blog, chance are that you are already familiar with Git/Github and SCM.

### Jenkins

One of the most important CI/CD tools. Jenkins is an Open-Source Automation tool that allows us to blend everything together.

### Microsoft Azure

To carry out this project, we need a virtual machine setup in the cloud. I have used Microsoft Azure for this project, but you can use any of the cloud services out there. A free AWS EC2 instance would work fine. We are just trying to get a Ubuntu VM running in the cloud so that we can build and deploy our source code on it.

### Docker

Lastly, we need to have a deployment environment. So for that, we are going to use Docker Container.

## Making the CI/CD Pipeline

The basic question is, for what project you are going to build a CI/CD Pipeline? For this blog, I'm using a simple NodeJS ToDo List Application (🔗: [https://github.com/harshit-sharma-gits/node-todo-cicd](https://github.com/harshit-sharma-gits/node-todo-cicd)) which I have forked from [https://github.com/LondheShubham153/node-todo-cicd](https://github.com/LondheShubham153/node-todo-cicd) and did some styling changes myself.

### Setting up the Ubuntu VM

Firstly we are going to set up our environment on the cloud. Heading on to **Microsoft Azure**, click on **Virtual Machine** that we intend to create.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688116906927/1e53d056-2004-4318-a9b5-dc78335c2e1f.png align="center")

Then we can choose **Create a Virtual Machine** to do the same:

While creating a Virtual Machine in Azure, remember these things:

* It is always good to have a separate resource group for every project. So make a new Resource group.
    
* Choose whatever region is closest to you. (This accounts for minimal latency)
    
* We are deploying a Ubuntu VM, so I have selected the **Ubuntu Server 20.04 LTS - x64 Gen 2** image. You can choose whatever is available.
    
* You need not to be very picky regarding the **size** of your VM. 1 CPU along with 2 GiB memory will work just fine for your use! (Again, you can also create a Free-tier AWS EC2 Instance)
    
* Under **Administrator account,** choose the Authentication type as **Password**. Then make your own username and password.
    
* Under **Inbound port rules,** make sure that you have **SSH (22)** selected so that you can connect to your VM using SSH (In the next step).
    
* Now hit **Review+Create.**
    

Pheww, your VM is now being created. It might take some time.

Now you should be able to see something like this: *(I've named my VM as* ***UbuntuTrainingVM****)*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688117870178/faefaec2-b8ae-42ed-988f-e4eea850931b.png align="center")

Now don't be flabbergasted by the looks of it. One thing I want you to note here is the Public IP of your VM. As for my VM, it is `20.24.139.71` **.**

Now we are ready to **log in to our VM** and install the required software on it. But how do we do that again?

We need an SSH Client to log in to our VM. [PuTTy](https://www.putty.org/) is something you can use to establish an SSH connection to your VM. Or else, you can use your **Terminal** to do the same. Just write the command in your terminal:

```powershell
ssh <USERNAME>@<PUBLIC IP OF VM> 
```

It will ask for the password, and you can enter it. Remember passwords don't appear when you write them in the terminal. Not even the Asterisks(\*)!

You should see something like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688118747997/26f09a4b-41af-4b64-bffe-78c1cb92657d.png align="center")

If you do, then congrats you have successfully logged in to your freshly created VM.

Now let's install Jenkins.

### Installing Jenkins on the VM

While in the terminal, you can use some commands to install and start Jenkins.

```bash
sudo apt update
```

```bash
sudo apt install openjdk-11-jre
```

```bash
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 
```

```bash
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install jenkins
```

This will install Jenkins on your VM. Now you can start withJenkins these commands:

```bash
sudo systemctl enable jenkins
```

```bash
sudo systemctl start jenkins
```

For checking the status of Jenkins:

```bash
sudo systemctl status jenkins
```

Now Jenkins is active, and you can access it on your browser by going to `<PUBLIC IP OF VM>:8080`. Or can you?

At this point, Jenkins would be running on your VM at port `8080` but you still can't access it. Why? Because port `8080` is not exposed to be accessed. You can expose it by going in the Networking Settings and adding an "Inbound security rule".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688145238269/2d98668a-ff33-4476-85d2-4c468c5b47d7.png align="center")

Make sure that the Destination port is 8080 (that's what you want to expose!) and Protocol is set to TCP.

Now if you go to `<PUBLIC IP OF VM>:8080` you can see Jenkins running there. Congrats!'

Now just make a user for Jenkins and you'll be good to go.

### Setting up SSH between your VM and GitHub Repo

For your Virtual Machine and Project Repository need to be connected, so that they can communicate with each other. One method to do it is via SSH. We have to generate SSH Key on our VM and then provide it on your GitHub.

Run the following command on your vm:

```bash
ssh-keygen
```

This command generates an SSH Key, which is placed the `.ssh` folder. When you go into this folder you can see, there are two files: `id_rsa` and `id_rsa.pub` .

The `id_rsa` is the Private key, and `id_rsa.pub` is the Public key. Use `cat` command to see the Public Key, and copy it. Now let's paste our Public SSH Key to our GitHub.

Open up the settings for your GitHub account and select the **SSH and GPG Keys** tab. Click on **New SSH Key** Button. *(Notice here I already have an SSH Key)*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381324017/8a86ac6f-3670-4259-b01e-043209566cf9.png align="center")

Just paste the **Public Key** there.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381410841/e095bb34-413b-4f3d-87f3-448689ee7d10.png align="center")

### Making a Job in Jenkins

Now let's create a job in Jenkins so that it can fetch and build our project. Give you Job a name and select **Freestyle Project** to start.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381561697/6c260086-141b-4dec-9029-c541d77523d6.png align="center")

Now for configuration:

* Make sure that GitHub Project is selected. Also provide the Repository URL there.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381672687/3e947d43-33f7-4c60-8c1a-1c24dd3da723.png align="center")
    
* For the SCM, provide the Repository URL again. Now let's setup the credentials.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381798008/cb4b4923-aa1e-4ba4-b002-a2f8e43482a0.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381949666/c6e14079-9ca7-43ce-98d2-89d28a2bd383.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688381994893/b5250e49-55ae-4b12-adb2-f97c8a0826a4.png align="center")
    
    Click on **Add** after copying your **Private SSH Key** here.
    
* Now select this credential.
    
* After this, scroll down to the bottom and hit **Save**. You have made your first Jenkins Job!
    

Your project must be setup in your VM now. In the folder:

`/var/lib/jenkins/workspace/node-todo-cicd/`

### Running your project

Open your VM Console and go into the above-mentioned folder.

Now this is a NodeJS Project, so must have some things installed on your VM. Follow these commands:

```bash
sudo apt install nodejs
```

```bash
sudo apt install npm
```

```bash
sudo npm install
```

(This command will download all the libraries which are used to run your project)

```bash
node app.js
```

Now your app must be running on the port `8000`.

Make sure to expose the port `8000` by going to **Add Inbound Port** again in Azure. Now if you go to `<PUBLIC IP OF VM>:8000` you can see the ToDo App running there!

### Dockerizing the Application

We have successfully run our project on our Azure Virtual Machine. But we need to dockerize it. And it is really easy!

Follow these commands:

```bash
sudo usermod -a -G docker $USER
```

*(Give your VM the permission to run docker)*

Now reboot your VM.

```bash
sudo usermod -a -G docker jenkins
```

*(Give Jenkins the permission to run docker, we will need it soon)*

Reboot your VM again, and restart Jenkins also.

We can build and run the Docker container via the Command Line, but let's do it with Jenkins!

Open Jenkins &gt; YOUR\_PROJECT &gt; Configuration &gt; Build Steps and paste the following commands in it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688383257877/1f2ba4f2-0d53-439f-96a2-1082f72ba311.png align="center")

```bash
docker build . -t node-todo-app
docker run -d --name node-app-container -p 8000:8000 node-todo-app
```

Hit save, and You're done with your Pipeline!

Click on **Build** in Jenkins, and wait for it to succeed.

If you want to automate it so that it will build whenever any change is pushed onto the Repository, you can use a **GitHub Webhook** for that.

Cheers! 🤜🤛

Thanks for reading this blog, please give me an Upvote if it helped.