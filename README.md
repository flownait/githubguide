# githubguide
This is the guidance for myself to record git usage in github

Reference Link

(Chinese)https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001373962845513aefd77a99f4145f0a2c7a7ca057e7570000

(English)https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners

# Here started my record and practise
----------------------------------------------------
I. Create Git Repository in local (MacOS)
1.Create a Git Folder and initialize as git folder
```terminal
mkdir 5.1.DailyTasks
cd 5.1.DailyTasks

# initialize folder as git folder
git init

# add file into git repository
git add readme.txt
git commit -m "add readme file"

# check for file status, whenever new files put in but not add into repo, it will show the messages
git status
```

2.Modify and recommit into git
```terminal
# whatever file changed, just use similar scripts
git add readme.txt
git commit -m "modify readme file"

# check again to see the difference
git status

# if don't want the change and need to revert back
git checkout -- readme.txt

# delete file and commit into git
git rm test.txt
git commit -m "delete test files"
```

3.Version Rollback and Reset
```terminal
# check historical changes
git log
git log --pretty=oneline

# rollback to last version use HEAD^, last 2nd HEAD^^, last 100 HEAD~100
git reset --hard HEAD^

# check log again, last log disappeared...
git log --pretty=oneline

# rollback use logid (starting id based on log...), this can fast locate to any version, including log "disappeared" version...
git reset --hard 8b9bc

# or maybe forget the logid...then just use reflog to show the historical edit
git reflog
```

II.Upload into GitHub
1. Create SSH key...
https://help.github.com/enterprise/2.14/user/articles/checking-for-existing-ssh-keys/
https://help.github.com/enterprise/2.14/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/

2. Add SSH key into GitHub
```terminal
# view the public ssh key and copy, paste into github
cat /Users/myname../.ssh/id_rsa.pub
```
3. Create GitHub project and remote link with local folder and it will display below scripts for usage
# …or create a new repository on the command line
```terminal
echo "# ...projectname" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github...com:...accountname/...projectname.git
git push -u origin master
```
# …or push an existing repository from the command line
```terminal
git remote add origin git@github...com:...accountname/...projectname.git
git push -u origin master
```
key messages here
```terminal
# link with github project
git remote add origin git@github...com:...accountname/...projectname.git

# push the code and update, -u for the first time to push all branches, without -u for later any update push
git push -u origin master
git push origin master

# push branch
git push origin branchname

# copy one github project into local
git clone git@github...com:...accountname/...projectname.git

# pull recent update/files to local
git pull origin master
```

III. Create & Manage Branches (MacOS)
1.Create a Branch
```terminal
git checkout -b branchname

# Check branch status
git branch

# Change to Master Branch
git checkout master

# Merge branch into Master
git merge branchname

# Delete branch
git branch -d branchname
```

2.Connect with Github
```terminal
# Push Branch into Github
git push origin branchname

# Delete Branch from Github
# Reference link https://stackoverflow.com/questions/6127328/how-can-i-delete-all-git-branches-which-have-been-merged
git push --delete origin branchname
```
