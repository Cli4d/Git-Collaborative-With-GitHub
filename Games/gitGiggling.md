# Git Giggling: The Meme Game

Welcome to the Git Giggling: The Meme Game! This is a fun activity that will help you practice using Git and GitHub while also having fun sharing memes. In this game, you will be creating a markdown file where you will add memes that describe certain feelings, your favorite movies, superheroes, and more. Follow the steps below to get started.

## Step 1: Fork the Repository

First, you need to fork this repository to your own GitHub account. To do this, click on the "Fork" button at the top right corner of the repository page.

## Step 2: Clone the Repository

Next, you need to clone the repository to your local machine. To do this, copy the URL of your forked repository and run the following command in your terminal:

```bash
git clone <URL>
```

Replace <URL> with the URL of your forked repository.


## Step 3: Create a New Branch

Create a new branch in your local repository where you will be making changes. This is important because it allows you to work on changes separately from the main branch and avoid conflicts. To create a new branch, run the following command:

```bash
git checkout -b <branch-name>

OR

git switch -c <branch-name>
```

Replace <branch-name> with a name of your choice for the branch.

## Step 4: Edit the Markdown File

In the submissions directory of your cloned repository, you will find a file called memes.md. This is where you will be adding memes. Open this file in your text editor and start adding memes.

For example, you can add a meme to describe your favorite movie like this:

```md

### My Favorite Movie

![Meme](<insert image URL here>)

```

Replace <insert image URL here> with the URL of the meme image you want to add.

You can also add a meme to describe a feeling, like this:

```md
### Feeling Happy

![Meme](<insert image URL here>)
```

And a meme to describe your favorite superhero, like this:

```md
### My Favorite Superhero

![Meme](<insert image URL here>)
```

Feel free to add as many memes as you want! Be as creative as you can be here.

## Step 5: Commit and Push Changes

Once you have added the memes, it's time to commit and push the changes to your branch. To do this, run the following commands in your terminal:

```bash
git add memes.md
git commit -m "Added memes"
git push origin <branch-name>
```

Replace <branch-name> with the name of the branch you created in Step 3.

## Step 6: Create a Pull Request

Go to your forked repository on GitHub and create a new pull request from your branch to the main branch of the original repository. This will allow you to submit your changes for review and merge.

Add a descriptive title and description for the pull request.

## Step 7: Resolve Merge Conflicts

In some cases, you may encounter merge conflicts when creating a pull request. This happens when there are conflicting changes made to the same file by different users. If you encounter a merge conflict, don't panic! It's a common issue and can be resolved easily.

To resolve a merge conflict, you need to manually edit the conflicting code and choose which changes to keep. Once you have resolved the conflict, commit and push your changes to your branch.

## Step 8: Repeat the Process
Repeat steps 2-6 for additional memes to the markdown file.


## Congratulations
You have successfully played Git Giggling: The Meme Game using Git and GitHub! To practice more, repeat the process by creating a new branch and adding more memes.  
Don't forget to commit and push your changes and create a new pull request for each branch.

## Share your creation
Share your vision board with the Game of Learners community using the hashtag #GOLvisionboard, #GOLSN4, #GOLSeason4, #GameofLearners

Have fun and keep learning!