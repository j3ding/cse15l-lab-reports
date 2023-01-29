---
# **Lab Report 1**

## ***Step 1  Installing VScode***
If already installed, skip this step.
If not get installed yet, use [this link](https://code.visualstudio.com/) and follow the following steps:
1. Click on *Download Mac Universal* or the side bar for Windows or Linux systems.
2. Waiting for the installation and unzip the download file. 
* Note: If the download does not start, please use the alternative link on the top of the download page.
3. Open the file and follow the instructions to install it on the computer. If the installation finishes, VScode should look like the following picture as shown. \
![vscode](https://user-images.githubusercontent.com/122497181/214936368-03c1593f-8d4f-49c1-9e05-ef352e54d6b0.png) \
**For Windows Users:** For the next step, should install `git` for the next step, using [this link](https://gitforwindows.org/) to install.
* Click on *Download* and follow the instructions.
* After the installation, set the default terminal to use the installed `git bash` in VScode. Click [here](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994) to see the instructions in details.

## ***Step 2  Remotely Connecting***
1. Open a terminal in VScode (on the top horizontal menu, choose *Terminal* and then click on *New Terminal*).
2. Connect using the CSE 15L account by typing `ssh cse15lwi23xxx@ieng6.ucsd.edu` in the terminal, where `xxx` is replaced by the letters in the specific account. **Important: Please reset the password for the student account, then try to log in.**
3. If connect this server for the first time, would see a message like this:
```
⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
4. Type `yes` and enter, then enter the password for the account. * Note: This may cause a system error. If this happens, try several times to enter the password, or try to log in using UCSD personal email (as shown in the graph).
5. If log in successfully, would see `Last login: ...` on the terminal.
![ss1](https://user-images.githubusercontent.com/122497181/214936387-9e58f1d6-5af9-4538-b04c-fb46c803f3b9.png)

## ***Step 3  Trying Some Commands***
Trying some commands in the terminal.
* `cd` is used to change the current directory (this command does not print anything in the terminal). For example, simply type in `cd` does not have any change.
* `ls` is the command to list files in current directory. For example, this command types files like *Desktop* on the terminal in blue.
* `pwd` prints the current working directory. This would help check the directory after `cd` command.
* `cp` can specify the location of certain classes. For example, this may be used to call a JUnit test.
* `mkdir` can make a new directory. This command should be followed by a directory's name.
* There are other useful commands such as `cd ~`, `ls -lat`, `ls -a` and so on.
* Type `exit` if want to log out. \
![ss3](https://user-images.githubusercontent.com/122497181/214936417-2ecac01c-d761-4c8d-acf6-ddac9d1a1d67.png)
![ss2](https://user-images.githubusercontent.com/122497181/214936399-298d462b-7f11-4edf-968d-d761e339fba7.png)
