# ***Hello, world!***

---
# **Lab Report 1**

## ***Step 1  Installing VScode***
I installed VScode on my computer from a previous CSE class. 
* To install, using [this link](https://code.visualstudio.com/). VScode looks like this after opening it. \
![screenshot 1](https://user-images.githubusercontent.com/122497181/212182466-c37bd7b4-1190-469c-b435-cf67292ed22c.png)

## ***Step 2  Remotely Connecting***
Try to log in using the CSE 15L account by typing `ssh cse15lwi23acy@ieng6.ucsd.edu` in VScode terminal.
* This may cause a system error by changing the Active Directory password. Try several times to enter the password. \
This fails, so try to log in using UCSD personal email (should still use CSE 15L account next time). \
![screenshot 2](https://user-images.githubusercontent.com/122497181/212182484-05360ab9-fa99-49d4-808a-e4da51d60695.png)

## ***Step 3  Trying Some Commands***
* Successfully trying some commands including `cd` (change directory), `ls` (list files in current directory), and `pwd` (print current working directory). Also success in other commands like `cd ~`, `ls -lat`, and `ls -a`.
* But fails in trying `mkdir` and `cp`, which seems to be an error in format and math expression. Also fails in `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/` and `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`, which mean that there is no such file in current directory. To solve this, try to create a `hello.txt` in this directory manually. \
![screenshot 3](https://user-images.githubusercontent.com/122497181/212182499-54e4d659-da72-409a-bc3a-8f627cc0b4d9.png)
![screenshot 4](https://user-images.githubusercontent.com/122497181/212182492-4224997c-52de-44e4-b6ad-2ca15fdfc18e.png)
