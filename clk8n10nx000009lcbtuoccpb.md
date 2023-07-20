---
title: "BASH Script to take backup of a folder whenever something is changed in it"
seoTitle: "Write a BASH Script to take backup of a directory"
seoDescription: "This BASH Script is going to watch over the directory and when any change happen (ADD | MODIFY | MOVE | DELETE) it is going to back up the directory."
datePublished: Tue Jul 18 2023 18:38:20 GMT+0000 (Coordinated Universal Time)
cuid: clk8n10nx000009lcbtuoccpb
slug: bash-script-to-take-backup-of-a-folder-whenever-something-is-changed-in-it
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689705377654/fc5f7e91-9403-4cf4-9d97-884d9782d181.png
tags: linux, bash, devops, script, wemakedevs

---

Let me clarify the problem statement a little bit before we move on to solve it!

We have a directory that we need to back up periodically. But periodically here means that whenever something is **added**, **modified**, **moved**, or **deleted** from this directory the backup needs to happen!

Please note here backup simply means copying the content of the directory to some other location. So we can use the `rsync` utility which can handle this task very effectively. Read more about it \[here.\]([https://www.geeksforgeeks.org/rsync-command-in-linux-with-examples/](https://www.geeksforgeeks.org/rsync-command-in-linux-with-examples/))

Now how can we watch the directory so that we can trigger backup whenever anything has changed in it? 🤔

After spending some time on StackOverflow, I got to know about `inotifywatch`. It is a utility that can do just that for us! So let's install it first:

```bash
sudo apt install inotify-tools
```

### Writing the script

Now we are ready to write our bash script, and here it is:

```bash
#!/bin/bash

################################################################################
##             WRITTEN BY - HARSHIT SHARMA <harshits908@gmail.com>            ##
## This script is going to montior a directory and backup it whenever any     ##
## change is made to this directory.                                          ##
## Two tools are used here:                                                   ##
## inotifywait (A handy utility for monitoring the folder for any event)      ##
## rsync (A utility to copy files to another location, backup basically)      ##
## BEFORE USING THIS SCRIPT MAKE SURE YOU HAVE BOTH THESE UTILITIES INSTALLED ##
################################################################################

# Provide the paths here for your use-case
originDir="/path/to/the/watched/directory/"
destinationDir="/path/to/the/destination/directory/"
logfile="/path/to/your/logfile"

# Watching the Directory using inotifywatch
inotifywait -m -r -e modify,create,delete,move "$originDir" |
while read path action file; do

        # Trigger - Change Detected
        currentTime=$(date +"%T")
        echo "Change detected in the database @ $currentTime , Making a backup!" >> "$logfile"

        # Taking the backup
        rsync -avz $originDir $destinationDir --delete >> "$logfile"

        echo "Backup Complete!" >> "$logfile"

done
```

### **Running the script**

Save the script as [`script.sh`](http://script.sh)

Give the permission to execute:

```bash
sudo chmod +x ./script.sh
```

Execute the script:

```bash
./script.sh
```

And the watches will be set!

### **Conclusion**

So that was it for this blog! Feel free to use this script. ✅

If you find this somewhat informative, please like this blog! ✨

Connect with me:

🔗 **LinkedIn:** [**https://www.linkedin.com/in/harshit-sharma--/**](https://www.linkedin.com/in/harshit-sharma--/)

🔗 **My YouTube Channel:** [**https://www.youtube.com/c/CoderBuddy?sub\_confirmation=1**](https://www.youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [**https://github.com/harshit-sharma-gits**](https://github.com/harshit-sharma-gits)