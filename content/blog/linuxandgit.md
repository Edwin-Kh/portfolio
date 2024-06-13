---
title: Living in the terminal with Linux and Git
description: Learning notes for Linux OS and Git VCS
date: 2024-04-30
cover: gitbash.png
tags:
  - Linux
  - Git
---

# Table of Contents

1. [Learning how to live in the terminal using Git without using GUI](#learning-how-to-live-in-the-terminal-using-git-without-using-gui)
2. [Pros and Cons of Using Terminal and GUI](#pros-and-cons-of-using-terminal-and-gui)
   - [Terminal](#terminal)
   - [GUI](#gui)
3. [Basic Terminal Command Cheat Sheet](#basic-terminal-command-cheat-sheet)
4. [Linux Directory Structure](#linux-directory-structure)
5. [Nano Editor](#nano-editor)
6. [Vi Editor](#vi-editor)
   - [Vi Command Mode and Navigation](#vi-command-mode-and-navigation)
7. [Git Command Cheat Sheet](#git-command-cheat-sheet)
8. [Reasoning behind learning Linux](#reasoning-behind-learning-linux)

---

# Learning how to live in the terminal using Git without using GUI.

As a developer, I will be expected to work with and using UNIX systems and the Git version control system that is used by over 90% of the industry. Although I predominantly learned everything on a Windows OS system during my undergraduate studies, I thought I should dip my feet into the basics before moving on to learning actual development. This would in theory, allow me to learn a completely different operating system as well as familiarise myself with the terminal and away from GUI software. I admit using GUI for most of my projects and courseworks such as File Explorer, GitHub Desktop, SourceTree and several others. Therefore, training myself to live in the terminal would help immensely to avoid being overwhelmed when the time arises to use them. Being “terminal savvy” is to be expected for seasoned developers which may not come as a surprise to many.

There are several VCS that are popular but none of them comes close to Git. I have experience with Subversion using TortoiseSVN as the GUI software during my internship at Finexus. It is a completely different type of VCS as it is a centralised system rather than a distributed system like Git or Mercurial. Git has several GUI that facilitate the need for an interactable interface for several reasons I will mention later. Popular Git GUI clients such as GitHub Desktop, GitKraken, Sublime and the one I am familiar with, Sourcetree, all serve the same purpose to provide tooling to use Git through an interface.

## Pros and Cons of Using Terminal and GUI

### Terminal

**Pros:**

- Terminal commands can be quicker to use than GUI once you're familiar with them.
- Allows for more complex commands and scripting. This can automate repetitive tasks.
- Offers more control over the system and software.

**Cons:**

- Can be difficult for beginners to learn.
- Unlike GUI, Terminal doesn't provide visual feedback, which might make it harder to understand what's happening.

### GUI

**Pros:**

- Generally more intuitive and easier for beginners to use.
- Provide visual representations making it easier to understand the structure and state of things.
- No need to remember specific commands as functions are represented visually.

**Cons:**

- Navigating through GUI can be slower than using Terminal commands.
- GUIs might not offer all the functionality that Terminal does.

## Basic Terminal Command Cheat Sheet

| Command                    | Explanation                                                                                                             | Example                                                                |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| ls                         | Show a list of files in the current directory that I am on/ pointing at.                                                | ls Downloads                                                           |
| ls Downloads/file          |
| start/open                 | Open the File Explorer at this current location.                                                                        | start .                                                                |
| clear                      | Clear the terminal.                                                                                                     |                                                                        |
| pwd                        | Print the current working directory/location/path.                                                                      |                                                                        |
| cd                         | Change directory to the one I am pointing at.                                                                           | cd Downloads                                                           |
| touch                      | Create a file/ updating a file                                                                                          | touch test.txt                                                         |
| touch Downloads/okay.py    |
| mkdir                      | Make a directory.                                                                                                       | mkdir New File                                                         |
| rmdir                      | Remove a directory.                                                                                                     |                                                                        |
| rm                         | Remove file.                                                                                                            | rm test.txt                                                            |
| rm Okay.py                 |
| rm -rf                     | Remove directory.                                                                                                       | rm Image                                                               |
| cat                        | Concatenate and displays files.                                                                                         | cat file                                                               |
| tac                        | Displays files in reverse order.                                                                                        |                                                                        |
| man <command>              | Display manual/documentation for commands                                                                               | man ls                                                                 |
| man -k <searchterm>        | Ask for help with a search term for a command.                                                                          | man -k calendar                                                        |
| exit                       | Exits the shell from the current session.                                                                               |                                                                        |
| echo                       | Display a line of text.                                                                                                 | echo $PATH                                                             |
| which                      | Shows the full path of commands.                                                                                        | which cat (first one that appears in the directory will be the result) |
| .                          | Execute a program.                                                                                                      | .game                                                                  |
| -a                         | Indicates all.                                                                                                          |                                                                        |
| -l                         | Use a list format.                                                                                                      |                                                                        |
| -F                         | Reveal file types by appending a character to the end of the file.                                                      | ls -F                                                                  |
| -d                         | List directory names and not the contents.                                                                              |                                                                        |
| -r                         | Reverse the order of the result.                                                                                        |                                                                        |
| -R                         | List files recursively.                                                                                                 |                                                                        |
| -t                         | Sort by time, most recent first.                                                                                        |                                                                        |
| find <path> <expression>   | Recursively finds files in the path that match the expression.                                                          |                                                                        |
| find -name <pattern>       | Find files and directories that match the pattern                                                                       |                                                                        |
| find -iname <pattern>      | Ignores case.                                                                                                           |                                                                        |
| find -mtime <days>         | Finds files that are days old.                                                                                          |                                                                        |
| find -size <num>           | Finds file that are of size num                                                                                         |                                                                        |
| find -newer <file>         | Find files that are newer than file                                                                                     |                                                                        |
| find -exec <command> {} \; | Run command against all the files that are found                                                                        |                                                                        |
| locate <pattern>           | Lists files that match the pattern. Is faster than find command but the results are not in real time. Queries an index. |                                                                        |
| uptime                     | Shows when the system was booted and how long it has been up.                                                           |                                                                        |
|                            |                                                                                                                         |                                                                        |
| cat <file>                 | Display the contents of the file.                                                                                       |                                                                        |
| more <file>                | Browse through a text file.                                                                                             |                                                                        |
| less <file>                | More features than more.                                                                                                |                                                                        |
| head <file>                | Output the beginning portion of the file.                                                                               | head -f <file>                                                         |

-f follows the file |
| tail <file> | Output the bottom portion of the file. | tail -n <file>

Where n is the number of lines |

| Symbol | Type                             | Permission | File                           | Directory                                           |
| ------ | -------------------------------- | ---------- | ------------------------------ | --------------------------------------------------- |
| / or d | Directory                        |            |                                |                                                     |
| @      | Link                             |            |                                |                                                     |
| \*     | Executable                       |            |                                |                                                     |
| l      | Symbolic Link                    |            |                                |                                                     |
| -      | Regular File                     |            |                                |                                                     |
| r      |                                  | Read       | Allows a file to be read       | Allows file names in the directory to be read.      |
| w      |                                  | Write      | Allows a file to be modified   | Allows entries to be modified within the directory. |
| x      |                                  | Execute    | Allows the execution of a file | Allows access to contents and metadata for entries. |
| u      |                                  | User       |                                |                                                     |
| g      |                                  | Group      |                                |                                                     |
| o      |                                  | Other      |                                |                                                     |
| a      |                                  | All        |                                |                                                     |
| chmod  | Change Mode Command              |            |                                |                                                     |
| ugoa   | User Category                    |            |                                |                                                     |
| +-=    | Add subtract and set permissions |            |                                |                                                     |

Reading File and Directory Permissions

| Type | User | Group | Other | Number of Links | Owner Name | Group Name | Number of bytes in the file | Last Modification Time | File Name  |
| ---- | ---- | ----- | ----- | --------------- | ---------- | ---------- | --------------------------- | ---------------------- | ---------- |
| -    | rw-  | r—    | r—    | 1               | bob        | users      | 10400                       | Sep 27 08:52           | sales.data |

| Octal | Binary | String | Description             |
| ----- | ------ | ------ | ----------------------- |
| 0     | 0      | - - -  | No permissions          |
| 1     | 1      | - - x  | Execute only            |
| 2     | 10     | -w-    | Write only              |
| 3     | 11     | -wx    | Write and Execute       |
| 4     | 100    | r- -   | Read only               |
| 5     | 101    | r-x    | Read and execute        |
| 6     | 110    | rw-    | Read and write          |
| 7     | 111    | rwx    | Read, write and execute |

Commonly Used Permissions

| Symbolic        | Octal | Description                                                                  |
| --------------- | ----- | ---------------------------------------------------------------------------- |
| -rwx- - - - - - | 700   | Read edited and executed only by the owner.                                  |
| -rwxr-xr-x      | 755   | Anyone on the system can execute it but only the owner can read and edit it. |
| -rw-rw-r- -     | 664   | Allow a group to edit the file and allow others to read it.                  |
| -rw-rw- - - -   | 660   | Allow a group to edit the file and but don’t allow others to read it.        |
| -rw-r- - r- -   | 644   | Allow all the users to read the file but only the owner can edit and use it. |

## Linux Directory Structure

Containers for other files or other directories. These containers are arranged in a tree-like structure that each can be accessed by their name or a shortcut to the position.

| Directories/Folders | Purpose                                                     |
| ------------------- | ----------------------------------------------------------- |
| /                   | Root folder                                                 |
| /bin                | Binaries and other exe programs                             |
| /etc                | System config files                                         |
| /home               | Home directories                                            |
| /opt                | Optional/3rd-party software                                 |
| /tmp                | Temporary folders that are cleared on reboot                |
| /var                | Variable data, log files                                    |
| /export             | Shared file systems                                         |
| /lib                | System Libraries                                            |
| /lib64              | System Libraries, 64bit                                     |
| /lost+found         | Used to store recovered files                               |
| /media              | Used to mount removable media                               |
| /mnt                | Used to mount external file systems                         |
| /proc               | Provides info of currently running processes                |
| /root               | Home directory for root account                             |
| /sbin               | System administration binaries                              |
| /selinux            | Used to display information about SELinux                   |
| /srv                | Data served by the system                                   |
| /srv/www            | Web server files                                            |
| /srv/ftp            | File Transfer Protocol (FTP) files                          |
| /sys                | Used to display and configure devices known to Linux kernel |
| /usr                | User related programs                                       |
| /usr/bin            | Binaries and executable programs                            |
| /usr/lib            | Libraries                                                   |
| /usr/local          | Locally installed software                                  |

| /usr/local/crashplan/<type>

bin
etc
lib
log | Application Directory |

# Nano Editor

Simple editor that is relatively easy to pickup but with lesser features than vi or emacs.

CTRL + G for more information when in the nano editor. To enter the nano editor;

```python
nano file.txt
```

# Vi Editor

Steeper learning curve that may not be as intuitive but in return, offers more powerful features.

```python
vi file.txt #Start editing the file
vim file.txt #Vi but with more features
view fil.txt #Starts vim in view mode
```

## Vi Command Mode and Navigation

| Key | Function                |
| --- | ----------------------- |
| k   | Up one Line             |
| j   | Down one line           |
| h   | Left one character      |
| l   | Right one character     |
| w   | Right one word          |
| b   | Left one word           |
| ^   | Go to beginning of line |
| $   | Go to end of line       |

## Git Command Cheat Sheet

| Command/Terminology             | Explanation                                                                                                                                | Example                 |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- |
| HEAD                            | Latest commit of the current branch the user is on.                                                                                        | HEAD → Main             |
| HEAD → Feature/030524           |
| master/main                     | Starting branch/trunk of the repository                                                                                                    |                         |
| git status                      | Check if there’s a current repository in this directory.                                                                                   |                         |
| git init                        | Initialise a new git repository.                                                                                                           |                         |
| git add                         | Add the changes/specific files that can be separated to stage for a commit from working directory.                                         | git add characters.txt  |
| git commit                      | Provide message for commit to summarise the changes done.                                                                                  | git commit -m “message” |
| git commit -a -m “message”      | Commit all unstaged files                                                                                                                  |                         |
| git log                         | Return a log of commits done by every contributing collaborator.                                                                           |                         |
| git log —oneline                | Return a simplified log with only the commit message.                                                                                      |                         |
| git commit —amend               | Edit the previous commit message done.                                                                                                     |                         |
| git branch                      | View existing branches in the report. \* shows the branch that the user is currently on.                                                   |                         |
| git branch <branch-name>        | Create a branch but does not change the current branch.                                                                                    | git branch bugfix       |
| git checkout                    | Does the same as git switch but also more.                                                                                                 |                         |
| git switch -c <branch-name>     | Create a branch and changes to the branch.                                                                                                 | git switch -c bugfix    |
| git switch <branch-name>        | Switches to the pointed branch.                                                                                                            | git switch bugfix       |
| git branch -d <branch-name>     | Delete the selected branch. If you are currently on the branch it cannot be deleted. Switch to another branch before deleting this branch. | git branch -d deleteMe  |
| git branch -D <branch-name>     | Force delete a branch even if it is not fully merged with its parent branch.                                                               | git branch -D deleteMe  |
| git branch -m <new-branch-name> | Move/rename a branch by being on the branch first.                                                                                         | git branch -m newName   |
| git merge <branch-name>         | Switch to the target branch to be merged into and use the command.                                                                         |                         |

# Reasoning behind learning Linux

Linux is a highly flexible and customizable operating system, allowing developers to alter its code to meet their specific needs. This is a major advantage over PowerShell, which is not open-source and therefore not as flexible. Another advantage is efficiency. Linux is known for its efficient use of system resources, making it perform faster and more smoothly than many other operating systems. This is especially important for developers who often run complex tasks that can be resource-intensive.

Furthermore, Linux has a strong community of users and developers who actively maintain and update its software. This means that new features, improvements, and security patches are constantly being added. It also means that help and support are readily available, which can be crucial when encountering a problem or learning something new. Linux is popular in the server space because it's free and has a lower total cost of ownership compared to other operating systems. It's often the go-to choice for web servers, making it an important skill for web developers.
