# githubguide
This is the guidance for myself to record git usage in github

Reference Link

(Chinese)https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001373962845513aefd77a99f4145f0a2c7a7ca057e7570000

(English)https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners

# Here started my record and practise

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
