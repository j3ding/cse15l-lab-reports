# **Lab Report 5**

In lab report 3, explore 4 interesting command-line options for `find` command. 
This lab report contains 4 interesting command-line options for `grep` command.


## 1. `grep --color` option

Type the following command on the terminal to search for a specific string, for example `industry` in `ch1.txt` file under the `Abernathy` subdirectory in `written_2` directory. The command asks the terminal to print all lines in this file that contain the required string with the string highlighted with red. This is useful in searching for a specific string and see its context.
```
$ grep --color "industry" written_2/non-fiction/OUP/Abernathy/ch1.txt
```
* Note that the option is `--color` rather than `-color`.
* `""` should be the string that we want to highlight in the file(s).
* The path after the string must point to a file rather than a directory or subdirectory.
* The terminal should look like this as shown below.
(5-1-1 here)

We can also search for all files in the same subdirectory at the same time. Since this would print a lot in the terminal, try the following command instead.
```
$ grep --color "museums" written_2/travel_guides/berlitz1/IntroDublin.txt
```
* If want to use this command and option on all files in a subdirectory, for example `berlitz1`, may try `...berlitz1/*` where `*` represents all files in the subdirectory.
* The command only prints **the exact line** of the required string rather than the paragraph or the whole passage.
* By the last two labs, can save time by typing `<up>` to get the command in the first example. Only have to change the string and path.
(5-1-2 here)


## 2. `grep -r` option

This option represents for searching for a specific string recursively in a directory. Run the following command line on the terminal. In this case, want to search for `regionalization` in all subdirectories in `written_2/non-fiction/OUP` directory. It is useful to directly search a string when the user only knows the name of the directories, and it uses recursion.
```
$ grep -r "regionalization" written_2/non-fiction/OUP/*
```
* `*` represents for all the files in all the subdirectories in `OUP` subdirectory.
* Similar to the previous command option, it only prints the corresponding lines rather than the whole passage.
* The result is shown below, what have been found in `ch1.txt` is printed before that in `ch15.txt`, and this is because the command uses recursion.
(5-2-1 here)

In this case, give the specific file name and search recursively for a string. Run the following command on the terminal.
```
$ grep -r "support" written_2/travel_guides/berlitz2/Vallarta-History.txt
```
* This time the terminal would only prints out the results in this specific file called `Vallarta-History`, as is shown below.
(5-2-2 here)
