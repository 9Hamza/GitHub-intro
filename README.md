Windows Test 1 2 3

# Demo

This is a demo for a Git Tutorial.

## Step by Step Tutorial

- First thing I did is create a repository in GitHub. 
- Wrote on the README.md file
- Cloned this file by going to Terminal on my PC and written "git clone [link]"
[link] is a link that lets you clone the repository, it is found in the GitHub website.

- Before committing any changes, "git status" command shows you all of the files that have been updated, added, deleted but haven't been saved on a commit yet

If you create a new file, and you didn't add it to the main branch, when you do "git status", it will tell you that this created file is "untracked", which means git doesn't know about this file. To add that file, you do "git add [filename]", or "git add ." which tracks all the files that are listed (everything that needs updating basically).

- Now after you've added the changes, you can check that they're added by doing "git status" again. After that, they will need to be committed so, commit any changes writing on Terminal git commit -m "Added index.html" -m "some description"

The first -m "" is the main message or the header of the commit, and the second -m "" which is optional is the description (-m means message)

- So far, all of what we did is save our code or changes locally (on my pc only). The changes are not live on GitHub. 
- To make them live, we do "git push". BUT in order to push the changes, you have to prove to GitHub that you are the owner of that account. So we have to connect our local machine to GitHub somehow. The way this is done is by using SSH keys.

    We first generate an SSH key by "ssh-keygen -t rsa -b 4096 -C "email@example.com"   
    After you have created the key, you will notice that there are two of them, id_rsa & id_rsa.pub 
    The first one is the private key, and the second one "id_rsa.pub" is the public key. You will give GitHub the public key
    And everytime you want to connect to GitHub or push your code there with your local machine, you use your private key to show GitHub that you are the one that generated this public key. 
    It's a mathematical proof that only this private key could generate this public key

To add the public key you copy your ssh key and add it in GitHub

- Now there's one more step, (google adding ssh key to ssh-agent, and do that step)
- After that, you can push all your changes to the master branch by "git push origin main" 

Another scenario where you want to create a repository locally, and you want to push it to GitHub

- Create the folder in your local machine
- Navigate to it through your shell (Terminal)
- You create the repository in Git (you initialize a git repository)
    git init

- Create the same folder name in GitHub (through website)
- To create the connection between the two repositories (or referencing them to each other)
    git remote add origin [link from GitHub repository]

To see the remote repositories that you are connected to 
    git remote -v

- Now that these are set up, you can push whatever changes or files you have added (after committing them ^^)

## Git Branching

There's the master (now called main) branch and there's the feature branch (the non-main one). The feature branch can be a branch of the master branch from any commit. It will be as if its another project on its own and any commits you do to it will only be to it. It will not be related to the main branch until you merge it. It could be your draft, or another way of doing your project, or maybe fixing a bug, and once you are done with it, you can publish it to the main branch by merging them together.

When you make a branch from the main branch, the code from the main branch and the new branch will be exactly the same. As you go further and make changes, each branch will have their own commits and own changes. Once you are ready to merge and add the changes of the new branch to the main branch, you can merge them together.

This will list the branches 
    git branch
The branch that has a "*" beside it is the one you are connected to.

To create a new branch you use (you want to make this as descriptive as possible)
    git checkout -b feature-readme-instructions

Now if you type
    git branch
you will see that the branch you are on is *feature-readme-instructions

To switch between branches, you also use
    git checkout [branchname]
    git checkout main


## Commands

Change your username when you commit (different from GitHub username)

    git config --global user.name "Your Name"

    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

To check your username and email 

    git config --global user.name

    git config --global user.email

To check the status of your changes

    git status

Clone a repository into a new directory

    git clone [link]

Add all the changes you did

    git add .

Add a change you did

    git add [filename]

Commit the changes you did (using title only)

    git commit -m "Title"

Commit the changes you did (using title and description)

    git commit -m "Title" -m "Here is some description"

I want to push this live to a remote repository where my project is hosted (master branch)

    git push origin main

To not write all of this ^ everytime, you can do 
    git push -u origin main
and now everytime you push you can just type   
    git push

List, delete, or create branches
    git branch

