## Github Actions -> 
Workflow auto service by github -> repo erlated processees


# 1.CI/CD - integration and deployement -> for automating app dev and dep
CI -> integrating new code or changes auto.
CD -> publishing the new veresion once code is tested auto.
# 2.Code and Repository mgmt. -> Github

Git - tool standalone - free veresion control system- managege source code changes -> save code snapshots (commit) -> branches (alt. code veresions) -> switch between branches and commits - checkout

Github - company -> cloud git repo and serivices maanaging in the cloud -> cloud git repo storage (push and pull) - code mgmt and collabaration (issues, projects, pull requests and more) - automation and CI/CD via Github Actions

# Git / Github -> 

Git Repo -> must be created in order to see git in actions -> track all changes (contains all metadata to jump back)

- git init - create git repos -> all managed by the git (folderes and subfolders)
- Working with commits (code snapshots):
- git add <> <> <> -> add changes / called staging -> file is staged
- git commit -m "message"-> create commits
- git status -> gives status do nothing
- git log -> shows what have you done with repos -> logs all commit
- HEAD (pointer - which commit/state is currently loaded) -> main (branch to which commit belongs) -> if more than one commit we'll be using -> 
- git checkout <id> - temporarily move to another commit  
- branches -> commits belong sto different branch -> when going to earlier commit means checkout -> it is loaded o/s the branch (HEAD)
- git checkout main/master
- git revert <id> -> undo changes in that commit  -> reverted by adding new commit
- git reset --hard <id> -> undo the changes by deleting all commits since id -> must be taken care can't be reset -> re writing the history
- .gitignore file -> ignores the file we don't want to push up in the repo
- git branches -> important concept -> related to commits -> commits are organized in branches -> we have by default the **master branch** -> beranches are containers that contains commit -> to work on new feature creaate branch w/o hinder the main work and merge them once the feature is complete ->
- git branch <name> -> by default take latest commit targeted by head and builds new branch with this commit as starting point 
- git merge <name> -> to merge branches -> need to resolve the conflicts
- git branch -> list all branches
- git checkout <branchname> -> to work in given branchname
- git branch -D <branchname> -> deletes the branchname
- git checkout -b <bname> -> creates and chheckout
- git merge <bname> -> add latest commit in bname -> git resolve such basic conflicts -> brand new commit
- git locally on our computer -> so maybe it get lost if computer crashes -> data may get lost -> collab is difficult -> copy the code -> that's why github
- github (used for backup and cross-device collab purposes) -> compny gives services related to git -> and store the git repo in cloud called as github repository **gitlab** -> public/ private -> for viewing purposes
- git remote add <localreponame-id for local // origin> <url> -> adds a remote repo to local
- git push orign main -> for uploading commits 
- git remote set-url origin https://okay-cs@github.com/okay-cs/git-academind.git -> use of **Personal Access Token**
- git push --set-upstream origin master
- git pull -> for downloading commits from remote repo
- pull request ?? -> 
- wiki - uses in open src dev
- git clone <url> <repo-name> -> clone the remote repo on our local machine
- git remote -> gives the remote repos
- git remote get-url origin -> give the url of the repo 
- Making changes as different user -> 

