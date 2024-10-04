# Linux Command Line

## Basic Commands

- ```date```: current date
- ```cal```: current months calendar
- ```cal 1999```: calendar for 1999
- ```cal -3```: calendar (last month, current and next month)
- ```cal -y```: all year calendar
- ```clear```: clear console text
- ```exit```: exits de terminal

    
### Commands

- ```pwd```: print working directory

- ```ls```: list directory

- ```cd```: change directory

- ```cd /```: take you to the root directory

- ```cd ~```: take you to the user home directory

- ```cd ./another_folder```: navigate from current directory to another_folder

- ```cd ..```: navigate from current directory to parent directory

- ```cd -```: go back to the previous working directory
  - ```cd /```: going to the root directory
  - ```cd ~/```: going to the home directory
  - ```cd -```: going back to the root directory


- ```cd "my work"``` or ```cd 'my work'``` or ```cd my\ work```: going to a folder with space

- ```ls /```: display your root directory

- ```ls ~```: display your home directory

- ```ls ..```: display the content of my parent directory

- **[DOES NOT WORK]** ```ls -```: should display you the content of your previous working directory

![Screenshot](./images/LS%20-L%20OUTPUT.png)


### Commands

- ```ls -i```: show inode id of files

- ```ls -l```: show files information (size in bytes, permission, etc.)

- ```ln```: link

- ```ln file_name hard_link1```: Create a hard link for a file (same inode)

- ```ln -s file_name soft_link1```: Create a soft link for a file

- ```ln -s .. c```: Create a soft link C for the parent directory you are currently located in

## LS Options

- ```ls```: List files by alphabetic order

- ```ls -i```: This will list the index node number of each file

- ```ls -a```: This will show all the files (-a == all files) in your current directory, including hidden files

- ```ls -l```: Long listing of all files in the directory and some important information.

- ```ls -t```: Sort files by modification date

- ```ls -r```: List the files in reverse fashion (in this case reverse based on alphabetic order)

- ```ls -rt OR ls -r -t```: List the file in reverse fashion (in this case reverse based on modification date)

- ```ls -li```: Long listing + show inode ids

- ```ls -lia```: Long listing + show inode ids + hidden files

- ```ls -R```: Show current directory content plus any children/sub directory content as well

- ```ls -Ra```: Show current directory content plus any children/sub directory content as well + including hidden files


## Touch Command (Create a file)

