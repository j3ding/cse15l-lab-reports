# **Lab Report 3**
The following are four useful command-line options of `find` command.
## 1. Find files by names: `-name` option.
Type this command in the terminal in order to check all of the txt files in the written_2 directory. For this command, we can search for files or directories by name so that we can quickly locate some specific documents we want.
```
$ find written_2 -name "*.txt"
```
* `""` is used to give the name of the file we want to search for.
* `*` represents the arbitrary portion of the file we want to search for. (In this case, since we want to search for any txt files, the name of the file can be anything, but the ending of the file must be `.txt`.)
* As is shown below, the results are printed directly in the terminal.
(3-1-1 here)
We can also search for different types of files in different directories. For example,
```
$ find written_2/travel_guides -name "berlitz1"
```
* In this case, we search for a directory named `berlitz1` in the `travel_guides` directory in `written_2`.
* Note that `-name` command looks for the file by its full name, so within the `""` we either type the full name of the file or use `*` to represent for arbitrary portions. (So in the following screenshot, if we search for `"berlitz"`, the terminal would search for the file that exactly names `"berlitz"`, which does not exist in `written_2` directory.)
(3-1-2 here)
## 2. Find files by types: `-type` option.
Type this command in the terminal to search for the file types only (not directories). This command-line option is useful in categorizing documents into different types.
```
$ find written_2 -type f
```
* Here `f` means that the command would return only files. 
* Since we only have txt files in the `written_2` directory, the result as shown below is the same as the first example in the previous part of `-name` option.
(3-2-1 here)
Try to search for other types, such as directory, using this command.
```
$ find written_2 -type d
```
* Here `d` represents for the directory type. All of the directories within `written_2` (including itself) are printed in the terminal.
(3-2-2 here)
