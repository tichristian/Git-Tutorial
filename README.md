This is a tutorial about learning git.

Create a source file for you project, in my case, I created a virtual
environment for my project

$ virtualenv venv -p python3.6

{since in a virtual env, after activating}

----------------- Local environment -------------------

1) 
created a git repository first

() $ git init

This is a local repository


2) 
check files

() $ git branch

shows all files that we are working with

3)
create a test file

() $ nano test.txt

4)

show which files that has not been stage or committed

() $ git status

commit this file

first add to stage

() $ git add test.txt

() $ git rm --cached {filePath} //to unstage

note: you can add a directory, and it will add all the fils in that directory
      in your stage

then commit

(venv) $ git commit -m 'message for this commit'

4.1)
git may ask for who you are, just answer the questions

() $ git config user.email 'your@email.com'

() $ git config user.name 'your name'

4.2)
to add files and folders to ignore, in the directory of your git repository (same directory as where the .git is), create a local .gitignore file

() $ touch .gitignore

nano into that file, and enter the names of files and dirs you want to ignore
example:

'# Ignore these directories'

directory_name/

'# Ignore these files'

filename

'*.file extention (for multiple files)'

5)
Create a new branch

() $ git checkout -b {branch name}

make sure to commit  changes in a branch before changing
or it will show on both as something that you are working on for that
branch.

6)
push to Github

() $ git remote add origin https://github.com/tichristian/{repository-name.git}

() $ git push -u origin master

then paste the other branch

() $ git push -u origin {branch name}

Then use github.com (or other git of your choice) to control, 
to do merging and stuff

7)
Now to make sure you local match git,
do a pull

() $ git pull origin master

8)
If you want to do merges locally

() $ git checkout {master/any really}

() $ git merge {branch that is going into other branch}

if you conflict, you have to resolve manually,
or use

() $ git mergetool

9)
to see branches as a tree

() $ git log --graph --all --format='%C(cyan dim) %p %Cred %h %C(white dim) %s %Cgreen(%cr)%C(cyan dim) <%an>%C(bold yellow)%d%Creset'

10)
to see difference in file

() $ git diff {path to file}

11)
to remove a branch

local branch

() $ git branch -d the_local_branch

remote branch

() $ git push origin --delete the_remote_branch

12)
to clone a git to work with. Do this when you want to work with branches from a remote repository.

() $ git clone {path of remote git}

it will only show master, to see all other branches (remotes are hidden)

() $ git branch -a

If you want to make a local branch that will track a remote branch, 

() $ git branch -t my_local_branch origin/remote_branch
() $ git checkout my_local_branch

Do your work, and then simply push it directly to remote branch. That way all merge can be done in repository.

() $ git push
