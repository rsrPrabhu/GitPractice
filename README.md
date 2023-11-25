# gitProject 

<!-- ABOUT THE PROJECT -->
## About Git Project

I created this repo to practice the git commands

## Commands List
git installation == search in GOOGLE as git scm
git --version

levels of configuration
 1.Repository/project level   (repository/.git/config)
 2.User Account(Global level)  (users/username/.gitconfig)
 3.System level (Git installation)  (user/local/etc/gitconfig)

git config --list --show-origin (details of git paths)
git config --list --show-origin --global --list
clear  == clear cmd lines
cd..   == go back from folder

ls      ===  list of content in folder
ls -a   ===  displays hidden folder too
mkdir   ===  creates folder
touch filename.filextension(index.html)  ===  create file with this name
vi filename.filextension(index.html)  ===  create and open the file with this name in cmd


git config user.name    retrieves the configured Name
git config user.email   retrieves the configured mail Id

git init
git config user.email
git config  --local user.email mailid@.com  == local term in cmd  :::  means to create in project level configuration
git config user.name (adds name)
git config  --unset user.name (removes name)

    file data ex :: user.name is key value as mentioning
         [user]
          email = prabhass575@gmail.com
        	name = Prabhakaran

git config --local --remove-section user  == removes whole section            
git help       == gives all comments provided by git commonly
git help -a    == all set of git comments ==  -a indicates all 
git help --all

git help init == gives the detail about init command
git status
git add filname (git add index.html)  ==  file is staged
git commit -m 'message'
git log  == gives the log of git folder including files


git diff  command types
working area vs staging Area ==  Git diff
staging area vs  Repository Area ==  Git diff  --staged
working area vs Repository Area ==  Git diff head

git log 
SHA1  = 12 chars hashcode

git cat-file (12 chars unique id )  -p
git cat-file 8a4ee47fc133f9a0ba6385b355d17bdf9a2db170 -p

rename file 
mv oldFilename.txt newFilename.html

git restore --staged filename.txt  (staged file would be unstaged(workspace))
git restore filename.txt  (revert the file)
git checkout -b branchname (creates branch and HEAD would be there)
git checkout branchname (move the HEAD to branchname)

git log --oneline    ******
git branch   == gives the branch list
cat .git/path gives the files inside folder

use git-school.github for practice

git branch -m new_branch  (rename the branch, so we should be inside that branch and add this command)
git branch -d branchname  (note :: come out from that del_branch and try this command )
git branch -D branchname  (for changes made in inside content)

git merge branchName
git merge --abort  (stop merging)

git rebase branchname
git merge branchname  (if we are in feature branch , and git merge feature2 , it merges feature2 with feature branch )
git log --oneline --graph


------- combine multiple commit into 1 -----------
git rebase -i  master
git rebase --interactive  master 

pick ==  pick the commit
squash == combining commits

amend  == change the content of existing commits
git show 89303393(hashcode) == provides the details of that commit
git diff --cached  === gives the differnce between two commits
git commit --amend  

CHERRY PICK
pick a particular commit use in a our work / incorporate with a branch
cons :: duplicate :: 'cos while combining the particular commit would be in multiple place 

br1 -br1commit1 -br1commit2 -br1commit3 -br1commit4 -br2cherrPickBR2commit
br2 -br2commit1 -br2cherrPickBR2commit
as u can c br2cherrPickBR2commit from br2 branch would move to br1 branch, so br2cherrPickBR2commit in both branches(duplicate)

git cherry-pick 444444-hashcode

git reset --used to remove unwanted commit from a time 
--hard == working and staging
--mixed  default  =move files to staging
--soft

git reset hash
git reset hash --hard

stash -- not commit the work , but stores in hidden place
git stash
git stash list
git stash pop  == for get back the changes  == picks the stored stash data ,and removing stash

git stash save 'stash name'
git stash apply stashID(stash@{0})  == picks the stored stash data , but not removing stash

see changes in stash
git stash show   == provides recent stashed data
git stash show -p  == show file data of recently stashed data
git stash show  stashId -p  == shows the particular stshed data by id

git stash drop   == provides recent stashed data 
git stash drop  stashId -p  == drops the particular stashed data by id

git stash clear :: clears all stashes
git stash branch branchName stashId  ==  moves this stash data to new branchname

