# **Lab Report 5**

In lab report 3, explore 4 interesting command-line options for `find` command. 
This lab report contains 4 interesting command-line options for `grep` command. Information about the options are from [this source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix).


## 1. `grep --color` option

Type the following command on the terminal to search for a specific string, for example `industry` in `ch1.txt` file under the `Abernathy` subdirectory in `written_2` directory. The command asks the terminal to print all lines in this file that contain the required string with the string highlighted with red. This is useful in searching for a specific string and see its context.
```
$ grep --color "industry" written_2/non-fiction/OUP/Abernathy/ch1.txt
```
* Note that the option is `--color` rather than `-color`.
* `""` should be the string that we want to highlight in the file(s).
* The path after the string must point to a file rather than a directory or subdirectory.
* The terminal should look like this as shown below.
![5-1-1](https://user-images.githubusercontent.com/122497181/224458377-8fc89639-03d2-4fc2-940a-7be177616bec.png)

We can also search for all files in the same subdirectory at the same time. Since this would print a lot in the terminal, try the following command instead.
```
$ grep --color "museums" written_2/travel_guides/berlitz1/IntroDublin.txt
```
* If want to use this command and option on all files in a subdirectory, for example `berlitz1`, may try `...berlitz1/*` where `*` represents all files in the subdirectory.
* The command only prints **the exact line** of the required string rather than the paragraph or the whole passage.
* By the last two labs, can save time by typing `<up>` to get the command in the first example. Only have to change the string and path.
![5-1-2](https://user-images.githubusercontent.com/122497181/224458380-3c9758f2-0c64-4855-9b1b-18962bb2a5ad.png)


## 2. `grep -r` option

This option represents for searching for a specific string recursively in a directory. Run the following command line on the terminal. In this case, want to search for `regionalization` in all subdirectories in `written_2/non-fiction/OUP` directory. It is useful to directly search a string when the user only knows the name of the directories, and it uses recursion.
```
$ grep -r "regionalization" written_2/non-fiction/OUP/*
```
* `*` represents for all the files in all the subdirectories in `OUP` subdirectory.
* Similar to the previous command option, it only prints the corresponding lines rather than the whole passage.
* The result is shown below, what have been found in `ch1.txt` is printed before that in `ch15.txt`, and this is because the command uses recursion.
![5-2-1](https://user-images.githubusercontent.com/122497181/224458381-8f0283d9-6d6e-40e5-b0d1-909070e916e9.png)

In this case, give the specific file name and search recursively for a string. Run the following command on the terminal.
```
$ grep -r "support" written_2/travel_guides/berlitz2/Vallarta-History.txt
```
* This time the terminal would only prints out the results in this specific file called `Vallarta-History`, as is shown below.
![5-2-2](https://user-images.githubusercontent.com/122497181/224458384-3e355c4f-918a-4c46-841b-fc3185f1b27b.png)


## 3. `grep -c` option
This option counts the lines of a specific string presents in files. Type the following command line on the terminal. This command option is useful because it can replace the `wc` command and can check for all files given the directory or subdirectories.
```
$ grep -c "credit cards" written_2/travel_guides/berlitz1/*
```
* Want to get the number of lines that contain `"credit cards"` in all files in the subdirectory `berlitz1`, where `*` represents for all files in this subdirectory.
* The results are certain numbers corresponding to each file in the subdirectory.
* Note that if there is no such string in the file, the result would be `0` as shown below.
* This command would not print the specific text but only show the numerical results for counting.
![5-3-1](https://user-images.githubusercontent.com/122497181/224458388-4942b765-434b-4c26-8255-0b2db5bc8c6d.png)

If we want to search for a string within only one file, run the command line like the following.
```
$ grep -c "history" written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
```
* In this case, only want to know the number of lines in the file called `Amsterdam-WhereToGo.txt` that contains `"history"`.
* Since look for only one file this time, the path of the file is not shown (only a number `9` that stands for the requried result).
![5-3-2](https://user-images.githubusercontent.com/122497181/224458392-b1bbfaf7-10a7-4bd5-9a13-280173916bc2.png)


## 4. `grep -v` option
This command requires the terminal to print out the lines in the required file that do not contain a specific string. This is particuarly useful if we do not want to see some texts, which can be interpreted as the complement of the `grep -r` option. For example, run the following command on the terminal.
```
$ grep -v "and" written_2/non-fiction/OUP/Castro/chY.txt
```
* This command does not show all the lines that contain `"and"` in a file called `chY.txt`.
* The results are printed on the terminal, and as shown below there is no required string `"and"` in the printed result.
![5-4-1](https://user-images.githubusercontent.com/122497181/224458394-a2acf866-6f33-416f-9239-42a773c12092.png)

This option can also be used to check in all files within one directory or subdirectory. For instance, type the following on the terminal.
```
$ grep -v "to" written_2/non-fiction/OUP/Castro/*
```
* Like in the other options, `"*"` represents all files in the subdirectory `Castro`.
* Since the command searches for several files, the printed result contains the path for a specific file for every line. Can see from the following screenshot that this command option prints all the results line by line.
![5-4-2](https://user-images.githubusercontent.com/122497181/224458396-7ff05788-6952-4001-b9e0-e8aaf1404d36.png)