- Touch is used to create empty files

  - ```touch file_name```: Create a file called file_name
  - ```touch file_name1 file_name2 file_name3```: Creates 3 files
  - ```touch 'my file'``` or ```touch "my file"``` or ```touch my\ \ file```: create a file with a name containing spaces
    - ```\``` is a scape sequence


- Touch is also used to update a current files timestamp (modification dade)

  - ```touch newFile```
  - ```echo "test" > newFile```
  - ```touch newFile```: this will update the file timestamp and keep the content


## MKDIR (Make directory) and RMDIR (Remove directory) Commands

- If you want to create a directory, then you use ```mkdir``` command as follow:

  ```
  mkdir directory_name
  mkdir directory_name1 directory_name2 directory_name3
  ```

- To remove **empty** directories you can use ```rmdir``` command as follows:

  ```
  mkdir empty_dir
  rmdir empty_dir
  ```

  - In case you do ```rmdir``` in one directory that has files and another that is empty, it will only delete the empty one.


- To create a directory with a name containing spaces, you can do ```mkdir 'my directory'``` or ```mkdir "my directory"```

## RM (Remove) Command

  - To delete non-empty-directory files, or just normal files you just do:
    
  - ```rm``` options:

    - ```rm -i```: Prompt you before removing any existing file. the ```-i``` means interactive mode

    - ```rm -f```: Never prompt you before removing a file. And will not display a warning if the file you are trying to delete does not exist, meaning that it will ignore non existent files. -f means force

    - ```rm -v```: Verbose mode. It will print the name of each file before removing it.

    - ```rm -R``` or ```rm -r```: Recursively delete files. If the file is a directory, remove the entire directory and all its contents, including subdirectories.

## CP (Copy) Command

- The ```cp``` command copies files or directories. It can be used in two different ways:
  - Copy a file: ```cp file file2```
  - Make a copy of a directory: ```cp -R dir dir2```: ```dir2``` does not need to exist
    - This will make a copy of dir1 named dir2 (Assuming that dir2 didn't exist)

  -  In case you copy many files using the following syntax:
    - ```cp file1 file2 file3 dir```: ```dir``` must exist in this case.
    - Same case for directories: ```cp -R dir1 dir2 dir3```


- ```cp``` options:

  - ```cp -i```: Before overwriting an existing file, prompt the user for confirmation. **cp will silently overwrite files by default.**
  - ```cp -v```: Verbose mode (print the name of each file that was copied).
  - ```cp -R```: Recursively copy directories and their content. Just like the ```rm``` command, this option must be specified when copying a directory.
  - ```cp -r```: Same as cp -R


## MV (Move) Command

- The ```mv``` command can be used in two different ways.
  - Renaming files

    - ```mv file1 file2```: This will rename file1 to file2
    - ```mv dir1 dir2```: If your file is a directory, this will rename the directory
    - **You do not need to use the -R option with ```mv```**

  - Moving files

    - ```mv file1 file2 dir1```: This will move file1 and file2 to dir1. However, dir1 must exist
    - ```mv dir1 dir2 dir3```: This will move dir1 and dir2 to dir3. Again, dir3 must exist


- ```mv``` options:

  - ```mv -i```: Before overwriting an existing file, prompt the user for confirmation. If the option is not specified ```mv``` **will silently overwrite the file**

  - ```mv -v```: Verbose mode (print the name of each file that was moved or renamed)

## FILE (File) Command

  - Filenames are case sensitive in just like the commands are.

  - Linux has no concept of  `file extension` like Windows. You can have files without any extension.
    - It checks the file content to identify what kind is it.


  - The command ```file filename``` will give us information about the file type.

  - ```file LS -L OUTPUT.png```: LS -L OUTPUT.png: PNG image data, 1968 x 488, 8-bit/color RGBA, non-interlaced

## Command Line History

  - ```history```: Show all the commands executed in the cmd
  - ```history 10```: Show last 10 commands
  - ```history -c```: Clear history
    - Your history is stored at ```~/.bash_history```
  - ```!number```: Runs a command from history

## Shortcuts

  - ```Control+a```: Start of the line
  - ```Control+e```: End of the line
  - ```Control+d```: Remove character from left to right
  - ```Control+l```: Clear

## View text files (less, cat, tac, head, tail) Commands

  - ```less file1```: View the content of the file ```file1```
    - Press ```q``` to quit

  - ```cat file1 file2```: View the content of the file ```file1```concatenated with ```file2```
    - ```cat``` lets you see two files output concatenated

  - ```tac file```: Shows the content of file, but reversed
  - ```head -n 20 file```: Show first 20 lines of file
  - ```tail -n 20 file```: Show last 20 lines of file


## WC (word count) Command

  - ```wc file```: Presents the data like -> Number of lines, number of words, number of bytes
  - ```wc -l```: Show just number of lines
  - ```wc -w```: Show just number of words
  - ```wc -c```: Show just number of bytes
  - ```wc -L```: Length of longest line in characters

## Types of Commands

  - ```bash```: Born again shell

  - Executable programs
    - They are inside ```/bin``` and ```usr/bin```.
    - Example: ```cp``` command

  - Shell builtin
    - ```cd``` command
    - In computing, a shell builtin is a command or a function, called from a shell, that is executed directly in the shell itself, instead of an external executable program which the shell would load and execute.

      Shell builtins work significantly faster than external programs, because there is no program loading overhead. However, their code is inherently present in the shell, and thus modifying or updating them requires modifications to the shell. Therefore, shell builtins are usually used for simple, almost trivial, functions, such as text output.

  - Shell scripts
    - Custom programs written in shell script

  - Alias
    - ```ls``` command
    - Create your own commands
    - 	The alias command makes it possible to launch any command or group of commands (inclusive of any options, arguments and redirection) by entering a pre-set string (i.e., sequence of characters).

  - Display information about command type:
    - It displays if command is an alias, shell function, shell builtin, disk file, or shell reserved word.
    - ```type ls```: ls is hashed (/bin/ls)
    - ```type cd```: cd is a shell builtin
    - ```type cp```: cp is /bin/cp
      - ```file /bin/cp```: tells you that ```cp``` is an executable


  - ```which``` will display the path of shell scripts and executables, it does not support shell builtins.
    - ```which cp```: display executable location ```/bin/cp```


  - For shell builtin help you can do ```help cd```

  - For executable help you can do ```man cp```
    - Also for executables, you can do ```whatis cp``` to get a short description about the program

## Wild cards

  - ```*```: all occurrences
    - ```cp *.txt dir```
    - ```cp * dir```
  
  - `*.png` returns all the files that end with the extension .png

  - `pea?.png` returns all files that start with "pea", is followed by any single character, and end with .png (for example, peas.png and pear.png)

  - `*.{txt,pdf}` returns all files that end with either .txt or .pdf

  - `log[12345].pdf` returns files log1.pdf, log2.pdf, log3.pdf, log4.pdf and log5.pdf

  - ```?```: represents a single character
   - ```cp file?.txt dir```: copy all files file0.txt, file1.txt, etc. Any file that has a name structure like ```file``` + an unknown character + ```.txt```

  - ```[]```: range of characters
    - ```cp [abc]*.txt dir```: Copy all the file that begins with the letters abc to ```dir```

    - ```cp [!abc]*.txt dir```: Copy all the file that **does not** begins with the letters abc to ```dir```

        - Exclamation mark negates the command

    - ```cp [0-9]*.txt dir```: Copy all files starting from 0 to 9

    - ```cp [[:upper:]]* dir```: Copy all the files that starts with an upper case letter

    - ```cp [[:lower:]]* dir```: Copy all the files that starts with an lower case letter

    - ```cp *[[:digit:]] dir```: Copy all the files that ends with a digit

    - ```cp [[:alpha:]] dir```: Copy all the files that starts with a character from the alphabet

    - ```cp [[:alnum:]] dir```: Copy all the files that starts with a character from the alphabet or a number. (alpha numeric)

    - ```cp [[:alnum:]][0-9]* dir```: Copy all the files that starts with a character or a number (alpha numeric) and the second character must be a number from 0 to 9

    - ```cat ???```: View all files with exactly 3 characters

    - ```rm [[:digit]]*[abc]```: Remove all the files that begins with a number and ends with the letter (a,b or c)

    - ```rm [[:digit]]*abc```: Remove all the files that begins with a number and ends with the letters abc all together  

## Alias

  - ```alias myname="cd Desktop;mkdir dir"```: Create an alias called myname that goes to the Desktop folder and creates a directory called dir

  - ```unalias myname```: Delete an alias

  - To retain an alias, save it inside ```~/.bashrc```

  - ```alias```: List of all alias in the system
