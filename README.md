# Demo

This is a demo for a Git Tutorial.

# Step by Step Tutorial

- First thing I did is create a repository in GitHub. 
- Wrote the README.md file
- Cloned this file by going to Terminal on my PC and written "git clone [link]"
[link] is a link that lets you clone the repository, it is found in the GitHub website.

- Before committing any changes, "git status" command shows you all of the files that have been updated, added, deleted but haven't been saved on a commit yet

If you create a new file, and you didn't add it to the main branch, when you do "git status", it will tell you that this created file is "untracked", which means git doesn't know about this file. To add that file, you do "git add [filename]", or "git add ." which tracks all the files that are listed (everything that needs updating basically).



- Now after you've added the changes, you can check that they're added by doing "git status" again. After that, they will need to be committed so, commit any changes writing on Terminal git commit -m "Added index.html" -m "some description"

The first -m "" is the main message or the header of the commit, and the second -m "" which is optional is the description (-m means message)