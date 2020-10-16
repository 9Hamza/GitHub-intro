# Demo

This is a demo for a Git Tutorial.

# Step by Step Tutorial

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


# Commands

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

    git push origin master