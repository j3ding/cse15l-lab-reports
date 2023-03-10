# **Lab Report 4**
Reproduce the tasks from the competition "Baseline". Should complete the steps as fast as possible.

## Step 1
Setup: if fork [the repository](https://github.com/ucsd-cse15l-w23/lab7) before, delete it. Should look like this in the personal account.
![4-1-1](https://user-images.githubusercontent.com/122497181/221335426-00b7079f-f915-4b71-8d83-ee7ad1fa43fd.png)

## Step 2
Fork [the repository](https://github.com/ucsd-cse15l-w23/lab7).
![4-1-2](https://user-images.githubusercontent.com/122497181/221335461-066dd439-4d78-4c73-8a6c-90d0d3e0dba9.png)

## Step 3
Start the timer.

## Step 4
Log into ieng6 on the terminal of VScode by typing the command `$ ssh cs15lwi23xxx@ieng6.ucsd.edu` where `xxx` differs for different student accounts. Since have used this account for last log in, can directly press `<up><enter>` in the terminal instead of typing. The terminal would look like this if successfully log in (Note: if fails to log in using the course account, can use the student email `$ ssh <email>@ieng6.ucsd.edu` to log in).
![4-1-4](https://user-images.githubusercontent.com/122497181/221335464-84380fa2-23ff-4bec-99ff-ddb61bc33361.png)
* To save time of typing password, generate ssh keys for ieng6 in the following steps.
* 1. In local terminal, type `ssh-keygen`.
  2. Keep entering `<Enter>` until the terminal gives a "randomart image", and the public key is saved in a certain path. 
  3. Log into the ieng6 remote server and type `mkdir .ssh` in the terminal. Log out the account using `Ctrl+D`.
  4. In order to copy the public ssh key just created, find it in directory `.ssh` and a file called `authorized_keys` (note that the public key file ends in `.pub`). Copy the path presented in the terminal where the terminal says `Your public key has been saved in: <copy this path>`.
  5. Run this and type the password (on local computer).
  ```
  $ scp <path copied in last step> <account name>@ieng6.ucsd.edu:~/.ssh/authorized_keys
  ```
  6. Log into the ieng6 remote server again and it does not require entering password.
  ![ss](https://user-images.githubusercontent.com/122497181/224210716-3cce71d7-bdd2-47bc-b119-3fee0ae68ccf.png)

## Step 5
Clone the fork of the repository from personal Github account. Type `$ git clone` in the terminal, and the ssh clone URL `git@github.com:xxxx/lab7.git`, where `xxxx` represents the Github account name. The following picture shows how to access the URL.
* Note: if cannot use the ssh git clone, use `$ git clone https://github.com/xxxx/lab7.git` instead, as is shown below.
* Note: if the `lab7` directory already exists in the server, use `$ rm -r lab7` to remove the non-empty directory `lab7` and enter `y` to confirm.
![4-1-5](https://user-images.githubusercontent.com/122497181/221335468-09bacd76-839d-4388-b17e-562490b5472d.png)
![4-1-5(2)](https://user-images.githubusercontent.com/122497181/221335470-629d5ef1-b36b-4f0c-b9a2-e7924b5f3820.png)

## Step 6
Change directory to `lab7` and run the tests, typing following in the terminal for MAC users.
```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
* Note: If have run the tests before, type `javac` and then `<up><up><up><up><up><up><enter>` to search for previous calls, and similar for the `java` command. As is shown below, there is one failure.
![4-1-6](https://user-images.githubusercontent.com/122497181/221335981-ff370f32-202c-4c91-86c8-dee8539c362a.png)

## Step 7
Fix the problem. In this case, there is one problem in `merge` method in `ListExamples.java`. Change `index1 += 1` in line 43 into `index2 += 1`. Type `$ nano L<tab><enter>` in the terminal and it would complete it as `$ nano ListExamples.java`. This command opens a new window of editor of this file that can be edited. 
* There are a lot of ways to fix the problem. For example, use `Ctrl+\` to search for `index1 += 1` and replace it into `index2 += 1`. Since there are more than one matchings, can use `^N` to move to different matchings.
* After edit, press `Ctrl-O` to save and `Ctrl-X` to exit.
![4-1-7](https://user-images.githubusercontent.com/122497181/221335479-2a534ae4-f62a-4e57-905d-1683efdab3a8.png)

## Step 8
Run the tests, using the same method as step 6 did to save time (or use copy and paste: on MAC, use `Command-C` to copy and `Command-V` to paste). The two tests should all pass like this.
![4-1-8](https://user-images.githubusercontent.com/122497181/221335480-8c218c95-db93-4699-9e00-9db6c1ccc287.png)

## Step 9
As is shown below, type `$ git add L<tab><enter>` and use `$ git commit` to commit. Then, type `$ git push o<tab> m<tab><enter>` to push changes to the Github account. Terminal would ask for username and password of the account.
![4-1-9](https://user-images.githubusercontent.com/122497181/221335484-d02b8a6d-553b-4a21-b861-07b893b0cac5.png)

