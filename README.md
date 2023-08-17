#
# <mark>Git commands</mark>
## <mark>Git initialize</mark>
1. git init : Working directory where .git is been created and a new repository is created on the local

# <mark>Git remote add vs git clone</mark>
2. git remote add origin URL vs git clone URL
When i run --> git remote add command on local, i create a new branch, commit and push my changes to the remote, here i can't push my files to the default branch available on the remote repository

Whereas when i run --> git clone i take a copy of the remote repo and work on it and push the changes to a new branch or the default branch.

# <mark>List the untracked files, add and commit STAGING AREA</mark>
3. git status
4. git add . or git add filename or ADDING MULTIPLE FILES USING A SPACE git add filename1 filename2
5. git commit -m "First commit"

# <mark>Displays the commit history</mark>
6. git log 
7. git log --oneline

# <mark>Amend</mark>
After you do the first commit and forgot to add any other file, you can simply add the file "git add filename" 

8. git commit --amend --no-edit or git commit --amend -m "updated commit"
Check your commit history "git log" 

It allows you to make changes to the most recent commit in repository without creating additional commits

# <mark>Push from local to github repo</mark>
9. git push origin nameofthebranch  - This will push the changes and the code to the remote repo

# <mark>Troubleshoot non-fast-forward error</mark>
When you try to push the changes from local repository and the commits/history made are unrelated to the remote repository it will throw an error : non-fast-forward or with different terms. So, try running this command where the latest changes will be downloaded from remote repo and merge it to the local repo.

10. git pull --rebase origin nameofthebranch
11. git push origin nameofthebranch

# <mark>Git fetch vs git pull</mark>
If we want to download the latest code changes from remote to the local repository we run the command "fetch" and we can review the fetched data using git log and then "merge" it to the local repo

12. git fetch origin nameofthebranch
13. git merge master
14. git pull origin nameofthebranch

git pull = git fetch + git merge
It automatically merges into the local repository without allowing us to review it and need not run merge command separately.

# <mark>Create branches and switch between them</mark>
15. git branch newbranchname
16. git switch feature or git checkout feature

# <mark>Merge vs --squash merge vs rebase</mark>
17. git merge

When you normally run git merge it gives you the file changes and the commit history. Merges from source branch to the target branch

18. git merge --squash

Here you get only the file changes where it squeezes all the commits into one

19. git rebase

Git rebase is a way of moving the changes from one branch onto another branch.

# <mark>Cherrypick</mark>
20. git cherrpick commitid 

If suppose there are 50 commits and want to commit 12 you can run $git log and copy the commitid and only that feature upgrade is merged to your masterline

# <mark>Stash</mark>
21. git stash

Example: your working on the feature branch and your teammate asks to check the code in main branch, you don't want to commit your work unnecessarily so run "stash" command once again switch back to your feature branch run

22. git stash pop : you can continue your changes and once done can commit it

23. git stash list

# <mark>Remove your local .git</mark>
24. rm -rf .git

# <mark>Git reset vs git revert</mark>
25. git reset --hard HEAD~1
26. git revert commitid

Example: i have created file1.txt and file2.txt
|file1.txt|file2.txt|
|---------|---------|
|version1 :Ferrari|version1 :BMW|

Now i commit it : git commit -m "Ferrari version1 file1"

git commit -m "BMW version1 file2"

Again i make changes by adding new data
|file1.txt|file2.txt|
|---------|---------|
|version1 :Ferrari|version1 :BMW|
|version2 :Ferrari|version2 :BMW|

git commit -m "Ferrari version2 file1"

git commit -m "BMW version2 file2"

git log --oneline

outputs:

commitid 1 (HEAD->master)BMW version2 file2

commitid 2 Ferrari version2 file1

commitid 3 BMW version1 file2

commitid 4 Ferrari version1 file1"


Now, if i want to rollback my changes and remove newly added version2 to version1 in file2

git reset --hard HEAD~1

git log --oneline

Outputs:

commitid 1 (HEAD->master)Ferrari version2 file1

commitid 2 BMW version1 file2

commitid 3 Ferrari version1 file1

recent commit is rollbacked and if want to rollback to the commitid 3 then HEAD~3

Open your file2 and check only version1 is available after rollback
|file2.txt|
|---------|
|version1 :BMW|

IF you want to update the version2 again copy the commitid of BMW version2 file2 : 

git reset --hard paste the commitid of BMW version2 file2

NOTE: git reset can be done only locally and git revert can be done even after pusing to the remote repo

Follow the same process for revert and try it.
git revert commitid
git log
new commit is created and does not affect or delete the reverted commit history

This is explained in detail because in realtime projects we do update the versions and rollback it.

# <mark>Git fork</mark>
This can be done on the github account and not on the git bash where we fork the repository and can work on it and if we want to merge our changes can create a pull request and the code is validated then you can merge your changes to the target repository. This is done when we don't have the repo credentials.

# <mark>Merge Conflicts</mark>
when there is a file abc.txt and two developers use the same file for upgrading or making changes and try to push their files there occurs the conflict which is to be considered as the latest merge so there occurs a human intervention between the developers and merge the updated file.

!!! Hope you enjoyed learning !!!


![Thumbsup](https://github.com/NithiyaJoseph/GIT/blob/main/Thumbsup.jpg)
