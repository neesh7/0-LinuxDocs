## Commands
### Working with the Shell - I
```bash
# ~ character represent home directory which is usually looks like /home/username

$ <commands> <args>
# usually commands in linux needs cmd + args (acts as a input for cmd)
$ echo hello
$ echo -n hello # to avoid new trailing line to print after 
# some commands doesnt need any args so we refer it as 
$ uptime
# command <option> <args>
# echo -n hello

# commands in linux are of 2 type internal( built-in or part of linux os) or external commands (installed by user or place at a place as binary) to check the type of command use type command
$ type echo
$ type mv
```

### Working with the Shell - II ( Files and Directories)
```bash
$ pwd # to check present working directory
$ ls # list contents
$ mkdir # to create directories
$ echo $HOME # shows home directory
# directories
$ mkdir folder1 # create directory simply
$ mkdir folder1 folder2 # create multiple directories
$ mkdir folder1/folderA # create sub directory inside a directory
$ mkdir -p folder1/folderA # create parent and child directory at once

# Switching directories
$ cd # change directory - it takes you to home directly
$ cd .. # it take 1 level back at prev directory
$ cd / # takes to root directory
$ cd /home/dev # takes to the path provided - cd <path>

# pushd and popd
# when working with large number of directory structure this can be used pass pushd the directory you want to save and then do cd and navigate anywhere when you wish to comeback to the directory you saved just type popd

$ pushd /etc # saved etc directory location
$ cd /asia/india/mumbai # navigated anywhere we wish
$ popd # here we come back to the location we saved ( last pushed directory comes out first)


# Moving a file/directory
$ mv <sourceFile> <DestinationFile> # copies file from one location to another
$ mv <sourceFile> # copies all file from source to pwd

# Renaming a file
$ mv <currentfilename> <newfilename>
$ mv hello.py hello1.py

# Copying files/directories
$ cp <sourceFile> <DestinationLocation> # to copy from one location to another
$ cp -r <sourceDir> <DestinationLocation> # to copy or remove any directory we do it recursively

# deleting
$ rm <file> # deleting a file
$ rm -r <directory> # deleting a directory
```
### Working with the Shell - III ( Files and Directories)
```bash

# Read/Write files
$ cat <filename.txt> # it is used to read files
$ cat > files.txt # Redirect content to a file , ctrl+d to exit from editor

# The touch commands magic
$ touch hello.txt
$ touch file1.txt file2.txt file3.txt # creating multiple file using touch
$ touch file{1..5}.txt # using touch with wildcards to create multiple files
$ ls -l file{1..5}.txt
$ stat myfile.txt # shows stats timestamps wise for the file

$ vim hello.txt
$ nano hello.txt

# Pagers
$ more file.txt
$ less file.txt

# List files
$ ls -l # long list
$ ls -a # list all files including hidden files
$ ls -lt # list files in order they are created
$ ls -ltr # list files in reverse order
$ ls -R # recursive listing

# Getting help
$ whatis <cmd>
$ man <cmd> # opens manual
$ <cmd> -h or --help
$ apropos <keyword> # search through manuals
```