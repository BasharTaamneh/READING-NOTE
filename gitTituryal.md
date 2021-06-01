# **git-tutorial**
## *INTRODUCTION*

- **Prerequisites**

it is highly recommended that you have a solid understanding of the Terminal (for Mac) or Command Line (for Windows and Linux).

&nbsp
- **Version Control**

Version Control is a system that allows you to revisit various versions of a file or set of files by recording changes. Through version control, one can revert a file or project to a previous version, track modifications and modifying individuals, and compare changes. By utilizing a Version Control System (VCS), mistakes with files can easily be rectified.

&nbsp
- **Local Version Control**

Many years ago, programmers created Local Version Control systems. A Local VCS entails one database on your hard disk that stores changes to files.

&nbsp
- **Centralized Version Control**

The need for collaboration within a developer team on a single file or set of files led to the advent of the Centralized Version Control System (CVCS). This system entails a single server storing all changes and file versions, which can be accessed by various clients. This streamlined the collaboration process (by eliminating the need to involve all local databases), allowed programmers to have more knowledge of team members’ activities with certain files, and gave administrators much more control over divvying up revision privileges.

&nbsp
- **Distributed Version Control**

A Distributed Version Control systems (DVCS) addresses the major vulnerability of the CVS: the server as a single point of failure. If a CVS goes down, collaborators cannot work with each other on a file or save changes and new versions. Also, in the event of corruption of a central database’s hard disk — with the absence of backups — all work will be lost, except for any portions on local machines.

To prevent this type of catastrophic loss, a DVCS allows clients to create mirrored repositories. These data backups can be easily be placed on the server to replace any lost information.

Because the DVCS allows for multiple mirrored repositories, programmers working in teams can collaborate with each other in various ways to complete a joint project, which enables the use of various simultaneous workflows.

&nbsp
- **So, what is Git?**

##### ***Snapshots***

Git is a DVCS that stores data in a file system made up of snapshots. Each time you save a changed version of your project — called commit — Git creates a snapshot of the file and stores a reference to it. If the file has not changed, Git only stores a reference to the already-stored identical version of it.

Local Operations

Git mostly relies on local operations because most necessary information can be found in local resources. This allows for process expediency because a project’s history resides on the local disk, eliminating the need to fetch history information from the server, and allowing one to continue work on a project even when not online or on a VPN.

Tracking Changes

Every single change applied to any file or directory is tracked by Git. And, as the gatekeeper, Git will always detect file corruption or loss of information in transit.

Loss of Data

Git is set up to greatly minimize the possibility of irreversible damage to files, such as accidentally lost data. Git makes it extremely difficult for a snapshot of your file that is committed to be lost.

States

Files in Git can reside in three main states: committed, modified and staged.

Committed

Data is securely stored in a local database

Modified

File has been changed but not committed to the database

Staged 

Flagged a file’s changes version to be committed in the next snapshot

