# git_cheatsheet

## My own quick reference for basic Git commands

- delete a branch :
`git branch -d`

- rename branch :
`git branch branchname log_number`

- remove something from your repo
`git rm --cached .vscode`

- rewriting the most recent commit message
`git commit --amend`

## Using Git when working with a team

Different kind of branches :
- main branch (protected)
- feature branches
- bug fixes branches

1. **To create a new branch**
`git checkout -b name-you-want-for-branch`

2. **Check every day whether there is a change on the main branch**
- switch from your branch to main `git checkout main`
- get the latest version of the remote main with
	- `git pull origin main` **OR**
	- `git pull --rebase origin main`(if merge conflict during the rebase : resolve the file's conflicts and continue on the command line git `add . && git rebase --continue`)
- switch back to the branch you are working on `git checkout your-branch-name`
- merge the changes from main to your branch `git merge main`

3. **Push your local branch to Github**
- `git add .`
- `git status`
- `git commit -m "your-commit-message"`
- `git push -u origin your-branch-name`

4. **Merge your branch to the main branch**
- From your branch :
	- Add, commit and push your local branch
	- Bring changes from main to your local branch `git pull origin main` (make sure your in *your branch*)
- Create a pull request
- If conflict :
	- `git pull origin main` (make sure your in *your branch*)
	- resolve conflict
	- Add, commit and push your local branch
- If pull request approved :
	- Go to main branch and get all the changes from the pull request : `git pull origin main` (make sure your in *the main branch*)
	- delete your branch `git branch -D your-branch-name`

5. **Other**
- to view all existing branches `git branch -a`
- to delete a branch `git branch -d branch-name`
- to check the destination of where your code is going to be pushed `git remote -v`

**Check also**
- https://jameschambers.co.uk/git-team-workflow-cheatsheet (Warning : no mention of pull request)
- https://www.youtube.com/watch?v=jhtbhSpV5YA

**Illustrated workflow - without pull request**
![alt text](https://img.jame.sc/git-workflow.gif)
