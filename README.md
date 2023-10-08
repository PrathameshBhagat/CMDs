# Git Commands
`git init` => initialise a git repository in the folder  
`git clone https://` => clone a repo in new folder  
`git clone -b <branch> --single-branch https:...` => for single branch  
`git add .` => add all file(s -> .) to staging area to add to next commmit  
`git commit -m " " ` => commit/save the code with message in " "  
`git commit --amend` => adds change to previous commit, but it is now a different commit (avoid in remote repos)   
`git log` => print all current commits in current branch  
`git log --oneline`   => print all current commits in current branch in oneline   
`git log -p -u ` => prints the difference/commits from the start **(`git log --all --decorate --oneline --graph`)**   
`git status` => Check status fo staging area   
`git revert <commitID>` => revert a single commit (this works on a remote branch/repo too)  
<b><details><summary> Branch </summary>

><i> A branch is just a name associated with a commit(just for understanding)  
 A commit has a next pointer(just for understanding)  
 `HEAD` is just where  you currently are , at a particular commit or at a branch's start,  
 If at a commit ,then it is in "detached state",   If at a branch it automatically points to latest commit of the branch  
</i></details>  </b>
 
`git branch` => lists branches (if added -a also gives remote branches with local)  
`git branch [branch name] ` => creates a new branch   
`git branch -d [branch name]`  => deletes a branch   
`git branch -m [old] [new]` => Rename a branch  
`git checkout X..` => to go to a branch or commit (just moves HEAD)   
`git merge A` =>   would merge A into current/existing branch  
 <b><details><summary>Merge </summary>
 </b>
><i>If master is just: `A ` <br> and Branch1 is: `A - B` => Does not raise conflict issue as **no commit needs to be rewritten**<br>  
>If your master is: `A - C`<br> and Branch1 is: `A - B` => Merge raises a conflict issue as C needs to be rewritten  </i></details>

`git diff` => show changes between index(git add ,files only) and working directory   
`git diff --cached` => between <b><i>index</i></b> with last commit   
`git diff HEAD` =>  between the files in the working directory and the last commit  
(can add HEAD~ to change the commit described in above 2 lines)
###  Modify local commit history   
`git reset --soft <commit ID>` => brings all commits from present to <commit ID> and deletes commit history  
But keeps changes in working directory/folder and in staging area  
`git reset --mixed <commit ID>` => brings all commits from present to <commit ID> and deletes commit history  
But keeps changes in working directory/folder only (same with just <b>git reset <commit ID></b> as is default)    
> **Carefull Changes below are unchangable !!**
     
`git reset --hard <commit ID>` =>**deletes the code completely with history** and file in working directory  
`git rebase -i <commit ID>` => reorder/change message/delete/merge commits, etc to commits before <commit ID>  
`git rebase -i --root ` => same as above but rebases all commits from history  

> **_A Rebase or a commit automatically aborts if empty message or command_**
# CMD Commands 
`cls` => clear screen  
`echo hello> a.php  ` => write hello in a.php(<b>overrides the complete file</b>)  
`echo Moning >> a.php ` => ammends hello in a.php  
`type a.php` => show content in file(`del` to delete file)  
`cd .\A` => change directory "A"   
`cd ..\` => go one directory/folder back     
# Unnecessary 
Tags are same as branches ,they point to a commit ,but tags do not change.   
Two types fo tags : annotated and lightweight    
(check below lines once)
Annotated:(`git tag -a v1.0.0 -m "..." `) just have more information and need to add -a flag   (check)
Lightweight: just tags and are added as `git tag v1.0.0 -m "..." `
###### _Rebase_
or a commit automatically aborts if empty message or command_
- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740
100. First list item
       - First nested list item
         - Second nested list item
> This is a quote
>  [ghhhh](Git_Commands.md#git-commands)-
	[Markdown - Link](#Git-Commands)
