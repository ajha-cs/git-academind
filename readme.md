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
- git remote set-url origin urlhere
- Making changes as different user -> 
- git push origin feat-color -> error (we don't have permission) ->  How to make our local changes appears on the repo we don't create nor we own ?? 
- -> Github Issues and Collaboration ->
- 1. Reach out to the creator -> by creating issues (not a good method) -> in issues section using ''' wrappers -> add a stranger as collaborators
- Also Branch Protection Rules to protect our main branch -> require pull request before merging
- Pull request -> a request to owners or colleagues to pull our changes in main branch -> whoever had a write access can revview this changes
- 2. Understanding Forks -> we don't trust anyone reaching out to us -> no collaborators
- In such a case **fork** a repo -> cloning a repo on github -> that repo is mine -> then create a pull request once changed
- **compare across forks options** -> to see changes
- Resolving conflicts
- git stash -> suppose working on new feature in master branch -> go back to latest commit ?? - we don't want to create new commit -> stash - internal memory where we can save uncommitted unstaged changes
- git stash -> to save uncommited unstaged changes
- git stash apply -> apply the latest data - stages
- git stash list -> list different stages
- Once you git stash / access the stash data -> either commit the changes or undo changes -> commit -> change smthng -> stash or stast again -> then git stash apply 
- Add msg to stash 
- git stash push -m "msg" -> add msg to the stash
- git stash pop 0 -> apply the stage - 0 and remove from stash 
- git stash drop 0 -> remove the stage 0
- git stash clear -> remove all stages
- Can we bring back the deleted commits/snapshots ?? 
- Can we bring back the deleted commits/snapshots ?? 
- git reflog -> shows all commmits for last 30 days also helps if we deleted branches tho
- git reset --hard HEAD~1 -> remove the commit 1 behind HEAD
- git reset --hard commit_id/ from git reflog -> to add back the commit
- git restore
- To get deleted branch back -> 
- git checkout reflogid
- git switch -c abc
- Combining master and feature branches ->     
- Merge types -> 
1. fast-fwd merge ->  if we have no additional commits in master only commits in feature branch -> merge moves HEAD fwd to f2 commit and doesn't create new commit -> no new merge commit -> 
- git merge --squash <bname> -> put all commit together in the end 
2. non fast fwd merge (recursive/octopus/ours/subtree) -> **recursive merge** -> 
- git merge --no-ff <bname> -> no ff merge -> creates a new merged commit 
- recursive merge -> if we have commits in both feature and master branch after feature branch cerated -> and additional merge commit created in master branch
- git rebase -> Rebase Alternative -> we can add f1,f2 to the updated master branch after m3 -> result in ffm -> rebase means rebase the master in feature branch -> changes in feature branch based on m3 -> f1 -> f2
1. rebase master to feature branch
2. mereg rebased feature into master
rebase -> make new commits not move them their hashtags will be different -> may creates havoc history
## REBASE - DEPENDS ON PROJECTS -> CAREFUL WHEN COMMITS O/S OF YOUR REPOSITORY
- git rebase <bname> -> when to apply -> new commits while working in feature branch -> feature relies on additional commits in master branch -> rebase massater into feature branch **OR** feature is finished and implementation **without the merge commit**
## REBASING REWRITES THE HISTORY
## What if we have conflicts during the merge ?? -> 
- once conflict -> working on two file aat a same time
- git status -> give more information about the conflict 
- git log --merge -> show commits we wanna merge
- git diff -> shows differences 
- Merge (**noff create merge commit -> new commit** or **ff - just moving head no new commit**) vs Rebase (change single commit's parent -> new commit ids) vs Cherry-Pick (Add specific commit to branch (HEAD) - copies commit with new id)
- git cheery-pick <id> -> merging only the particular specific commits -> but duplicate commits
- git tags -> to tag important milestones/ important stages -> lightweight tags (pointer to the commits in the branch) vs annonated tags (full object in git who added this tag - email)
- git tag tag_name <id>
- git tag -d 1.0 -> remove lw tag
- git checkout tag_name
- git show -> show the content / object in git
- git tag -a <ver> -m "Latest Version"
- git tag -d 2.0
- git push -u origin feature-upstream -> u - means upstreams
- git branch -a ?? remote tracking branch (RTB) -> local **read only** copy of RB
- git branch -r -> show remote tracking branches
- git ls-remote -> makes n/w connection and get the details of remote branch
- LB - RTB - RB
- [LTB - RTB] - RB
## ALWAYS RTB gets updated first before making changes
- git pull origin master -> git fetch (update RTB from RMB) + git merge (merge RTB chanegs to LMB)
- git fetch origin -> (RMB changes to RTB - red one)
- To get this RTB updates -> we could checkout RTB and then create a new branch to have these changes
# Efficient Way
- LTB (Local Tracking Branch) ?? -> Local refernce to RTB - can be edited (git push, git pull available)
- Creating LTB 
- git branch --track <LTB_name -  same name as RB> origin/feature-remote ->  add a LTB to track changes of RB -> feature-remote
[LTB -> git push -> RTB]
- git branch -vv -> shows more information about the branch
- git remote -> show current remote servers
- git remote show origin -> more information about current env we working on
- git push -u origin feature-upstream -> now this branch is LTB for tracking remote branch (feature-upstream)
- Can we delete RTB -> 
- git branch --delete --remote origin/feature
- Can we delete RB -> On deletion of RB its RTB also deleted
- git push origin --delete feature
- git push --force origin master

## GITHUB ACTIONS

- Repos -> Workflows -> Jobs -> Steps
- Repo could have as many workflows
- Workflows -  contains one or more jobs Trigerred upon **events**
- Jobs - contains one or more steps -> define a runner (execution environment) -> Jobs can run **parallel** or **sequential** -> can be **conditional**
- Steps -> execute **shell script** or **actions** -> executed **inorder** -> ans also **conditionally**
- yml file -> .github/workflows
- events -> 
- **on**: workflow_dispatch -> manually trigger wf
- **jobs**:
- job_name (build): needs a env.
- **runs-on**: environment where steps gonna run
- **steps**: 
- - **name**: name of the step
- **run** -> run shell command
- Workflow Triggers (events) ->
- Repo Related -> 
- push -> branches: main, abc 
- pull_request -> types: [opened, closed], create, fork, issues, issue_comment, watch, discussion and many more
- other -> 
- repository_dispatch -> REST API request trigger wf
- schedule 
- workflow_call
- Workflow don;'t run in our repo -> it runs on server
- Actions -> custom or third party app that performs common and repeated tasks
- "run" -> to run shell command
- Marketplace for the GHA
- To use **actions** -> 
- actions/checkout -> 
- **uses**: actions/checkout@v3
- **with**: take keys that configure the action -> key-value pair
- To run jobs one after another -> 
- **needs**: job_name
- Using Multiple Triggers (events) ->
- **on**: [push, workflow_dispatch]
- Expressions and Github Contexts -> we might needs some metadata -> collection of metadata are called **contexts** -> 
- To use contexts -> "${{ toJSON(github) }}" -> gives information about repo or keys or other information
- ${{ <context> }}

## Events

- Filtered Events ??
- Available events -> **workflow_call**, **repository_dispatch**, **schedule**
- On deploy acition if code pushed to master branch -> 
- **Activity Types** -> more control on events - which variation will triggered the wf -> for eg: pull_request -> based on issues is closed or opened or labeled or edited -> default - opened, synchronised, reopened
- **Filters** -> for eg: push -> based on target branches, tags, branches-ignore, tags-ignore, paths, paths-ignore
- ## By default, pr based on forks do not trigger a wf -> bcoz anyone can fork the repo -> might spam your wf

- Cancelling (get cancelled if job fails (can be changed) or stesp failed (can be changed) or can be cancelled manually) & Skipping WF (skip a wf run - push can trigger a wf but we could add exceptions for pull_request and push - on adding msg in commit like -> 
- **[skip ci] [ci skip] [skip actions] [actions skip]**)

## Job Data & Outputs - Artifacts

# Job Artifacts -> like logs, binary files we wanna share or analyze
- Job (build app) -> produces op assets (app binary websites files) -> so user can download manually (via UI or API) or use them in other jobs (via actions)

# Downloading artifacts automatically -> 
- Since jobs running on different machines so won't accessibledirectly must be **downloaded**
- downloads the artifacts and **unzips** them

# Job Outputs -> simple values that can be used in another jobs
- Add new key at top of jobs definition before **steps**
- **outputs**: 
- **script-file**: ${{ steps.publlish.outputs.smthng }} key
- jobs can pick up and share outputs via **steps** context -> 
2 ways
- "script-file" -> name of output used across the jobs
- "smthng" -> name of output used within the job
- 'smthng={}' >> $GITHUB_OUTPUT 
- '::set-output name=smthng::{}' 
- '>> $GITHUB_OUTPUT' -> target special file created by github in the env where job runs where output key-value pair written to
- To access in another jobs -> use **needs** context
- echo "${{ needs.build.outputs.**script-file** }}"

# Dependency Caching -> 
- wf takes some time - like 3 min -> but some time get a code is repetitive task - but it is fast
- but installing a deps is longest -> if we could able to store it website deploys faster
- **must be before the target**
- **also rerun once the job is finished**
- must give cache a key - for retrieving a cache in future or also indicates whether the cache should be discarded when deps changed -> make it dynamic -> **hashFiles()**
- **/package-lock.json means - more / infront is allowed -> ./folder/folder/package-lock.json
- **central caching** is used

## Environment Variables & Secrets
- Certain variable that are dynamic -> foreg: pwd might changes as per env (testing/production)
- so how to provide these env variables
- **env**: use of env keyword 
- can be set on workflow lvl and can be accessed by each jobs in wf until and unless not overwrite by other jobs
- can be set on job lvl
- Now these env variable can be used across the code files
- **some env variable can also used in wf file** -> 
- run: **$PORT** might depends on shell
- or we could use expression syntax -> use env context - contains environment variable steps-specific or job-specific it depends
- ${{ env.MONGODB_USERNAME }}

## Understanding and using Secrets
- Don't wanna put credentials to the workflow file
- **Secrets** -> gha allow you to store secrets -> using github 
- Can be stored at organisation lvl (organ. acc.)
- Can be stored on repo lvl (repo settings -> secrets -> action specific -> value available to all wf executed for this repo) -> can't be viewed only updated
- can be accessed using **secrets** context object
- github knows these are secrets won't log them out

## Utilising Environment Secrets ->
- github Env. -> attached to repo -> wf can reference these env. -> extra config/secret for jobs in that env -> special protection rules -> diffrent secret for different jobs -> eennv. specific secrets
- **environment** key is used to make it job specific

## Controlling Execution Flow

- Running jobs and steps conditionally, using mtx, reusabillity
- **if** (jobs/steps): ${{dynamic_expression}} -> 
- steps.<id>.conclusion -> after **continue-on-error** evaluated or 
- steps.<id>.outcome -> before **continue-on-error** evaluated == 'failure' -> to change the deafult behavivor add failure()
- **continue-on-error** (steps) -> true or false
- failure() -> returns true if prev steps or jobs failed
- success() -> returns true if no prev steps failed
- always() -> causes steps to execute even when cancelled
- cancelled() -> returns true if wf is cancelled

## Matrix Jobs

- running the same job with different config at the same time
- Runs in parallel by default
- **strategy**: 
-   **matrix**: 
-       node-version: [12,14,16]
- **include** key -> to have standalone config ->  add a list with dashes -> node-version: 18, operating-system: ubuntu-latest
- **exclude** key -> to exclude value -> node-version: 12, operating-system: windows-latest

## Reusable Workflows

- **on**: workflow_call -> wf whose gonna used this can apply -> 
- **uses**: full_path

# Adding inputs to reusable wf ->
- **inputs**:
-   **input_name//anything**:
-       **description, required, default, type keys**
- using inputs context -> ${{ inputs.input_name }}
- can be used **with** then **input_name**

# Also secrets
- **secrets**:
-   **secret_name**:
-       **description, required, default, type keys**
- can be used **secrets** then ${{ secrets.some-secret }}

# Also Outputs
- **outputs**:
-    **output_name**:
-       **description**:
-       **value**: ${{ jobs.deploy.outputs.outcome }}

