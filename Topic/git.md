what is git and github, how to use it

git workflow

Branching Strategies

Git Cherry-pick:

Git Rebase vs. Merge



git reset HEAD~1  			

git branch -D <BranchName>

git checkout .

git checkout master && git fetch origin && git rebase origin/master

->  git fetch origin                # Updates origin/master 

->  git rebase origin/master   # Rebases current branch onto origin/master

->git clone -b <branch> <remote_repo>   (clone a specific branch)

-> git fetch origin <branch_name>:<branch_name> && git checkout discover
