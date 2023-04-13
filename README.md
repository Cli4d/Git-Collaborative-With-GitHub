# Git-Collaborative-With-GitHub
Thsi is a repo designed to help learners explore the capabilities of git and GitHub in helping them collaborate better and boost their productivity. It is created as a follow up to the GitHub Workshop conducted for Microsoft's Game Of Learners Season 4 participants to get them to better understand Git and GitHub

## What it covers 
- [Git-Collaborative-With-GitHub](#git-collaborative-with-github)
  - [What it covers](#what-it-covers)
  - [Let's get started](#lets-get-started)
    - [Getting Project Ready](#getting-project-ready)
      - [Installation](#installation)
      - [Configuration variables](#configuration-variables)
      - [Initializing a project](#initializing-a-project)
    - [Making and handling project changes with git](#making-and-handling-project-changes-with-git)
      - [Staging files](#staging-files)
      - [Recording changes using checkpoints](#recording-changes-using-checkpoints)
      - [Git under the hood](#git-under-the-hood)
        - [Working, staging and repository environments](#working-staging-and-repository-environments)
        - [File States](#file-states)
      - [Deleting and Renaming files](#deleting-and-renaming-files)
      - [Ignoring Files](#ignoring-files)
    - [Reviewing your projects history](#reviewing-your-projects-history)
      - [Relfecting on the past](#relfecting-on-the-past)
      - [Differentiating changes](#differentiating-changes)
    - [Travelling back in time and rewriting history](#travelling-back-in-time-and-rewriting-history)
      - [Ammending commits](#ammending-commits)
    - [Working with branches](#working-with-branches)
        - [Merging](#merging)
        - [Merge Conflicts](#merge-conflicts)
    - [Immortalizing Your project with GitHub](#immortalizing-your-project-with-github)
      - [Setting up a GitHub account](#setting-up-a-github-account)
      - [Connecting your online repo to your local repo](#connecting-your-online-repo-to-your-local-repo)
      - [Setting up a remote](#setting-up-a-remote)
      - [Syncing With GitHub](#syncing-with-github)
    - [More Resources](#more-resources)
  - [Practice Time!](#practice-time)


## Let's get started
### Getting Project Ready

#### Installation
To be able to harness the full power of git, you'll need to have git installed on your machine. To successfully do this you can go to the [git website](https://git-scm.com/) and install.

For Windows users this will involve installing **git bash**.


#### Configuration variables
The first time you are using git, you will need to setup some configuration variables to store certain information about you, the user. 

The most common set variables are name, email and default code editor. To configure them, you can run the following commands in your terminal (You can use the VSCode terminal or git bash for windows users)

```bash
//Configuring name
git config --global user.name "firstName SecondName"

//Configuring email
git config --global user.email "youremail@email.com"

//Setting default editor as Visual Studio Code
git config --global core.editor "code --wait"


```
The global flag makes sure that every project being tracked by git is using the same config variables
It is important to note that in email, using your github email makes it better for you even when it comes to authentication and authorization in given circumstances.



#### Initializing a project
Now that we have successfully downloaded, installed git and set our config variables  we can initialize a oroject to be a git repository. 
To initialize a project, navigate to the root directory of the project and run the following command
```bash
git init
```
This adds a hidden .git folder that helps in tracking all the changes of your repository(project).


### Making and handling project changes with git
Git offers you a bunch of ways to handle and manage changes throughout your project. We will look at the various ways we can efficiently use git to do so.

#### Staging files
Staging a file is moving the file to a sort of waiting bay as you prepare to commit it. You can add files to the staging area using this command

```bash
//Adding one file at a time
git add filename.extension

//Adding all files with changes in the current directory
git add .

```
#### Recording changes using checkpoints
Commits can be viewed as checkpoints marking certin stages during a projects timeline and giving a description about it for easy rememberance in future. It's kind of like how people visit certain places and leave a mark 'Clifford was here". 
Commits record changes that happen and give a message to describe the changes. After adding files to the staging are, we need to commit them. You can do that using the following command:
```bash
git commit -m "Descriptive message goes in here"

//Adding a commit title then a commit message
git commit -m "Title of the commit" -m "The description of the title"

```

#### Git under the hood
To better understand how git works, we need to have a high level understanding of a git environment and the different states of files that it works with. 

##### Working, staging and repository environments
Git primarily has 3 key environments where it works on. That is:
- Working Environment: Is the current state of your repo. Where you are building your project. This can be a local repository of your project's directory
- Staging environment: this is the buffer zone where all changes that have been added using the `git add` command exost waiting a commit
- Repository/Commit environment: this it where all goes after a commit. Files from staging area move here after a commit and are recorded in the project's history

##### File States
Files exist in differnt states throughout the history of your repo. Primarily there are 2 main states in which the files in your repo can exist.
- **Tracked files -** these are files that have existed in your previous commits. That means that git is keeping a record of how they change thoughout your project.
Tracked files can also be in 3 categories. 
  - **Modified:** this means that the file has changed since the last commit.
  - **Unmodified:** file hasn't changed since the last commit
  - **Staged:** file has been moved to the staging area and is awaiting commit.   
- **Untracked files -** these are files that have been added after your last commit and git is not following their changes yet.
  
#### Deleting and Renaming files
Git usually handles file operations differently. There are 2 main ways to delete and rename a files managed by git
1. **Using the file system**
   - When deleting using the file system, delete the file as you normally would. However, git records the deletion as a change and you will have to `git add` and `git commit` the change.
   - When renaming the file, rename the file as you would using your operating system. Git will view this as 2 changes. First, *a deletion of the old file name*(the file that has been renamed) then *addition of the new renamed file*.
2. **Using git commands**
   - To delete, use the
```bash
git rm <filename>
```
  This records the change and moves it to the staging area ready for you to commit (`git commit -m "message goes here"`)
   - To rename, use 
```bash
git mv currentName newName
```
   This command also records the change and moves it to staging area ready for you to commit.
  
#### Ignoring Files
Sometimes you might need to keep some sensitive files untracked by git for security reasons. This is where `.gitignore` comes in handy.

Commonly ignored files include
- Files containing sensitive info e.g API Keys, tokens, passwords etc.
- System files
- Node modules
- Personal notes

To ignore a file, you create a file named `.gitignore` and have it in the root directory of your project. In the file you can add the names of the files and directories you want to be ignored by git.  


### Reviewing your projects history  
#### Relfecting on the past
Git allows you to always look at the past history of your project and how it is changing at the moment.   
```bash
git status
``` 
This command allows you to always check the current state of your project at any point and time. It will show what states the files are in and whichever changes are waiting to be *added* or *committed*.

```bash
git log
``` 
This command shows all the commits/checkpoints in your project's history. To exit/quit the log, press `Q`. 

If you have so many commits, the information displayed by `git log` might be overwhelming. To show a simplified view of your logs, you can use
```bash
git log --oneline
```  

#### Differentiating changes
In git you can always look at the differences between your current version of the repo and other previous ones. The command used for this is
```bash
git diff
```
It shows the differences between files in your repo.  

`git diff` can sometimes get messy on the terminal when you have lots of changes and files. You can use **Visual Studio Code's Source Control tab** to view differences in a clean and orderly way.   

To open Source control tab on VSCode, use `ctrl+Shift+G` in windows or `Command + Shift + G` for mac users.  

Once you open, just click on a file to open a view of the differences in the file.  

On the terminal you can compare the current project state with an earlier version using the command
```bash
git diff <commit hash>
```

The **commit hash** is the identifier (usually a hexadecimal) attached to the logs displayed by running `git log` or `git log --oneline`. It is also called **commit ID** at times.

There are better and more specialized tools to use when doing a lot of difference comparison. You can checkout **GitLens**. There is a VSCode extension, check [here](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)


### Travelling back in time and rewriting history
You can always change the current state of your repo to how it ways in a certain point of your project's history. This can be done because of various reasons.  

To do this, 
```bash
git reset <commit hash>
```
This command resets the repo to the state it was in that commit. However, it **doesn't delete the changes** you have made since then. It only unstages and uncommits them.  

To reset and delete changes made, you use the `--hard` flag.
```bash
git reset --hard <commit hash> 
```
**CAUTION:** This is a dangerous command and should therefore be used with a lot of care

#### Ammending commits
The beauty about git is that you can not only travel back in time during your project's history but you can also change history.  

To ammend the commits you had previously made, you can use
```bash
git commit --amend 
```
This opens up your code editor and allows you to change whatever you wrote in your commits

### Working with branches
Branches are alternative timelines/versions of your code/project.

The exist to experiment with your code and to try out different features and changes without messing up the original code. It is like a personalized sandbox.

To see all the branches existing in your repo use 
```bash
git branch
```
To create a branch, you use
```bash
git switch -c branchName

//or use
git branch -checkout branchName

//or use
git checkout -b branchName
```
This creates a branch with your specified *branchName* and switches you from the main branch (or the branch you were in) to the created branch.

To switch to another existing branch, you use
```bash
git switch branchName

//or use
git checkout branchName
```
##### Merging
After making your changes in the branch and confirming it works well, you might need to add the changes in the created branch to your main branch. This is called **merging**.   
To merge
- Switch to the main branch first then run the command
```bash
git merge createdBranchName
```
This will merge all the changes made on the created branch to the main branch.

After merging the two branches, it is good practice to delete the created branch as it is same as the main branch. To delete a branch 

```bash
git branch -d branchName

//OR
git branch --delete branchName

git branch -D branchName
```

This sequence of doing things is called **git flow**. It involves
1. Creating a branch
2. Making changes/fixes in the created branch
3. Merge the new branch to main branch
4. Delete the merged branch

##### Merge Conflicts
Changes can sync well between the files modified in the created branch and the main branch. However in other occassions you can have problems during merging. This are called **merge conflicts**.

They occur when you are merging 2 branches but different changes have been made to the same file in the 2 branches.

Merge conflicts invoke the terminal to open your default editor and to show ther merge conflicts. It is upon you to **resolve the merge conflicts**.   
To do this you can use the editor to choose what to retain and what to delete.

### Immortalizing Your project with GitHub
GitHub is a user interface that gives a smoother alternative to interact with git.  

It also gives a cloud storage to your git projects to make them easily accessible.

GitHub has also more features including project management and CI/CD. 

#### Setting up a GitHub account

Go to [GitHub Website](http://github.com/) and create an account using your email and passowrd. 

#### Connecting your online repo to your local repo
Mostly at any time, there exists 2 repos in your workspace:
- **Local repository**: this is the project file existing in your machine and where you work with using the git terminal
- **Online repository/GirHub repository**: this is usually the same as your local repo but esists as a GitHub repo. It exists in the cloud and can be easily accessed.


#### Setting up a remote
Remotes are the connection that exists between your local repo and your GitHub repository. It is useful in syncing changes between your online and local repo

To setup a remote 
```bash
git remote add remoteName URL
```
The **remoteName** can be anything but the most commonly used is origin.   
The **URL** is the link to your online repo from GitHub

These are other commands to help you manipulate your remotes
```bash
//removing a remote
git remote remove remoteName

//renaming remotes
git remote oldName newName

//Display the remotes
git remote

//Or
git remote -v
```

More remotes in your local repo means you can sync changes done to multiple online repos

#### Syncing With GitHub
To make full use of online repos, one has to sync changes made to the local repo with the online one and vice-versa.

To push changes from your local repo to the online repo. This is done after setting up the remote.   

The first time doing this
```bash
git push -u remoteName branchName

```

The **-u flag** is an upstream and it is set to tell git the remote and the branch(in this case master) where the commits are to be pushed to. The upstream is only set once. 

Next time you are pushing, 
```bash
git push
```

To clone an online repo to the local machine use
```bash
git clone URL
```
The **URL** is the link to the online repo and can be obtained from GitHub

To get changes from the online repo to the local repo you can:
- **Fetching**
```bash
git fetch
```
This downloads info from the remote/online repo to the local repo. It only gets the infomation, but does not merge with what is in the local repo

- **Pulling**
```bash
git pull
```
This is a combination of `git fetch` and `git merge`. It fetches the info from the remote repo and merges with the local repo.   
`git pull` requires an **upstream to be set** and can have *merge conflicts*

### More Resources

1. **Git and GitHub basics** - You can check this in-depth tutorial on basics of Git and GitHub [video tutorial](https://www.youtube.com/live/TB7m05rilw4?feature=share)   
Covers:-
- What is Git and GitHub
- Setting up a GitHub account
- Creating a repository 
- Setting up a Profile readme

2. **Git and GitHub Definitive guide:** an indepth guide to git getting started with git and GitHub [here](https://docs.google.com/presentation/d/1lmnOt-wBKgtuW6RH8EtFcbr2Znygkydzi_JxrIs5Pkk/edit?usp=sharing)

1. **GitHub Skills:** learn how to use GitHub with interactive courses designed for beginners and experts. Check it [here](https://skills.github.com/) 

1. **Game of Learners Season 4: GitHub Workshop Slides:** Access the workshop slides [here](https://www.canva.com/design/DAFcfzJZzqM/b-Ag7G2JUH8w-Zd5BDm84w/view?utm_content=DAFcfzJZzqM&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)

2. **GitHub Learning paths on Microsoft Learn:**
   - **Manage source control** - Learn how GitHub enables you to build a modern source control strategy that fosters collaboration and enables you to automate your build and deployment processes. Click [here](https://learn.microsoft.com/en-us/training/paths/az-400-manage-source-control/)
   - **Collaborate with others with Markdown and GitHub Pages** - Learn how to use Markdown to effectively communicate with others in your GitHub issues, pull requests, comments, and documentation. Then learn how to build project sites and blog posts to promote your projects with GitHub Pages. Click [here](https://learn.microsoft.com/en-us/training/paths/collaborate-markdown-github-pages/)
   - **Manage the lifecycle of your projects on GitHub** - Take full control of your GitHub projects. Through work planning and tracking, effective branching strategies, and extending GitHub through its API, manage releases all the way from idea to working software in the hands of your users. Click [here](https://learn.microsoft.com/en-us/training/paths/manage-project-lifecycle-github/)

## Practice Time!

To get some hands on practice with git, I have created some 2 interactive games in the Games folder of this repo. One is for individual trial and the other game is for you (Game of Learners participants) to do in your Game of Learners teams.

Head over to the folder, read the game instructions and start the game. Use this README file as a reference to the git commands and explanations. 

3. **Feel free to share with your friends so they can play the git game as well:)**

