# Best setup for Competitive Programming with C++

Are you into Competitive Programming, or starting out the same? One of the things you'd spend time the most, is your Setup for CP. And obviously, you don't want that to be un-productive. So, here is my setup for Competitive Programming:
- MinGW Compiler
- Sublime Code Editor
- and a little build system 😉

The following steps assume you have a windows operating system.

### Install Sublime Text Editor

Download the setup of **Sublime Text Editor** from [here](https://www.sublimetext.com/) and install it.

### Install MinGW Compiler

**MinGW **was created to support the GCC compiler on Windows OS.

- Download **MinGW **from [here](https://sourceforge.net/projects/mingw/).
- Install the basic setup for MinGW.
- Mark the following package for installation:

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267207411/SbLN55wFR.png align="left")

- Click on Installation > Apply changes


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267293843/pwtqET7tW.png align="left")

This will install the minGW **gcc**, and **g++** compiler.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267286994/4EalTVAzz.png align="left")

### Setting up the environment

Now **gcc**, and **g++** are installed on your system. But for you to access them from anywhere, you need to add them to **PATH**. Just follow these steps:

- Search for `environment`, something like `Edit the system environment variables` should pop up. Click on that.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267616643/g8H9pdV96.png align="left")

- Click on environment variables.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267676221/bp4Z0Y1H1.png align="left")

- Locate **Path** inside the **System Variables**, and hit **Edit**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669267773992/y5CwTmF2Z.png align="left")

- Now you have to add the path to the bin folder of MinGW directory. By default, the path is `C:\MinGW\bin\` (you can just copy-paste from here as well)

- Add it and click **Ok**

- Now the C++ compiler is up and running within your environment, and you may check it by running `g++ --version` inside your terminal.

- If your terminal shows something like this, then you are good to go ahead. If not, try reiterating the above steps.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669268070662/9dezZ8C1l.png align="left")

### Creating a build system

Now comes the last step, Creating your very own CP build system!

- Open Sublime Text and go to *Tools > Build System > New Build System*
- Paste the following code in the file and save it.
- Name the file as `CP.sublime-build`.

```
{
    "cmd": ["g++.exe", "-std=c++17", "${file}",
            "-o", "${file_base_name}.exe",
            "&&", "${file_base_name}.exe<inputf.in>outputf.out"],
    "shell":true,
    "working_dir":"$file_path",
    "selector":"source.cpp"
}
```

This build system allows you programs to take input from **inputf.in** and write the output to **outputf.out** (both of which are text files)

### Set up a windows layout

Create three new files as shown below and make sure all of them are in the same folder.

- **file.cpp**: The file for writing the code.
- **inputf.in**: The file where we will be giving the input.
- **outputf.out**: The file where the output will be displayed.

Now, perform the following steps:

- Select *View > Layout > Columns : 3*. This will create three columns in the workspace. - - Move the three files into three columns.
- Select *View > Groups > Max Columns : 2.*
- Select the build system we just created from *Tools > Build System > CP*.

Now your layout should look like this:


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669269125258/0oxrSrvYS.png align="left")

Cheers! ✨