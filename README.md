# GithubWorkshop
In this repository you will find general information to use Git and Github to keep projects organized and all your collaborators informed of the progress. 

**Table of Contents**

1. [Installation and Set-up](#installation-an-set-up)
2. [Repositories, Commits, and Pushes](#repositories-commits-and-pushes)
3. [Projects](#projects)
4. [Issues](#issues)
5. [Summary of Git and Github Commands](#summary-of-git-and-github-commands)
5. [Additional Information](#additional-information)

## Installation and Set-up

### Installation

 The installation of Github depends on the operating system, you can find how to install git in your computer [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

 There are different software that allow you to manage all git changes in you computer. However, I strongly suggest that you use the terminal, the command window, or any of the following terminals, [iTerm2](https://www.iterm2.com/) (if in Mac), [terminator](https://terminator-gtk3.readthedocs.io/en/latest/) (if in Linux), Powershell, [cmder](https://cmder.net/) (if in Windows), or any other Unix based terminal. 

 This course is designed to use the terminal, for that the following are some basic commands:

 - `cd <directory>`: change directory.
 - `cd ..`: previous directory.
 - `mkdir <directory>`: make directory.
 - `ls`: list directory (Mac, Linux, cmder).
 - `dir`: list directory (Windows).
 - `rm -r <File or folder>`: remove file or directory. **Danger: documents eliminated with this command cannot be recover.**
 - `source <.profile_file>`: activate profile.

### Git Set-up
 Once installed, we can open the terminal and write the command `git --version` the terminal should give you back version of git installed in the computer.

 Now, we can do the general set-up of git to be able to upload files into the Github, for that we need to tell git our name and email using the following commands,

 ```bash
 git config --global user.name "Daniel Gonzalez"
 git config --global user.email "github_user_email@email.com"
 ```

 This will allow you to commit and push changes into repositories that you have access, keep in mind that each time that you push a change you will need to type your password, in order to save your password in the cache please look into this [link](https://help.github.com/en/github/using-git/caching-your-github-password-in-git).

 Before we begin doing pushes into this repository we also need to set-up the default editor of git, this will be used in few cases. There are a handful of editors out there, the set up of some of them can be found [here](https://swcarpentry.github.io/git-novice/02-setup/index.html). For the purpose of this Workshop we will set-up the nano editor that is common to all OS.

 ```bash
 git config --global core.editor "nano -w"
 ```

 **Note:** Keep in mind that most Linux distributions have vi or vim as default editor. So, if you miss to change it and haven't used vim in the past, the way to exit the document without saving is press escape and then type `:q!` and then enter.

## Repositories, Commits, and Pushes

 Git is a version control software that allow its users to keep track of changes made in different files in a respective repository. Think of it as a cloud without the automatic online update and for files with sizes smaller than 100 MB. To use git we don't necessary need to use Github, git can track the changes made in the repository in your computer, allowing you to go back in time and create branches if needed.  On the other hand, Github is an online platform that allows you to have your repository online, collaborate with others easier, and have a legacy of your scripts, and your projects.

 Now, to create a repository in the computer we can go to the folder that we want to keep track of the changes and use the command `git init`, this will create a .git file in the folder and from there you can use the git commands to track this changes. Another way to create a repository is to do it from Github and then clone it into the computer, for that you can go to your profile and click on new repository and follow the steps to create it. 

 For this workshop we will be using this repository to test the functionalities of git. First we will need to clone this repository, to do that please open the terminal and `cd` to the folder where you want to have this repository, then use the following command,

 ```bash
 git clone https://github.com/DGD042/GithubWorkshop.git
 ```

 This command will download the repository in your computer as a separate folder. Yo clone a repository you don't need to be a collaborator, but in order to do changes you would need to have certain privileges.

 Now, in order to know if some changes have been made into the online repository we can use the following commands

 ```bash
 git fetch
 git status
 ```
 
 These commands will tell you if you are behind in the commits made in the online repository, if there are changes made in the repository you can use the command `git pull` to download the last the latest changes made into the online repository. 

 Let's add a document into the repository and go through the steps to upload it. 

 1. Add the document or folder to the tracking list.
 2. Commit changes and add a comment. 
 3. Push the changes to upload them into the online repository.

 The steps in terminal look like,

 ```bash
 git add <files/folders>
 git commit -m "Comment of the commit"
 git push
 ```

 after the `git push` the terminal window should ask your password for Github and then it should upload the documents into the online repository. If you do changes in the files that are already on the track list it is not necessary to do the `git add` command, you can commit the changes in those files directly if you use

 ```bash
 git commit -am "Comment of the commit"
 git push
 ```

 If you want to see all of the commits that have been made in the repository you can use the command `git log`, this helps you to keep track of the changes made and it also allows you to go back in time to an specific commit, to do that you can use

 ```bash
 git checkout <commit ID>
 ```
 This will change your local folder to the time at which that commit was made, all of the files created after that will not be there and all of the changes made in any document will not be there as well. Usually the commit IDs are long, you can just pick the first 6 characters and you will be good. To go back to the current time use

 ```bash
 git checkout master
 ```

 For further information of how to explore the history take a look at this [link](https://swcarpentry.github.io/git-novice/05-history/index.html)

### Ignoring Files
 
 As I mentioned above it is not recommended to upload files with sizes higher than 100 MB, and I strongly recommend not to upload files with sizes higher than 15 MB, the idea of a repository is to have a light folder that only includes  only the scripts and the documentation of the project or package, it is not recommended to add data or results, and there is where the .gitignore file comes into play.

 This file will essentially ignore the files that you include in it, preventing git to track changes of those files and allowing you to have this files in the repository without any problem. I encourage you  to read this [link](https://swcarpentry.github.io/git-novice/06-ignore/index.html) to learn more about the file or see the one that is created in [this repository](https://github.com/DGD042/GithubWorkshop/blob/master/.gitignore) to have an idea of how this file works.

 If you definitely need to upload large size documents into the repository, I suggest you to take a look at [Git Large File Storage](https://git-lfs.github.com/), this complement could help you save large files in the repository as links to a cloud, keeping your repository small while having the data there.

## Projects
 In this and the next sections I will turn a bit away from the terminal window and start working on the Github repository itself. Recently Github release the [Projects tab ](https://github.com/DGD042/GithubWorkshop/projects) in the repositories for free. The [Projects tab](https://github.com/DGD042/GithubWorkshop/projects) grants you and your collaborators the ability to create projects inside that repository, allowing everyone to keep track of what is missing, what is been done, and what is already done, and how is responsible for making those changes.

 To create a project go to the [Projects tab](https://github.com/DGD042/GithubWorkshop/projects) and click on 'New Project', a window will appear where you can set your project name, description and the template (if needed), I strongly recommend using an automated kanban template as it allows you to keep track of issues automatically. Once you have created the project you will be taken to the project page, where you will have 3 columns: "To do", "In progress", and "Done", and some information in the "To do" column on how to set up the rest of the project.

 Adding cards in the project allows everyone to keep track of the tasks that need to be address to finish the project, but one of the most useful things about projects is their integration with issues, and the automated process that we can do with that.

## Issues

 Issues is one of the most useful features of Github, this feature helps you keep track of things that needs to be corrected or added into the repository. But not only that, they can be assigned to one person in charge of doing the changes, and they can be linked to projects, labels and milestones. To create a new issue you can go to the [Issues tab](https://github.com/DGD042/GithubWorkshop/issues) and press on "New issue", it will prompt you a window where you can write the title and a description of the issue, on the right panel you can assign the issue and link it to projects, labels and milestones. You can also add documents or figures showing what needs to be done. 

 Once you have created the issue, you can go to the project that you created before and assign the issue to the "To do" or "In progress" columns. If you have selected an automated kanban template for the project once the issue is closed it would jump automatically to the "Done" column. Also, if the issue is reopen it will jump to the "In progress" column. This is important, as you can close an issue with a commit in the command window and everything will be updated automatically, and the commit that closed that issue will be saved in the history of the issue, meaning that if there is a problem in the repository after that issue was closed you can go and see what commit did that change and check what was changed in that commit.

 In order to close an issue with a commit in terminal window, you need to add any of the word in the list, followed by the number of the issue as "#XXX",

 - close
 - closes
 - closed
 - fix
 - fixes
 - fixed
 - resolve
 - resolves
 - resolved

 Here is an example of how to do it is the following,

 ```bash
 git add <files/folders>
 git commit -m "Closes #2 Documents added"
 git push
 ```

## Branching and Pull Requests
 The last thing that I want to show in the use of the Branches and how to do Pull Requests in the repository. Let's think that we want to implement a new feature in our package, or do strong changes in on script that might cause the functionality of the project be compromised. In those situation is where branches can be really useful.

 To create a branch you can use

 ```bash
 git checkout -b <branch name>
 ```
 now all of the changes that you make will be stored in this branch, to go back to the master just enter the command `git checkout master`. 

 Once do changes in this branch you can commit them and push them into the online repository with 

 ```bash
 git commit -am "comment"
 git push -u origin <branch_name>
 ```
 this will automatically create a Pull Requests in the repository. In collaborative repositories, a Pull Requests is made when a developer wants his changes to be applied in the master, there one of the admins of the repository can see the changes made and merge the branch to the master if nothing is conflicting and all is working good. Pull Requests can be linked to issues and to projects and can be commented as well. All of this process can be made in the [Pull Requests tab](https://github.com/DGD042/GithubWorkshop/pulls).

 Everyone in the repository can see the active branches by using the commands 
 ```bash
 git fetch
 git branch
 ```
 and any collaborator can access to other branches by entering `git checkout <branch_name>`. More information about Branches and Pull Requests can be found in 

 - [Branches](https://thenewstack.io/dont-mess-with-the-master-working-with-branches-in-git-and-github/#:~:text=The%20way%20git%2C%20and%20GitHub,have%20one%20or%20more%20branches.)
 - [Merging](https://help.github.com/en/github/using-git/getting-changes-from-a-remote-repository)

## Summary of Git and Github Commands

 - `git init`: initialise a repository in the folder.
 - `git clone <git repository>`: download a repository and link it to a folder in your computer.
 - `git fetch`: retrieve the HEAD of the online repository.
 - `git status`: shows the latest changes made in the local repository, if `git fetch` is run first it will also tell you the how many commits you are behind on the online version.
 - `git pull`: download the latest online version of the repository.
 - `git add <files/folders>`: add files to the tracking list.
 - `git commit -m "Comment of the commit"`: apply changes in the repository.
 - `git commit -am "Comment of the commit"`: apply changes to the all the added documents in the repository.
 - `git push`: upload changes to the online repository.
 - `git log`: displays all the commits made in the repository.
 - `git checkout <commit_ID>`: go back in time to that commit.
 - `git checkout master`: go back to the master.
 - `git checkout -b <branch_name>`: create a new branch.
 - `git branch`: See current branches.

## Additional Information

 In this section you will see further information if you want to keep learning how to use Git or other projects.

 - Swcarpentry git course [https://swcarpentry.github.io/git-novice/](https://swcarpentry.github.io/git-novice/).

 - Git Large File Storage [https://git-lfs.github.com/](https://git-lfs.github.com/)

 - Markdown Cheatsheet [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

 - Markdown tutorial [https://www.markdowntutorial.com/](https://www.markdowntutorial.com/)

 - MultiMarkdown Software [https://multimarkdown.com/](https://multimarkdown.com/)