![explaning image](https://blog.udemy.com/wp-content/uploads/2015/08/image066.png)

&nbsp
- **History of Git**

Git traces its roots to the open source software project Linux kernel. Developers of this project began using a DVCS called BitKeeper in 2002. In 2005, many of these developers stopped using this DVCS due to tension between the Linux kernel community and the company behind BitKeeper’s and the eventual revocation of the DVCS’ gratis status. 

&nbsp
- **Download Git**

In order to use Git, your computer must have it available. If you already have Git on your computer, you should make sure you have the latest version.

Git can be installed in three ways:

1. Install as a package
2. Install via another installer
3. Download and compile the source code.

                                          Mac OS X
Terminal

The simplest method for installing Git on a Mac (for Mavericks 10.9 and above) is running Git from the Terminal. If Git is not installed, you will see a prompt for installation.

Git Website

You can also download Git by visiting this link and following the posted directions:

http://git-scm.com/download/mac

GitHub

A third option is to install Git as part of the GitHub for Mac install. GitHub is repository hosting service, which we will discuss in a future section.

Download GitHub for Mac via the following link:

http://mac.github.com

                                              Windows

Git Website

You can download Git by visiting this link and following the posted directions:

http://git-scm.com/download/win

GitHub

Install Git as part of the GitHub for Windows install.

http://windows.github.com

                                              Linux

Package Manager

You can try installing Git via your distribution’s inherent package management tool.

For Fedora:

$ sudo yum install git
For Ubuntu:

$ sudo apt-get install git
Git Website

To download Git for Linux, visit this link and follow the posted directions:

http://git-scm.com/download/linux

&nbsp
- **GUI Clients**

You can access a variety of GUI clients for Mac, Windows, and Linux via the following link:

https://git-scm.com/downloads/guis

&nbsp
- **Initial Customization**

After making sure Git has been installed, you should perform some customization steps, which should only need to be completed once on any machine. To change settings, you can repeat these steps.

#### **Configuration of Variables**

An inherent Git tool called git config allows the setting of configuration variables that control aspects of Git’s operation and look.

#### **Identity Setting**

After installing Git, users should immediately set the user name and email address, which will be used for every Git commit.


*Type the following into Terminal or Command Line:*

    git config --global user.name "Jane Smith"

    git config --global user.email "example@email.com"

  &nbsp

*To confirm that you have the correct settings, enter the following command:*

    git config --global user.name (should return Jane Smith)

    git config --global user.email (should return example@email.com)

*By using the –global option, these Git settings apply to anything on the system. To use different identity settings for a specific project, change the working directory to the desired local Git repository and repeat the steps above without using –global.

&nbsp
- **Default Text Editor**

Without configuration of a default text editor, Git will use the system’s default editor–most likely Vim. To configure a different text editor, such as Emacs, type the following into your Terminal or Command Line:

    $ git config --global core.editor emacs

Note: For some editors, you may need to find specific instructions for default configuration.

&nbsp
- **Check Settings**

To check settings, use the git config --list command.

Example:

    $ git config --list

    user.name=Jane Smith

    user.email=example@email.com

    color.status=auto

    color.branch=auto

    color.interactive=auto

&nbsp
- **Getting Help**

There are three ways to get more information on a particular command, by accessing the manual:

    git help command

    git command --help

    man git-command

&nbsp
## *Setting up a Git Repository*

- **Importing**

To import an existing project or directory into Git, follow these steps using the Terminal or Command Line:

1. Switch to the target project’s directory
Example:

    $ cd test (cd = change directory)

2. Use the git init command
     
      $ git init
  
  **Note:** At this stage, you have created a new subdirectory named .git that has the repository files. Tracking has not commenced.

3. To start tracking these repository files, perform an initial commit by typing the following:

    $ git add *.c
    $ git add LICENSE
    $ git commit -m “any message here”
Now, your files are tracked and there’s an initial commit. We will discuss the particular commands in detail soon.

&nbsp
- **Cloning**

You can also create a copy of an existing Git repository from a particular server by using the clone command with a repository’s URL:

    $ git clone https://github.com/test

By cloning the file, you have copied all versions of all files for a project. This command leads to the creation of a directory called “test,” with an initialized .git directory inside it, which has copies of all versions of all files for the specified project. The command also automatically checks out — or retrieves for editing — a copy of the newest version of the project.

To clone a repository into a directory with another name of your choosing, use the following command format:

    $ git clone https://github.com/test mydirectory

The command above makes a copy of the target repository in a directory named “mydirectory.”

&nbsp
## *Workflow*

- **Local Repository Structure**

The local Git repository has three components:

1. Working Directory: The actual files reside here.
2. Index: The area used for staging
3. Head: Points to the most recent commit

![image](https://blog.udemy.com/wp-content/uploads/2015/08/image036.png)

&nbsp
- ** Saving Changes**

All files in a checked out (or working) copy of a project file are either in a tracked or untracked state.

#### **Tracked**

Tracked files can be modified, unmodified, or staged; they were part of the most recent file snapshot.

#### **Untracked**

Untracked files were not in the last snapshot and do not currently reside in the staging area.

*After cloning a repository, files have tracked status and are unmodified because they have been checked out but not edited.

&nbsp
- **The Life Cycle of File Status**

1. After you edit a file, Git flags it as modified because of changes made after the previous commit.
2. You stage the modified file.
3. Then, you commit staged changes.

![image](https://blog.udemy.com/wp-content/uploads/2015/08/image006.png)

&nbsp
- **Check File Status**

To determine the state of files, utilize the git status command:

    $ git status

On branch master

nothing to commit, working directory clean

*This information indicates which branch you’re on (we will cover branches in a later section) and states “working directory clean,” which means that files have tracked or modified status at the moment. Also, no untracked files are present because Git has not listed any.

&nbsp 
- **Tracking and Staging a New File**

#### *Single File*

Track one file only by using the following format:

    git add filename

#### *All Files*

Track all files in a repository by using the following command:

    $ git add *

*After using these commands, files are tracked and staged for committing.

After adding a new file called EXAMPLE, you would see information regarding changes to be committed when using the git status command:

    $ git status
    On branch master
    Changes to be committed:
    (use "git reset HEAD ..." to unstage)

    new file: EXAMPLE

This information tells us that there are changes to be committed and that the file has been staged.

&nbsp
- **Committing a File**

After staging one or multiple files, you should commit the changes and record what you did within the commit message:

    $ git commit -m “made change x,y,z”

*This step has committed changes for the file or files (you can have one commit message for multiple files, if applicable) to the HEAD.

&nbsp
- **Committing All Changes**

    $ git commit -a

*This command commits a snapshot of all modifications to tracked files in the working directory.

&nbsp
- **Pushing Changes**

Next, you would push changes to a remote repository. We will discuss remote repositories in more depth in the next section. For now, we will look at a general overview of pushing changes to remotes.

Example:

    $ git push origin master

*This command pushes changes from the local “master” branch to the remote repository named “origin”.

*For cloned repositories, Git will automatically give the name “origin” to the server from which you cloned and the name “master” to your local repository. However, these names can be changed by the user.

&nbsp
- **Stashing Changes**

When you are not ready to commit changes but do not want to lose them either, **git stash** is a great option. This command temporarily removes changes and hides them, giving you a clean working directory. When you are ready to continue working on the changes, simply use the **git stash apply** command to retrieve the hidden changes.

&nbsp
## *Remote Repositories*

In order to collaborate on Git projects, you must interact with remote repositories, versions of a project residing online or on a network. You can work with multiple repositories, for which you can have read/write or read-only privileges. Teams can use remote repositories to push information to and pull data from.

&nbsp
- **Cloned Repositories**

As mentioned earlier, for cloned repositories, Git will automatically give the name “origin” to the server from which you cloned and the name “master” to your local branch.

to know more please visit this [link](https://blog.udemy.com/git-tutorial-a-comprehensive-guide/#1).