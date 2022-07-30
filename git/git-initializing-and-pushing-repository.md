## Git Initializing and Pushing Files Into Remote Repository

## Contents

**1. Initializing a Local and Remote Repository**

1.1 Creating a Remote Repository

1.2 Creating a new local repository using Git Bash command line

**2. Pushing Files into Remote Repository**

## 1. Initializing a Local and Remote Repository

You have two repositories

1.  Local Repository
2.  2\. Remote Repository

## 1.1 Creating a Remote Repository

Follow the steps given below to initialize your remote Repository with Github.

## Step 1:

-   Signin with your GitHub account

**![](media/0648245e1a85745322a7dd941bbf58d5.png)**

## Step 2:

-   Make Remote Repository on Github. Top left side ,click on the new button to create remote repo

    **![https://media.geeksforgeeks.org/wp-content/uploads/20200421144627/git-4.jpg](media/255b30cfd5ae85300d0f9e18443594f0.jpeg)**

## Step 3:

-   Give a suitable name of your repository and click on create repository

**![](media/e96c8beeb9c38b14c6a63fc602e3b06f.png)**

Note: You can choose to initialize your git repository with a README file, and further, you can mention your project details in it. It helps people know what this repository is about. However, it’s absolutely not necessary. But if you do initialize your remote repo with a README file using interface provided by GitHub, then your local repository won’t have this README file. So add README.md file in local repo

## Step 4:

-   Remote repository looks as shown in below diagram.

**![](media/02fdcab91912119a879f3ca5c763f9df.png)**

## 1.2 Creating a new local repository using Git Bash command line

-   They are 2 methods to open git bash for creating local repo

## Method 1:

-   Go to your working directory. Click right-click and choose Git Bash Here option.

**![](media/e5930ebe90accd4ec9a266e34ec40f47.png)**

-   The Git Bash is opened with your current working Directory.

**![](media/087b372df61b5b526ecd1c9081adc837.png)**

## Method 2:

-   Open Git Bash and change the current working directory to your local project by use of cd command.

    **Syntax:** cd \<directory_name\>

    **Output:**

**![](media/9837a4898875ed7a53307a9cb53be584.png)**

**Now run the commands in the following sequence.**

## Step 1:

-   Initialize the local directory as a Git repository in the working directory.

**Syntax:**

git init

**Output:**

**![](media/c0fe6e65e2f4d5e34c41f148538f9b48.png)**

-   Now go to your working directory, the hidden .git folder can be viewed.

    **![](media/78bb74249ccdc6b5a0bf1ee33aab7398.png)**

-   The .git folder contains all information that is necessary for the project and all information relating commits, remote repository address, etc. It also contains a log that stores the commit history. This log can help you to roll back to the desired version of the code.

## Step 2:

**![](media/1ea98ea5667928563a4815b0f35982d1.png)**

-   Add an empty README.md file in the working directory because the remote repository has a README.md file

    **![](media/26f6de46f211e4d54ab643020030ec9b.png)**

-   In readme.md add any instructions that you want to share with others. Use Markdown to format headings, lists, links, etc. Here are some guides for the Markdown syntax:

[guides.github.com/features/mastering-markdown](https://guides.github.com/features/mastering-markdown/)

-   When updations done, commit the changes and push them to the remote repo. GitHub will display the nicely formatting ReadMe on the project page for the repo.

## Step 3:

-   Rename the master branch of local repo to main

    **Synatax:**

    git branch -M main

    **Output:**

    **![](media/fba65f7914a129a64a4001064534780f.png)**

## Step 4:

-   By “git status” you can see the staged files.

**![](media/93281ebe95f3028a8359f4b77ce947df.png)**

## Step 5:

-   Add all the files of current folder(.) to staging

    **Syntax:**

    git add .

    **Output:**

    **![](media/44fae92f9ab681df0cba64d507c51d52.png)**

## Step 6:

-   commit all the files from staging to local repo with a commit message

**Syntax:**

git commit -m "lambda demo completed"

**output:**

**![](media/f7e7b36266fb22db5dceb3b23201c664.png)**

## Step 7:

-   Configure local git with user name and email so we will know who pushed the code to github

**Syntax:**

git config --global user.name “[name]”

git config --global user.email “[email address]”

**Output:**

**![](media/a6e4c8e9776fcb0508b8fe1996fb56ab.png)**

## 2. Pushing Local Repository Files into Remote Repository

## Step 8:

-   Specify the remote Github repo to which we would want to push the files

**How to get the Remote repo URL?**

-   Go to your remote repo on Github, Click on code**![](media/b56e062d2753613e3fbe0ec44debc89d.png)**
-   you will get the remote repo URL

**![](media/02a1fec132d799a78628046609128af6.png)**

Copy the URL and paste in command line

**syntax:**

git remote add origin remote_repo_URL

**Output:**

**![](media/f1340e136babe7cbdeaec2d4aba8502b.png)**

**Step 9:**

-   push the files to the remote repo

**syntax:**

git push --set-upstream origin main

## 

**References:**

[**https://phoenixnap.com/kb/what-is-git-bash**](https://phoenixnap.com/kb/what-is-git-bash)

[**https://dev.classmethod.jp/articles/git-bash-commands/**](https://dev.classmethod.jp/articles/git-bash-commands/)

**https://www.geeksforgeeks.org/working-on-git-bash/**

## 
