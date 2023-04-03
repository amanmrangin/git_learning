# Git Learning

## **Installation**
- Install [Git Client](https://git-scm.com/download/win), launch 'Git Bash' tool, and run

  `git --version`

- Install Git Tools such as _GitKraken_, _SourceTree_ or [_GitHubDeskTop_](https://desktop.github.com/)
    - Create a free account at [GitHub](www.github.com) to create and manage your personal repositories

## **Settings**
After git client is installed, run the following commands to the settings which will get added to _<user-home>/.gitconfig_

    git config color.ui true
    git config format.pretty oneline
    git config --list --show-origin
    git config --global user.name "Your Name"
    git config --global user.email "Your Account ID"

## Notes
By Default, a developer works on a directory AKA Working Directory or Working Tree. e.g.: **_git_learning_**
![img_1.png](img_1.png)
![img_3.png](img_3.png)
Note that **.git** directory is created under 'git_learning' WorkingTree,
## Initialize/Create/Add/Remove Commands
***
To **create (initiate) a new Git Repository** in Local machine: It will create '.git' directory under WorkingTree/Directory

`git init`

![img_2.png](img_2.png)

To **Uninitialize (remove) a Git Repo** in Local machine, navigate to repo directory (e.g. cd /...../.../workindir/)
   
 `rm -rf .git`

To **download/clone an existing remote Git Repo** 
    
`git clone <remote URL>`

 e.g.: `git clone  https://github.com/<accoutname>/<reponame>.git>`

To **Add a change in the WorkingTree(Working Directory) to Git's Stage(Index)**

`git add <filename>` 

To **Remove a file from Stage(Index)**

`git reset .` OR `git rm --cached <filename>` OR `git rm -r --cached <filename>` OR  `git restore --staged <filename>`

To **Stage all (added, modified, deleted) files from the current WorkingTree**

`git add -A` (git add --all)

## Commit commands
***

To **Commit all the Staged files in Local Repo**

`git commit -m "Commit Message Here"`

To **Commit all modified files

To **Stage all (added, modified and deleted) files and commit**

`git add -A && git commit -m "Commit Message here"`

## Push commands (To push all changes to from local repo to Remote repo)
***
To **Push the committed files from Local Repo to Remote Rep**

`git push`

To **Modify the comment of last commit and push into remote repo**

<span style="color:red"><strong>Extra Careful:</strong></span>  Assuming no local changes existing,  run the following commands

 - Pull all the changes from Remote to local
 `git pull`
 - Modify the comment of last commit
 `git commit --amend -m "New Commit Message Here"`
 - Push the change Forcefully to remote branch
 `git push --force origin <remote branch name>`

## Undo/Restore/Revert
***
To **Undo most recent commit**

`git reset HEAD~1`

To **Revert to specific commit**

`git revert <SHACODE>`

To **Hard Reset the local branch to look like Remote branch**

`git fetch origin && git reset --hard origin/<remote-branch-name> && git pull && git status -sb` 

OR  

`git clean -d -i -f && git reset --hard origin/<remote-branch-name>`


To **Remove all the local changes and reset to local Head**

`git reset --hard HEAD`

## Squash and Merge (Multiple Commits of one branch as one large commit into another branch)
***
To **Merge the code (multiple commits and multiple files) from 'feature_1' branch into 'release_X' branch**

**Assumptions**: No other developer is working on these 2 branches while you are merging in your local machine
- **Prepare in Local machine**
    1. Verify that 'feature_1' branch in local machine does NOT have any changes
    2. Pull all the changes from remote 'feature_1' branch to local machine: `git checkout feature_1 && git pull && git status -sb`
    3. Switch your local workspace to target (relase_X) branch:   `git checkout release_X && git pull && git status -sb`

- **Merge in Local machine**
    1. ake all commits from 'feature_1' branch, squash them as one single commit and merge them into 'release_X' branch `git merge --squash feature_1`
    2. Resolve all the merge conflicts in local machine if there are any
- **Commit in Local Machine** 
    1. Commit the changes to 'release_X': `git commit`
- **Push changes from Local to Remote**
    1.  `git push`
- **Verify** the commit history on the remote 'release_X' branch



## Additional Materials
- [Git for beginners: The definitive practical guide](https://stackoverflow.com/q/315911/12860895)
- [Resources to learn Git](https://try.github.io/)
- [Learn Git Branching](https://learngitbranching.js.org/)
- [Explain Git With D3](https://onlywei.github.io/explain-git-with-d3)
