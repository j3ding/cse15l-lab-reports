# **Lab Report 4**
Reproduce the tasks from the competition.

## Baseline
In this task, should complete the steps as fast as possible.
1. Setup: if fork [the repository](https://github.com/ucsd-cse15l-w23/lab7) before, delete it. Should look like this in the personal account.
(4-1-1 here)
2. Fork [the repository](https://github.com/ucsd-cse15l-w23/lab7).
(4-1-2 here)
3. Start the timer.
4. Log into ieng6 on the terminal of VScode by typing the command `$ ssh cs15lwi23xxx@ieng6.ucsd.edu` where `xxx` differs for different student accounts. Since have used this account for last log in, can directly press `<up><enter>` in the terminal instead of typing. The terminal would look like this if successfully log in.
* Note: if fails to log in using the course account, can use the student email `$ ssh <email>@ieng6.ucsd.edu` to log in.
(4-1-4 here)
5. Clone the fork of the repository from personal Github account. Type `$ git clone https://github.com/xxxx/lab7` in the terminal, where `xxxx` is the Github username.
* Note: if the `lab7` directory already exists in the server, use `$ rm -r lab7` to remove the non-empty directory `lab7` and enter `y` to confirm.
(4-1-5 here)
6. Change directory to `lab7` and run the tests, typing following in the terminal for MAC users.
```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
* Note: If have run the tests before, type `javac` and then `<up><up><up><up><up><up><enter>` to search for previous calls, and similar for the `java` command. As is shown below, there is one failure.
(4-1-6 here)
7. Fix the problem. In this case, there is one problem in `merge` method in `ListExamples.java`. Change `index1 += 1` in line 43 into `index2 += 1`.The correct code should look like this.
(4-1-7 here)
8. Run the tests, using the same method as step 6 did to save time (or use copy and paste: on MAC, use `Command-C` to copy and `Command-V` to paste). The two tests should all pass like this.
(4-1-8 here)
9. Open Github Desktop, select `Commit to main` and then `Push to origin`. Can also use `$ git add <filename>` to commit the file, and `$ git push` to push the final changes to personal Github account.
(4-1-9 here)
