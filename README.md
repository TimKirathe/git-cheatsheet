# Welcome
### Heads Up
Code encased in angled brackets is meant to represent what you should replace in the line of code:
`git add <file-name>` should be `git add file.py` for example
## Helpful commands to get started:
* `git init` \- Initialises Git in the directory you are in. Essentially, allows you to start using git and it's functionalities
* `git clone <remote-repository-url>` \- Clones the git repository at <remote-repository-url> to your current directory
* `git -h <command>` \- Displays further help & options for a git specific command that you want to know more about. `git -h commit` shows help and all possible options for the `commit` command.

## Configuration commands:
* `git config --list` \- See the git configuration settings on your device.
* `git config --global user.name "<your-name>"` \- Sets your git username information for your entire computer.
* `git config --global user.email "<your-email>"` \- Sets your git email information for your entire computer.
* `git config --global color.ui true` \- Allows git to colorise the output to your terminal. Set it to false if you do not want colored output.
* `git config --global color.status auto` \- Allows git to determine whether to use colored outputs or not depending on whether your terminal supports it or not.
* `git config --global color.branch auto` \- Allows git to determine whether to use colored outputs or not when running the `git branch command`.

## Adding, Commiting and Pushing:
* `git add <file-name>` \- Adds your file to git tracking.
* `git add .` \- Adds every file & subdirectory in your current directory to git tracking. (Which aren't specified in your .gitignore)
* `git commit -m "<your-message>"` \- Commits are used as somewhat of a save point for your project. The message is used to describe at what point you are in the project. This will allow every file you have added to git tracking to be pushed to your remote repository.
* `git push` \- Push current branch to corresponding remote branch in your remote repository.
* `git push origin <branch-name>` \- Push branch in <branch-name> to origin. Origin is the common and defualt name for your remote repository.
* `git push --set-upstream origin <branch-name>` \- Same as `git push origin <branch-name>` but tells git to connect your local branch <branch-name> to the remote branch origin/<branch-name> in your remote repository.