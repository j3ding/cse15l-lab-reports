# **Lab Report 3**
The following are four useful command-line options of `find` command. \
*The `-name` and `-type` options are learned from the [course webpage](https://ucsd-cse15l-w23.github.io/week/week4/). Search all of the four command-line options on [Google](https://www.google.com), and the specific source is [here](https://www.redhat.com/sysadmin/linux-find-command).*
## 1. Find files by names: `-name` option.
Type this command in the terminal in order to check all of the txt files in the written_2 directory. For this command, we can search for files or directories by name so that we can quickly locate some specific documents we want.
```
$ find written_2 -name "*.txt"
```
* `""` is used to give the name of the file we want to search for.
* `*` represents the arbitrary portion of the file we want to search for. (In this case, since we want to search for any txt files, the name of the file can be anything, but the ending of the file must be `.txt`.)
* As is shown below, the results are printed directly in the terminal.
![3-1-1](https://user-images.githubusercontent.com/122497181/218247612-913580b9-e774-4241-8dda-d5509333691c.png)
We can also search for different types of files in different directories. For example,
```
$ find written_2/travel_guides -name "berlitz1"
```
* In this case, we search for a directory named `berlitz1` in the `travel_guides` directory in `written_2`.
* Note that `-name` command looks for the file by its full name, so within the `""` we either type the full name of the file or use `*` to represent for arbitrary portions. (So in the following screenshot, if we search for `"berlitz"`, the terminal would search for the file that exactly names `"berlitz"`, which does not exist in `written_2` directory.)
![3-1-2](https://user-images.githubusercontent.com/122497181/218247616-2d9ab0cb-0512-4679-9992-1b10e266288f.png)


## 2. Find files by types: `-type` option.
Type this command in the terminal to search for the file types only (not directories). This command-line option is useful in categorizing documents into different types.
```
$ find written_2 -type f
```
* Here `f` means that the command would return only files. 
* Since we only have txt files in the `written_2` directory, the result as shown below is the same as the first example in the previous part of `-name` option.
![3-2-1](https://user-images.githubusercontent.com/122497181/218247653-d9795c43-68e1-4aa5-9eb5-51ce5fb89250.png)
Try to search for other types, such as directory, using this command.
```
$ find written_2 -type d
```
* Here `d` represents for the directory type. All of the directories within `written_2` (including itself) are printed in the terminal.
![3-2-2](https://user-images.githubusercontent.com/122497181/218247659-88fe4f2f-7bf4-42c4-9897-7fbc9999074e.png)


## 3. Find and list everything: `-ls` option.
Enter in this command in the terminal to print everything in directory `written_2`. This command is useful in looking up more detailed information about files in a directory. It also helps to print different information that can be summarized with `wc` command. 
```
$ find written_2 -ls
```
* As is discussed in the first lab report, `-ls` command can list all files and directories in the current directory. In this case, it lists all of the documents in `written_2`, including its file paths, word counting, time, and other detailed information.
![3-3-1](https://user-images.githubusercontent.com/122497181/218247711-ee4b2b4e-df68-4900-b630-3bf78a36a255.png)
Since `-ls` prints large amount of information, we can save the result into a txt file and summarize the data with commands like `wc`.
```
$ find written_2/non_fiction -ls > lsopt.txt
$ wc lsopt.txt
```
* The `>` sign means that the result is saved to a new file called `lsopt.txt` in the same directory as `written_2`. 
* We can also use `wc` the command of word counting to help us summarize the data (for example, get to know that there are 53 files in `non_fiction` directory).
![3-3-2](https://user-images.githubusercontent.com/122497181/218247714-f181f9ac-7f93-4713-85b0-b48340fdee57.png)


## 4. Find path: `-ipath` option.
Type in the following command line in the terminal to find any path that contains `Kauffman`. This is useful if we want to find some file but forget the file name. By recalling some of the directories (or part of the path), we can find the file and its path.
```
$ find written_2 -ipath "*Kauffman*"
```
* Suppose that we want to search for all of the works by a specific writer `Kauffman`, we use this command to include the writer's name as part of the path of the files we want to look for.
* Note that this has the same rules as `-name` option that we either type the whole path or use `*` to represent the neglecting portions.
![3-4-1](https://user-images.githubusercontent.com/122497181/218247760-5ced553d-3574-4ecd-bbea-4d813c8c4bd4.png)
The `-ipath` command can also do the same as the `-name` option if we type in the file names into `""`.
```
$ find written_2 -ipath "*/China*"
```
* This command search for the files that contain `China` in the file name.
* The only difference with the `-name` option is that `-ipath` can read `/` and take in paths, while `-name` reads `/` as a part of file name; so if we search for `*/China*` using `-name` option, the terminal would return nothing, because there is no file whose name has `/China`.
![3-4-2](https://user-images.githubusercontent.com/122497181/218247764-1fdd7442-f742-4e65-9118-c6a1efc49581.png)
