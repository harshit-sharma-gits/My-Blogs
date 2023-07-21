---
title: "Linux File System: EXPLAINED"
seoTitle: "Complete Linux File Systems Explained"
seoDescription: "This blog will cover through all the folders present at the root directory at a Linux System."
datePublished: Fri Jul 21 2023 12:16:05 GMT+0000 (Coordinated Universal Time)
cuid: clkcjozv7000609mc6dnj9s9v
slug: linux-file-system-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689940621876/c5d8edee-a916-499a-b074-33c704e907a6.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689941645834/6a883fd5-5ab9-424c-b53d-0982ea0ffce5.gif
tags: linux, devops, linux-for-beginners, devops-articles, wemakedevs

---

## Introduction

Linux, as a robust and open-source operating system, powers a vast array of devices, from servers to smartphones. One of the key elements that make Linux unique is its well-organized file structure. Understanding the Linux file structure is essential for both beginners and seasoned users alike. In this blog, we will delve into the directories present in a Linux system, explaining their purpose and functionality.

## The Linux Directories

Look below, there are SO MANY! 👇

We will look at the most common ones that are found in mostly all distributions.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689940455328/83cecf77-c357-47d7-8eb8-405e9a926b64.png align="center")

1. ### / (Root Directory):
    

The root directory(`/`) is the top-level directory in the Linux file system. It contains all other directories and files. As the starting point for the entire file structure, the root directory is designated as '`/`'. In Linux, the concept of a root directory is similar to the `C:\` drive in Windows.

1. ### /bin (Binary Files):
    

The `/bin` directory houses essential binary executable files that are crucial for basic system functioning. These binary files are commonly used by all users and are available in their default search path. Some common commands stored in /bin include ls (list directory contents), `cp` (copy files), and `mv` (move or rename files).

1. ### /boot (Boot Files):
    

The `/boot` directory contains files related to the booting process of the Linux system. It stores the Linux kernel, which is the core of the operating system, along with the initial RAM disk (initrd), which holds temporary files used during the boot process. Additionally, boot loader configurations like GRUB (Grand Unified Bootloader) are stored in this directory.

1. ### /dev (Device Files):
    

The `/dev` directory contains special files known as device files. These files represent hardware devices connected to the system, such as hard drives, USB ports, and input/output devices (e.g., keyboards and mice). When applications or users interact with these device files, they are essentially communicating with the corresponding hardware devices.

1. ### /etc (System Configuration Files):
    

The `/etc` directory houses system-wide configuration files that control various aspects of the Linux system. These configuration files determine how various applications and services behave. Some examples include network configurations (e.g., `/etc/network/interfaces`), user account information (e.g., `/etc/passwd` and `/etc/group`), and software settings (e.g., `/etc/apt/sources.list` for package repositories).

1. ### /home (User Home Directories):
    

The `/home` directory contains individual subdirectories for each user on the system. These subdirectories serve as personal home directories for users, where they can store their files, documents, and user-specific configuration files. For example, if the username is 'john,' the home directory for user 'john' would be '`/home/john`.'

1. ### /lib (Library Files):
    

The `/lib` directory contains shared library files that are essential for the proper functioning of executables stored in `/bin` and `/sbin`. Shared libraries contain code that multiple programs can use, reducing the overall size of the programs on the system. These libraries are often referred to as "shared objects" and have file extensions such as .so (shared object).

1. ### /media (Removable Media):
    

The `/media` directory serves as a mount point for removable media, such as USB drives and optical discs. When you insert a USB drive or a CD/DVD, Linux automatically mounts it to the /media directory, allowing you to access its contents.

1. ### /mnt (Temporary Mount Point):
    

The `/mnt` directory is used as a temporary mount point for manually mounted file systems. Users can mount additional file systems, such as network shares or external storage devices, on this directory to access their contents.

1. ### /opt (Optional Software):
    

The `/opt` directory is used for installing optional software packages that are not part of the standard Linux distribution. Third-party applications or large software packages may be installed in this directory to keep them separate from the system's default files.

1. ### `/proc` (Process Information):
    

The /proc directory is a virtual file system that provides real-time information about the current processes running on the Linux system. Each process on the system has a corresponding directory within /proc, with numeric names. These directories contain files that expose various attributes of the processes, such as memory usage, file descriptors, and more. Interacting with these files allows users and system administrators to view and modify kernel parameters and access other system information.

1. ### /root (Root User Home):
    

The `/root` directory serves as the home directory for the root user, which is the administrative user with full privileges. The root user can access and modify any part of the system, making this directory separate from the standard `/home` directory, where regular users' home directories are located.

1. ### /run (Runtime Data):
    

The /run directory contains temporary files and runtime data that should persist between reboots. It is often used by daemons and services to store information during system runtime. This directory is relatively new in Linux and serves as a replacement for /var/run.

1. ### /sbin (System Binaries):
    

The `/sbin` directory contains essential system binaries required for system administration tasks. These binaries perform various administrative functions and require elevated privileges to execute. Examples of commands in `/sbin` include ifconfig (configure network interfaces) and fdisk (partition table manipulator).

1. ### /srv (Service Data):
    

The `/srv` directory is used to store data related to services provided by the system. It often contains data that the system serves to clients or other systems. For instance, web servers might store website data in the `/srv` directory.

1. ### /tmp (Temporary Files):
    

The `/tmp` directory stores temporary files created by various applications and users. These files are typically short-lived and are often deleted upon system reboot. It is used as a common location for processes to create and use temporary files.

1. ### /usr (User Binaries and Libraries):
    

The `/usr` directory contains user-related binaries, libraries, documentation, and other data. It is one of the largest directories in a Linux system and typically contains a vast array of applications, libraries, and shared resources accessible to all users.

1. ### /var (Variable Data):
    

The `/var` directory holds variable data, including log files, spool directories, and other files that are expected to grow in size during system operation. It is often used to store data that changes frequently, such as logs generated by the system and its applications.

## Conclusion:

Understanding the file structure of Linux is fundamental for effectively managing and navigating the operating system. Each directory in the Linux file structure serves a specific purpose, organizing essential files and data within the system. By having a clear grasp of the functionalities of these directories, users can optimize their workflow, administer the system efficiently, and explore the vast possibilities offered by the Linux operating system.

Please note that Linux distributions might have some variations in their file structure, but the basic concepts remain consistent across most distributions. Whether you are a system administrator, developer, or casual user, mastering the Linux file structure empowers you to unlock the full potential of this versatile and powerful operating system.

If this blog did provide some info to you, please consider upvoting! ✨

Connect with me:

🔗 **LinkedIn:** [**linkedin.com/in/harshit-sharma--**](http://linkedin.com/in/harshit-sharma--)

🔗 **My YouTube Channel:** [**youtube.com/c/CoderBuddy?sub\_confirmation=1**](http://youtube.com/c/CoderBuddy?sub_confirmation=1)

🔗 **GitHub:** [**github.com/harshit-sharma-gits**](http://github.com/harshit-sharma-gits)