---
title: "How to send an email from Linux Terminal?!"
seoTitle: "Send Email from the Linux Terminal using SMTP"
seoDescription: "Send an email from your Ubuntu Linux Terminal using the Simple Mail Transfer Protocol by ssmpt cli utility."
datePublished: Tue Jul 25 2023 17:27:12 GMT+0000 (Coordinated Universal Time)
cuid: clkikkhxo000g09l436xfc4vh
slug: how-to-send-an-email-from-linux-terminal
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690305918549/a7a806f7-6d0c-4afa-8df6-4587724b0fa4.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690305968622/4a2d46e8-4a8c-4b11-954e-44dc5da0ee1c.gif
tags: linux, devops, linux-for-beginners, linux-basics, wemakedevs

---

As you can see, we are going to send an email from our Ubuntu Terminal. Let's do it then!

We are going to use the `ssmtp` CLI Utility. It is easily installed by running:

```bash
sudo apt install ssmtp
```

After our SMPT Utility has been installed, we need to do some changes to the `/etc/ssmtp/ssmtp.conf` configuration file.

Let's open this file using nano:

```bash
sudo nano /etc/ssmtp/ssmtp.conf
```

Make this file like this:

```bash
#
# Config file for sSMTP sendmail
#
# The person who gets all mail for userids < 1000
# Make this empty to disable rewriting.
# root=postmaster

# The place where the mail goes. The actual machine name is required no
# MX records are consulted. Commonly mailhosts are named mail.domain.com
mailhub=smtp.gmail.com:587

AuthUser=YOUR_EMAIL_HERE
AuthPass=YOUR_APP_PASSWD_HERE
UseTLS=YES
UseSTARTTLS=YES

# Where will the mail seem to come from?
rewriteDomain=gmail.com

# The full hostname
hostname=test

# Are users allowed to set their own From: address?
# YES - Allow the user to specify their own From: address
# NO - Use the system generated From: address
FromLineOverride=YES
```

One **important thing to note here** is that you should not use your account's original password for this. Instead you have to make an App Password for this to work.

Head on to this [link](https://myaccount.google.com/apppasswords) to setup an app password for your **Google Account**.

After this, you can easily send emails from your command line!!

```bash
ssmpt RECIPIENT_EMAIL_HERE
```

Hit enter, then type out:

```bash
Subject: SUBJECT_FOR_THE_MAIL_HERE
```

Hit enter, then you can type out the content of your email:

```bash
Sample content of the email
```

Now hit enter, and press Ctrl+D to send the email.

That's it for sending email from your Linux Terminal. Hope it helps!

Connect with me:

🔗 **LinkedIn:** [**linkedin.com/in/harshit-sharma--**](http://linkedin.com/in/harshit-sharma--)

🔗 **My YouTube Channel:** [**youtube.com/c/CoderBuddy?sub\_confirmation=1**](http://youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [**github.com/harshit-sharma-gits**](http://github.com/harshit-sharma-gits)