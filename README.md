# Git & GitHub Tutorial

This is my learning documentation for a Git Tutorial.
Learned from [VideoLink](https://www.youtube.com/watch?v=RGOj5yH7evk&t=1825s&ab_channel=freeCodeCamp.org)

## Step by Step Tutorial

- First thing I did is create a repository in GitHub. 
- Wrote on the README.md file
- Cloned this file by going to Terminal on my PC and written `"git clone [link]"`
[link] is a link that lets you clone the repository, it is found in the GitHub website.

- Before committing any changes, "git status" command shows you all of the files that have been updated, added, deleted but haven't been saved on a commit yet

If you create a new file, and you didn't add it to the main branch, when you do `git status`, it will tell you that this created file is "untracked", which means git doesn't know about this file. To add that file, you do `git add [filename]`, or `git add .` which tracks all the files that are listed (everything that needs updating basically).

- Now after you've added the changes, you can check that they're added by doing "git status" again. After that, they will need to be committed so, commit any changes writing on Terminal `git commit -m "Added index.html" -m "some description"`

The first -m "" is the main message or the header of the commit, and the second -m "" which is optional is the description (-m means message)

- So far, all of what we did is save our code or changes locally (on my pc only). The changes are not live on GitHub. 
- To make them live, we do "git push". BUT in order to push the changes, you have to prove to GitHub that you are the owner of that account. So we have to connect our local machine to GitHub somehow. The way this is done is by using SSH keys.

    We first generate an SSH key by `ssh-keygen -t rsa -b 4096 -C "email@example.com"`  
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

To push changes from your new branch to GitHub (we are setting the new upstream to the new branch, so whenever you <git push> you are pushing to the new branch)
    git push -u origin [branchname]
    git push -u origin feature-readme-instructions

What is a Pull Request? (also Called PR)
- it is a request to have your code pulled into another branch. For example, pulling code from my new branch to the main branch
- once the PR is done, anyone can review it, and ask us to make changes or updates.
- once you make the PR, you can still make changes by comitting to that same branch that did the PR. But generally, once the PR is merged, you will delete your branch or feature. Then when you want to make additional changes, you will create a new branch, and start the same procedure over again. (new branch, do changes, commit, new PR, etc...)

Usually the PR request should say the changes you have made and why you did them (in a list format)

In the GitHub interface: 
- you can see everything about the Pull Request including commits, comments, and more.
- you can comment specifically on any code and see any comments from other people

After the you merge the main branch with the feature branch, you should see the changes of the feature branch applied to the main branch.

Now to get the most recent changes that you did to your main branch which is not updated locally (on your local machine), you will do
    git pull
    git pull origin master

After you are done from the branch, you will probably delete it (because you don't usually reuse merged branches),so to do that you would type
    git branch -d feature-readme-instructions

## Forking

Forking is creating a copy of someone's repository to your GitHub account.
- You can contribute to someone's project. Take the original project, add some code, and then create a pull request to merge that code to the original project.

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

To update your files that were committed or had some changes on GitHub on your local machine, you do
    
    git pull origin master
    git pull

To delete a branch 
    
    git branch -d [branchname]
    git branch -d feature-readme-instructions

Shortcut for adding (adding changes) and commiting modified files [includes the add command in the commit command, and this only works for modified files ]
    
    git commit -am "Message"

To merge with main branch
    
    git merge main

To see the difference between the branch you are in and another branch
    
    git diff [otherbranchname]

Sometimes you want to undo a change that you added (these both have same meaning)
    
    git reset
    git reset README.md

If you want to undo a commit that you just made
    
    git reset HEAD~1

To see all the commits that you did
    
    git log

To delete one of the commits that you made, you first want to look at its hash number from "git log" and then do
    
    git reset [hashnumber]
    
(This will unstage the commit, which means the commit will no longer be in git, but all the changes wont go away, we are just removing the commit)

To remove all changes of a commit
    
    git reset --hard [hashnumber]
