# git
Git Guide

NOTE::  Remove tild files from project before commit

>find . -type f -name '*~' -exec rm -f '{}' \;

DONT WANT TO REMOVE THEN: Just add *~ to .gitignore at the root of you repo.

LINK:: https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config


INSTALLATION
=========================================================================================
>sudo apt-get install git

//To check git is installed on your PC type following command

>git --version


STEPS FOR PUSH TO GIT
=========================================================================================

> git clone https://github.com/nitin-vaghani/git.git /var/www/html/git/

> git checkout developer

> chmod -R 0777 ./*

> nano .gitignore  //goto .gitignore section

> git config --global user.name "User name"

> git config --global user.email "youremailhere"

> git config --global push.default matching

> git config merge.conflictstyle diff3

> git config merge.pin.driver true

> git add folder/					// if you want to add only folder

> git add file.php				// if you want to add only file

> git add --all :/				//if you want to add all files

> git reset HEAD *.scss 	//escape scss file to being upload to git.

> git commit -am "Fresh Copy"

> git checkout developer

> git push origin developer


.gitignore
=========================================================================================
*~

/.project

cgi-bin/

upload/

.sass-cache/


NOTES
==================================================================
If you have changed any files in (IE. admin folder) then you have to add those files to git again by following command:
git add admin/


Get pull from server
====================================================================
>git pull origin developer

Error Handling
====================================================================
In case you get error something like this :

--fatal: The remote end hung up unexpectedly

fatal: early EOF

fatal: index-pack failed

> git config --global core.compression 0

clone again.

> git config --global core.compression -1

STEPS FOR PUSH EXISTING PROJECT TO GIT
=========================================================================================

URL: https://help.github.com/en/articles/adding-an-existing-project-to-github-using-the-command-line

1. Create a new repository on GitHub. To avoid errors, do not initialize the new repository with README, license, or gitignore files. You can add these files after your project has been pushed to GitHub.
Create New Repository drop-down

2. Open Terminal.

3. Change the current working directory to your local project.

4. Initialize the local directory as a Git repository.

>git init

5. Add the files in your new local repository. This stages them for the first commit. To unstage a file, use 'git reset HEAD YOUR-FILE'.

>git add .

7. Commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use 'git reset --soft HEAD~1' and commit and add the file again.

>git commit -m "First commit"

8. At the top of your GitHub repository's Quick Setup page, click to copy the remote repository URL.
Copy remote repository URL field In Terminal, add the URL for the remote repository where your local repository will be pushed.
Sets the new remote EX. git remote add origin http://github.com/web-group/xyz.git

>git remote add origin remote "repository URL"

9. Verifies the new remote URL
>git remote -v

10. Push the changes in your local repository to GitHub remote server.

>git push origin master

For check difference between your LOCAL branch & Remote branch
=========================================================================================

Fetch remote data using below command locally
>git fetch

Now hit below command for get all branch list
>git branch -a

>feature/front-end : This is your local branch
>remotes/origin/feature/front-end : This is remove branch

Now, latest changes of remote branch is in your local..Use below command to check difference
>git diff feature/front-end remotes/origin/feature/front-end

#ThankYou!!
