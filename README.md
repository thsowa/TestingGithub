# TestingGithub
### A personal Github exercise repository
---
* Checking if git is installed

`which git`

`git --version`

`git help ...`

* Basic git config

`git config --global user.name "..."`

`git config --global user.email "..."`

`git config --global core.editor "vim"`

`git config --global color.ui true`

`git config --global credential.helper cache`

`git config --global core.excludesfile ~/.gitignore_global`

`git config --list`

* Possible files to get to improve usability

`sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

`curl -o $HOME/.git-prompt.sh https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh`

`curl -o $HOME/.git-completion.bash https://github.com/git/git/raw/master/contrib/completion/git-completion.bash`

```
vim .bashrc --> 	if [ -f ~/.git-completion.bash ]; then
  			   		source ~/.git-completion.bash
					fi
```
* Inside a repository

`git init`

`git add .` 	**//** 	`git add <file>`

`git commit -m "Message of the Commit"`

`git commit -am "Add to staging and commit at once"`

`git status`	**//** *check working directory*

```
git log	
git log -n 2  
git log --since=yyy-mm-dd
		--until=
		--author="..."
		--grep="..."
```
---
```
Basic concepts:
	three-tree architecture: working / staging index / repository
	checkout vs commit
	SHA1 to hash changes
	HEAD pointer to the tip of the current branch in repository
```
---
* Check for differences

`git diff`		**//** *view changes in the working directory*

`git diff --staged`	**//** *view changes in the staging index*

`git diff --color-words`

* Undo changes

`git reset HEAD file` 		**//**  *to unstage things*

`git checkout -- file` 		**//**  *to discard changes on file in working directory*

`git commit --amend -m "..."` 	**//**  *change the last commit*

```
git checkout fb0987ac02 -- file.txt	// checkout previous commit to work
	git reset HEAD file.txt
	git checkout -- file.txt	// to reset the commit checkout
```

`git revert fb0987ac02`		**//**  *reverts all commit changes*

`git revert -in fb0987ac02`	**//**  *same as above, but waits in staging*

`git reset`	// **soft** / **mixed** / **hard** //

`git reset --soft fb0987ac02`	**//**  *puts a commit back in staging safest!*

`git reset --mixed fb0987ac02`	**//**  *additionally to soft, it unstages too*

`git reset --hard fb0987ac02`	**//** *reverses everything to last commit*

`git clean -n`	**//**  *tells you what is there to delete*

`git clean -f`	**//**  *permanently deletes everything in the working directory*

```
git rm file.txt
git commit -m "Deleted File"
git mv file.txt renamedFile.txt
git commit -m "Renamed File"
```

* Ignoring files

`.gitignore` **//** *specify inside the file all that you want to be ignored*

```
Example:
	# Comment
	tempfile.txt
	.DS_Store
	*.zip
	*.gz
	log/*.log
	log/*.log.[0-9]
	assets/photoshop/
	assets/videos/
	!assets/videos/tour_*.mp4
```

`git add .gitignore`

`git commit -m "Add .gitignore file"`

* Using Remotes:

`git branch`	**//**  *shows all branches*

`git remote` 	**//**  *shows all remotes*

`git remote add origin https://github.com/samborshellz/....git`

`git push -u origin master`

`git fetch`

`git merge`

`git remote rm origin`

`git clone https://github.com/.../....git`

---	
##### Work in progress...
