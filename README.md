# Git-Collaborative-With-GitHub
Thsi is a repo designed to help learners explore the capabilities of git and GitHub in helping them collaborate better and boost their productivity. It is created as a follow up to the GitHub Workshop conducted for Microsoft's Game Of Learners Season 4 participants to get them to better understand Git and GitHub

## What it covers 
1. Getting your project ready
   - Installing git on your machine
   - Configuration variables
      - Email, username and ignore file
   - Initializing a git project (`git init`)
1. Making and handling project changes with git
   - Staging files with `git add`
   - Recording changes using checkpoints(`git commit`)
   - Git under the hood
      - Working, staging and commit environments
      - File states
          - Tracked
             - Unmodified, modified, staged
          - Untracked
   - Deleting and renaming files
   - Ignoring files
1. Reviewing your projects history   
   - Seeing a record of changes using `git status`, `git log` and `git log --oneline`
   - Differentiating changes
     - `git diff` 
     - VSCode Source control tab
     - Comparing changes with specific commits. `git diff commitHash`
1. Rewriting history
   - Ammending commits
1. Imortalizing your project with GitHub
   - Creating a GitHub repository
   - Connecting your local repo with online repo
     - Setting up remote
       - Adding a remote (`git add remote name URL`)
       - Removing a remote (`git remote remove name`)
       - Renaming a remote (`git remote oldname newname`)
       - Listing current remotes (`git remote -v`)
   - Pushing changes
       - `git push`
1. The collaborative power of GitHub
   - Pull requests
   - Issues 
   - Labels
   - Projects
   - Milestones


## Let's get started
### Getting Project Ready

#### Installation
To be able to harness the full power of git, you'll need to have git installed on your machine. To successfully do this you can go to the [git website]([url](https://git-scm.com/)) and install.

For Windows users this will involve installing **git bash**.


#### Configuration variables
The first time you are using git, you will need to setup some configuration variables to store certain information about you, the user. The most common set variables are name and email. To configure them, you can run the following comman in your terminal (You can use the VSCode terminal or git bash for windows users)

```
//Configuring name
git config --global user.name "firstName SecondName"

//Configuring email
git config --global user.email "youremail@email.com"

```
The global flag makes sure that every project being tracked by git is using the same config variables
It is important to note that in email, using your github email makes it better for you even when it comes to authentication and authorization in given circumstances.



#### Initializing a project
Now that we have successfully downloaded, installed git and set our config variables  we can initialize a oroject to be a git repository. 
To initialize a project, navigate to the root directory of the project and run the following command
``` git
git init
```
This adds a hidden .git folder that helps in tracking all the changes of your repository(project).


### Making and handling project changes with git
Git offers you a bunch of ways to handle and manage changes throughout your project. We will look at the various ways we can efficiently use git to do so.

#### Staging files
Staging a file is moving the file to a sort of waiting bay as you prepare to commit it. You can add files to the staging area using this command

```
//Adding one file at a time
git add filename.extension

//Adding all files with changes in the current directory
git add .

```
#### Recording changes using checkpoints
Commits can be viewed as checkpoints marking certin stages during a projects timeline and giving a description about it for easy rememberance in future. It's kind of like how people visit certain places and leave a mark 'Clifford was here". 
Commits record changes that happen and give a message to describe the changes. After adding files to the staging are, we need to commit them. You can do that using the following command:
``` git
git commit -m "Descriptive message goes in here"

//Adding a commit title then a commit message
git commit -m "Title of the commit" -m "The description of the title"

```

#### Git under the hood
To better understand how git works, we need to have a high level understanding of a git environment and the different states of files that it works with. 

##### Working, staging and repository environments
Git promarily has 3 key environments where it works on. That is:
- Working Environment: Is the current state of your repo. Where you are building your project. This can be a local repository of your project's directory
- Staging environment: this is the buffer zone where all changes that have been added using the `git add` command exost waiting a commit
- Repository/Commit environment: this it where all goes after a commit. Files from staging area move here after a commit and are recorded in the project's history
