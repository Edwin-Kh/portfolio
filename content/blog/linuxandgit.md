---
title: Living in the terminal with Linux and Git
description: Learning notes for Linux OS and Git VCS
date: 2024-04-30
cover: gitbash.png
tags:
  - Linux
  - Git
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

| Command                 | Explanation                                                                                                         | Example        |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------- |
| ls                      | Show a list of files in the current directory that I am on/ pointing at.                                            | ls Downloads   |
| ls Downloads/file       |
| start/open              | Open the File Explorer at this current location.                                                                    | start .        |
| clear                   | Clear the terminal.                                                                                                 |                |
| pwd                     | Print the current working directory/location/path.                                                                  |                |
| cd                      | Change directory to the one I am pointing at.                                                                       | cd Downloads   |
| touch                   | Create a file/ updating a file                                                                                      | touch test.txt |
| touch Downloads/okay.py |
| mkdir                   | Make directory                                                                                                      | mkdir New File |
| rm                      | Remove file                                                                                                         | rm test.txt    |
| rm Okay.py              |
| rm -rf                  | Remove directory                                                                                                    | rm Image       |
| cat                     | Create single or multiple files, view content of a file, concatenate files and redirect output in terminal or files | cat file       |

## Linux Directory Structure

| Directories/Folders | Purpose                                      |
| ------------------- | -------------------------------------------- |
| /                   | Root folder                                  |
| /bin                | Binaries and other exe programs              |
| /etc                | System config files                          |
| /home               | Home directories                             |
| /opt                | Optional/3rd-party software                  |
| /tmp                | Temporary folders that are cleared on reboot |
| /user               | User related programs                        |
| /var                | Variable data, log files                     |

Git Commit Workflow

Work on Changes > Add Changes > Commit

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
