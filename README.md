# Welcome

### Heads Up

Code encased in angled brackets is meant to represent what you should replace in the line of code. For example:
`git add <file-name>` could be `git add file.py`

## Helpful commands to get started:

- `git init` \- Initialises Git in the directory you are in. Essentially, allows you to start using git and it's functionalities
- `git clone <remote-repository-url>` \- Clones the git repository at <remote-repository-url> to your current directory
- `git remote add origin <remote-repository-url>` \- If you have run the `git init` command, this will link your local git repo to the upsteam one located at <remote-repository-url> and give it the name <origin>. <origin> acts as an 'alias' to the remote repo. Effectively, this spares you from having to use the <remote-repository-url> every time you want to run a command on the upstream repo. For example: You'd have to do `git push <remote-repository-url> <branch-name>`, instead of `git push origin <branch-name>`
- `git -h <command>` \- Displays further help & options for a git specific command that you want to know more about. `git -h commit` shows help and all possible options for the `commit` command.

## Configuration commands:

- `git config --list` \- See the git configuration settings on your device.
- `git config --global user.name "<your-name>"` \- Sets your git username information for your entire computer.
- `git config --global user.email "<your-email>"` \- Sets your git email information for your entire computer.
- `git config --global color.ui true` \- Allows git to colorise the output to your terminal. Set it to false if you do not want colored output.
- `git config --global color.status auto` \- Allows git to determine whether to use colored outputs or not depending on whether your terminal supports it or not.
- `git config --global color.branch auto` \- Allows git to determine whether to use colored outputs or not when running the `git branch command`.
- `git config --get core.excludesfile` \- View the global gitignore file on your computer.

## Adding, Commiting and Pushing:

- `git add <file-name>` \- Adds your file to git tracking.
- `git add .` \- Adds every file & subdirectory in your current directory to git tracking. (Which aren't specified in your .gitignore)
- `git commit -m "<your-message>"` \- Commits are used as somewhat of a save point for your project. The message is used to describe at what point you are in the project. This will allow every file you have added to git tracking to be pushed to your remote repository.
- `git push` \- Push all committed changes to upstream repository (on all branches where you have a committed change).
- `git push origin <branch-name>` \- Push branch in <branch-name> to remote repo. Origin is the common and defualt name for your remote repository.
- `git push --set-upstream origin <branch-name>` \- Pushes local branch <branch-name> to remote repo but tells git to set your local branch to track the remote branch origin/<branch-name> in your remote repository. So that next time you push, all you have to run is `git push`.

## Deleting files and branches:

- `git branch -d <branch-name>` \- Deletes the branch specified by <branch-name> (on your device)
- `git push origin --delete <remote-branch-name>` \- Deletes the branch specified by <branch-name> (on the remote repository)
- `git rm --cached <file-name>` \- Removes a file from being tracked by git
- `git rm --cached -r .` \- Removes files from git tracking that git has previously tracked, but you have recently added to the .gitignore
- `git reset --hard HEAD` \- Resets all file changes made on current branch to those which are in your most recent commit locally on that branch
- `git reset --hard <remote-branch-name>` \- Resets all file changes made on current branch to those which are in your most recent commit in the remote branch specified by <remote-branch-name>. Note that your remote branch names follow the naimg convention `origin/<branch-name`
- `git restore <file-name>` \- Unlike `git reset`, `git restore` will only reset the file specified by <file-name> to it's state in your most recent commit - not all files (IF you haven't used `git add <file-name>` on it).
- `git restore --staged <file-name>` \- Unlike `git reset`, `git restore --staged` will only reset the file specified by <file-name> to it's state in your most recent commit - not all files (IF you have used `git add <file-name>` on it).

## Working with branches:

- `git status` \- See all staged, and unstaged files on your local repo
- `git branch` \- Will show you all local branches you have in your repo
- `git branch -r` \- Will show you all local and remote branches in your repo. Remote branches will follow the naimg convention `origin/<branch-name>`
- `git branch <branch-name>` \- Will create a new branch specified by <branch-name> if it doesn't exist
- `git checkout <branch-name>` \- Will switch to the branch specified by <branch-name> if it exists
- `git checkout -b <branch-name>` \- Will create a new branch specified by <branch-name> and switch to the branch in one go
- `git checkout -b <branch-name> --track origin/<remote-branch-name>` \- Will create a new branch specified by <branch-name>, switch to it, and make it track the remote branch specified by <remote-branch-name> in one go. If <remote-branch-name> had work done to it already, <branch-name> will also have the latest changes and all previous commits.
- `git branch --set-upstream-to=origin/<remote-branch-name> <branch-name>` \- If <branch-name> doesn't already exist, will create it and will set <branch-name> to track the remote branch specified by `origin/<remote-branch-name>`. Unlike the command above, it will not add the changes in <remote-branch-name> to <branch-name>, you'll need to checkout to it and then do a `git pull`.

## Pushing, pulling, fetching & merging branches:

- `git push` \- Will push all commits in your branches to the upstream repo
- `git push origin <branch-name>` \- Will push only the commits in the branch specified by <branch-name> to upstream repo
- `git fetch` \- Will get all remote branches from upstream repo so that when you run `git branch -r` command, you'll see them. But, it does not merge the remote branches to your local ones
- `git fetch origin <branch-name>` \- Same as `git fetch`, but will only get the remote branch specified by <branch-name> from your upsteam repo
- `git merge <branch-name>` \- Merge the branch specified by <branch-name> into the branch you are currently in. **Note: The direction in which you merge is important. For example, if you're in main and do `git merge branch1`, it is NOT the same as doing `git merge main` whilst in branch1. Generally, you should merge into the branch you merged from. E.G. If I created branch1 by branching out of main, then I'll merge branch1 back into main when I finish my changes**
- `git merge --ours <branch-name>` \- If you know the merge will produce conflicts and are sure that the work in your current branch are the ones that you want to keep, it will keep the current branches changes instead of <branch-name>'s changes.
- `git merge --theirs <branch-name>`\- If you know the merge will produce conflicts and are sure that the work in your current branch are the ones that you want to keep, it will keep <branch-name>'s changes instead of the current branch's changes.
- `git pull` \- Git pull does a `git fetch` and `git merge` all at once. This specific way of using it will fetch all remote branch changes & merge them with any local branches that are set up to track those remote branches.
- `git pull origin <branch-name>` \- Same as `git pull`, but will only pull the changeson the branch specified by <branch-name>
