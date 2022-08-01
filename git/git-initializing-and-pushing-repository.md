## Git Initializing and Pushing Files Into Remote Repository

## Contents

**1. To get Started**

    1.1  How to Open GitBash

    1.2 How to Work with Git Config

**2. Initializing a Local and Remote Repository**

    2.1 Creating a Remote Repository

    2.2 Creating a Local Repository Using Git Bash Command Line

    2.3 Checking the Status of Files

    2.4 Adding Files to Staging Area

    2.5 Committing Files to Local Repository

**3. Pushing Files from Local Repository into Remote Repository**

**4. Pulling Files from Remote Repository to Local Repository**

## 1.To get Started

## 1.1 How to Open GitBash

-   They are 2 methods to open git bash

**Method 1:**

-   Go to your working directory. Right-click and choose Git Bash Here option.

**![](media/e5930ebe90accd4ec9a266e34ec40f47.png)**

-   The Git Bash opens up and points to your current working Directory.

**![](media/087b372df61b5b526ecd1c9081adc837.png)**

**Method 2:**

-   Open Git Bash and change the current working directory to your local project by using cd command.

    **Syntax:** cd \<directory_name\>

    **Output:**

**![](media/9837a4898875ed7a53307a9cb53be584.png)**

## How to Work with Git Config

-   Configure local git with user name and email so we will know who pushed the code to github

**Syntax:** git config –global user.name “[name]”

git config –global user.email “[email address]”

**Output:**

## ![](media/2931a350725114ff46a839e472a1c1f1.png)

## 2.Initializing a Local and Remote Repository

You have two repositories

1.  Remote Repository
2.  Local Repository

## 2.1 Creating a Remote Repository

Follow the steps given below to initialize your remote Repository with Github.

**Step 1:**

-   First step, Sign into Github with your GitHub account. The below diagram shows a Githhub account.

**![](media/0648245e1a85745322a7dd941bbf58d5.png)**

**Step 2:**

-   To create a new remote repository on Github, click on the new button on the top left side.

    **![https://media.geeksforgeeks.org/wp-content/uploads/20200421144627/git-4.jpg](media/255b30cfd5ae85300d0f9e18443594f0.jpeg)**

**Step 3:**

-   Give a suitable name for your repository and click on create repository

**![](media/e96c8beeb9c38b14c6a63fc602e3b06f.png)**

**Note:** You can choose to initialize your git repository with a README file, and further, you can mention your project details in it. It helps people to know what this repository is about. However, it is optional. 

**Step 4:**

-   Remote repository looks as shown in below diagram.

**![](media/02fdcab91912119a879f3ca5c763f9df.png)**

## 2.2 Creating a Local Repository using GitBash Command Line

-   They are two ways to create a local repository using Gitbash command line.
-   Now run the commands in the following sequence.

**Method 1:**

**Git clone**:

-   Clones a remote repository into a new directory in the local computer.
-   Be sure to clone the project in a working directory that makes sense so you can easily remember where your local project lives.
-   This will automatically initialize a local repository in the working directory and can be verified by checking the presence of a hidden .git folder in the working directory.

**Syntax:** git clone [remote-repository-url]

**How to get the remote repository URL?**

-   Go to your remote repo on Github, Click on the green code button.![](media/b56e062d2753613e3fbe0ec44debc89d.png)
-   You can copy the remote repository url from there.

**![](media/02a1fec132d799a78628046609128af6.png)**

**Note:** Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.

-   Before running git clone, you can see that there is no repository with name **project_repo**

    ![](media/98828ebc39d758022c3abf6ddd2c4bae.png)

**Output:**

![](media/8120313bfa4439f8b93523b9d6cf4003.png)

-   Now go to your working directory, you can see that **project_repo** (local) repository is created with remote repository name.

![](media/4563dd8d03a4b667362a9bbb020c2076.png)

-   Open repository, it contains .git hidden folder and README.md file

![](media/94357d9f7af0a7c85a898d469ab4b81f.png)

-   The **.git folder** contains all information that is necessary for the project and all information relating commits, remote repository address, etc. It also contains a log that stores the commit history. This log can help you to roll back to the desired version of the code.
-   In README.md file, add any instructions that you want to share with others. Use Markdown to format headings, lists, links, etc. Here are some guides for the Markdown syntax:

[guides.github.com/features/mastering-markdown](https://guides.github.com/features/mastering-markdown/)

-   When updations done, commit the changes and push them to the remote repo. GitHub will display the nicely formatting ReadMe on the project page for the repo.

**Method 2:**

**Step 1:**

-   Initialize the local directory as a Git repository in the working directory.

**Syntax:** git init

**Output:**

**![](media/c0fe6e65e2f4d5e34c41f148538f9b48.png)**

-   Now go to your working directory, the hidden .git folder can be viewed.

    **![](media/78bb74249ccdc6b5a0bf1ee33aab7398.png)**

**Step 2:**

-   Add an empty README.md file in the working directory because the remote repository has a README.md file

    **![](media/26f6de46f211e4d54ab643020030ec9b.png)**

**Step 3:**

-   Rename the master branch of local repo to main

    **Synatax:** git branch -m main

    **Output:**

    **![](media/fba65f7914a129a64a4001064534780f.png)**

## 2.3 Checking the Status of Files

-   By “git status” you can see the staged files.

**Syntax :** git status

**![](media/93281ebe95f3028a8359f4b77ce947df.png)**

## 2.4 Adding Files to Staging Area

-   Add all the files of current folder(.) to staging

    **Syntax:** git add .

    **Output:**

    **![](media/44fae92f9ab681df0cba64d507c51d52.png)**

## 2.5 Committing Files to Local Repository

-   commit all the files from staging to local repo with a commit message

**Syntax:** git commit -m " file1 completed"

**output:**

**![](media/f7e7b36266fb22db5dceb3b23201c664.png)**

## 3. Pushing Files from Local Repository into Remote Repository

**Step 1:**

-   In the Command line prompt, add the URL to specify the remote Github repo to which we would want to push the files.

**syntax:** git remote add origin remote_repo_URL

**Output:**

**![](media/f1340e136babe7cbdeaec2d4aba8502b.png)**

**Step 2:**

-   push the files from your local repo to the remote repo.
-   Now, am going to push two files i.e., file1.md and file2.md from local reo to remote repo.

    ![](media/1f45e3b1e282e97a24d4cc3613e32df3.png)

**syntax:** git push

**Output:**

![](media/c5a65b2b387027377fcb41add31100a5.png)

-   Here the files have been pushed to the main branch of your repository.
-   Now in the GitHub repository, the pushed files can be seen.

    ![](media/e75ca141e2312d4d6ad016e54b8e9ea0.png)

**4. Pulling Files from Remote Repository to Local Repository**

**References:**

[**https://phoenixnap.com/kb/what-is-git-bash**](https://phoenixnap.com/kb/what-is-git-bash)

**https://dev.classmethod.jp/articles/git-bash-commands/**

**https://www.geeksforgeeks.org/working-on-git-bash/**

## 