git checkout hashID :: also possible
git checkout - :: checkouts to previous selected branch/position
git checkout Head~2 :: moves the head to 2 commits behind with hash

git checkout Head filename  / git checkout -- filename   :: head as mentioned as  --

swith does the same as checkout
git switch branchname
git switch -c newBranchName

git restore --staged filename  (staged to workspace)
git restore filename  (remove changes to original format) ,,,,,, this two actions only possible

git restore --source Head~2 filname  :: moves the file from other branch

git reset --hard commitID   :: entire commit and log will be removed  ,,, and removes the commits after that commit
git reset --hard Head~2   :: entire commit and log will be removed  ,,, and removes the commits after that commit

git revert commitId  commitMessage  :: creates a new commit with old data


::::::::::::::::::      GITHUB    ::::::::::::::::::: 

ref ::: https://git-scm.com/docs

Github alternatives ::
Git
Bitbucket
Gerrit


Git clone 
Git clone <clone url>
Git clone -b branchName <clone url>

git push needs permission

github connected with HTTPS and SSH

HTTPS 
always asks the UN/PW always for changes in repo

SSH   (vidno :: 33 for ssh setup)
No data  and we shoud configure upfront toa ddd SSH agent
check the status ssh -T git@github.com 

******* Start from scratch
  1. Create a new repo in Github
  2. clone the project to machine
  3. do some work 
  4. push (git push needs permission)

******* Create repo for existing project 
 git remote  :: is that already in remote
 git remote -v  :: provides ssh and https urls
  1. Create a new repo in Github
  2. add a remote || connect your local repo
  3. Push local project to Github


origin is defaultly taken by Git
origin is alias of url
origin in the command can be changeable

git remote add origin <url>
git remote add myGitHubUrl <url>

git remote rename <oldname>  <new Name>
git remote remove <name>

git push originName fromBranchName : toBranchName (push from one branch to another branch)

-u option
 -u == its upstream , once we initiated the upstraem , it automatically updates to branch
  ex :: step 1 :: git push -u origin branchName
        step 2 :: git push 
                it recognize the branch and pushes there

git branch -M main (master would be changed as to main)                
git branch -r   ::: provides the branch list in Github

git fetch :: fetches the data from github repo to local repo level
git pull/clone :: fetches the data from github repo to  workdirectory level

git fetch origin branchname

git pull = git fetch + git merge
 
README.md     md=MarkDown
once we added the README.md file in git repo ,git recognize and displays that in project's home page

https://pandao.github.io/editor.md/en.html

Github Gists  https://gist.github.com/
:: Gists mode cannot changeable once created :: secret/public

Github pages
https://pages.github.com/
should need a index.html in root

git merge branchname
git branch --set-upstream origin/branchname
git branch --track origin/branchname    ::: set the current branh to track the mentioned branch
                                         local name and github repo name should be same

https://github.com/leelanarasimha?tab=repositories 

git switch -c branchname     branch created
git push -c origin branchname

rm -rf branchname


git fork :: is for without add as contributors

git remote add upstream <GitURL>
git pull upstream main  :: useful for connect with forked project's pull uptodate

git tags  :: labelling for commits
            use ful version updates

  1.Lightweight tags
  2.Annotated tags

Semantic versioning

   5.6.0    
   5  major
   6  minor
   0  patch

   Patch release :: majorly on bug fixes
   Minor release :: new feature / functionality added
   major release :: total change / major functionality changes

git tag
git tag v1.0.0        Lightweight
git tag -a v1.0.0     Annotated
git diff v1.0.0 v1.0.1

git tag -l "*name*"   // contains
git checkout tag
git show tagname
git show v1.0.0

git push origin tagValue
git push origin v1.0.0
git push originname --tags     adds multiple tags

git reflogs  :: Reference Logs

git reflog show
git reflog show main
git reflog show main@{1.day.ago}
git reflog show main@{one.day.ago}
git reflog show main@{one.week.ago}

git checkout show main@{one.day.ago}
git diff main main@{one.day.ago}

get the log id ,  and reset that


:::::::::::::ALIAS::::::::::

open the config file 

[alias]
   s = status



   --allow-unrelated-histories


systeminfo in CMD provides system details
