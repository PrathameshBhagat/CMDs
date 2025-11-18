# Git Commands
`git init` => Initialise a git repository in the folder  
`git clone https://` => Clone a repo in new folder  
`git clone -b <branch> --single-branch https:...` => For single branch   
`git clone --depth <no-of-commits> --branch <branch> <repo-url>` => For cloning only some last commits from a single branch  
`git add .` => Add all file(s -> .) to staging area to add to next commit  
`git commit -m " " ` => Commit/save the code with a message in " "  
`git commit --amend` => Adds change to the previous commit, but it is now a different commit (avoid in remote repos)   
### Log
`git log` => Prints all current commits in the current branch  
`git log --oneline`   => Prints all current commits in the current branch in oneline  
`git log --follow -- [file name]` => Prints all commits that modified a file  
`git log -p -u ` => Prints  the difference/commits from the start **(`git log --all --decorate --oneline --graph`)**   
`git status` => Check the status of the staging area   
`git revert <commitID>` => Revert a single commit (this works on a remote branch/repo too)  

### Branch
<details><Summary><b>Explain branch</b></Summary>  
<b> A branch is just a name associated with a commit(just for understanding) <br>  
A commit has a next pointer(just for understanding)<br>  
`HEAD` is just where  you currently are, at a particular commit or at a branch's start,<br>  
If at a commit, then it is in a "detached state",   If at a branch it automatically points to the latest commit of the branch</b></details>  

`git branch` => Lists branches (if added -a also gives remote branches with local)  
`git branch [branch name] ` => Creates a new branch   
`git branch -d [branch name]`  => Deletes a local branch   
`git push [remote name] --delete [branch name]` => Deletes a remote branch  
`git branch --remote --delete [remotename]/[branch name]` => Deletes a remote tracking branch  
(visible on `git branch --all`, as remotes/[origin..]/..)  
`git branch -m [old] [new]` => Renames a branch  
`git checkout X..` => To go to a branch or commit (just moves HEAD)   
`git merge A` =>   Would merge A into the current/existing branch  

<details><Summary><b>Git Merge</b></Summary> 
  
If master is just: `A` <br> and feature is: `A - B` => Does not raise conflict issue as **no commit needs to be rewritten** and master becomes A - B<br>  
If your master is: `A - C`<br> and feature is: `A - B` => Merge raises a conflict issue as **C needs to be rewritten** <hr>(Unverified)  

If master :  `A - B - C - D - E - F`,   
feature : `A - B - G - H `  

 
Then do `git merge --squash feature` when you are on master   <br>
It'll become `A - B - C - D - E - F - (all changes from feature in staging area)`  
now a commit with approprite mnessage     
So it changes to : `A - B - C - D - E - F - (one commit wit changes from G, H and all others)`   

</details>

### Diff
`git diff` => Show changes between index(git add ,files only) and working directory   
`git diff --cached` => Between <b><i>index</i></b> with last commit   
`git diff HEAD` =>  Between the files in the working directory and the last commit  
(`git diff HEAD~3` changes the commit described in the above 2 lines by 3 commits, but the commit should exist)

### Tags
`git tag [tag name] [comit ID]` => Creates a local tag at a commit  
`git tag` => Lists all existing tags.  
`git tag --delete [tag name]` => Deletes a local tag  
`git push [remote name] :[tag name]` => Deletes a remote tag, **semicolon is important**  
> **To rename local and remote tag**  
> `git tag [new tag name] [old tag name]` => First create a new tag (local) from the old tag (this dosen't deletes old tag)  
> `git tag --delete [old tag name]` => Delete old tag (locally)  
> `git push [branch name] [new tag name] :[old tag name]` => Pushes the newly created tag, and **deletes the old tag** as nothing was specified beforwe colon ':' 

## Reset (_Modify local commit history_)
`git reset --soft <commit ID>` => Brings all commits from present to <commit ID> and deletes commit history  
But keeps changes in the working directory/folder and staging area  
`git reset --mixed <commit ID>` => Brings all commits from present to <commit ID> and deletes commit history  
But keeps changes in the working directory/folder only (same with just <b>git reset <commit ID></b> as is the default)    
> **Careful Changes below are irreversible !!**

`git reset --hard <commit ID>` =>**Deletes the code completely with history** and file in working directory  
`git rebase -i <commit ID>` => Reorder/change message/delete/merge commits, etc to commits before <commit ID>  
`git rebase -i --root ` => Same as above but rebases all commits from history  
> **_A Rebase or a commit automatically aborts if empty message or command_**


## Vim Commands and snippets
**shift + p** => in command mode do a to paste system clip board  
(https://www.warp.dev/terminus/vim-copy-paste)[https://www.warp.dev/terminus/vim-copy-paste]<br><br><br><br>
# CMD Commands 
`cls` => Clear screen  
`echo hello> a.php` => Write hello in a.php(<b>overrides the complete file</b>)  
`echo Morning >> a.php` => Ammends Morning to hello in a.php  
`type a.php` => Show content in file(`del` to delete file)  
`cd .\A` => Change directory "A"   
`cd ..\` => Go one directory/folder back  
`python -m http.server 8000` => Open web server in one line, folder same as the current directory   

  <br><br>
# Miscellaneous

#### Tags
Tags are the same as branches, they point to a commit, but tags do not change.   
Two types of tags : annotated and lightweight    
(check below lines once)
Annotated:(`git tag -a v1.0.0 -m "..." `) just have more information and need to add -a flag   (check)
Lightweight: just tags and are added as `git tag v1.0.0 -m "..." `  

#### Windows 
To convert the OracleVirtualBox OS file(i.e .vdi/.ova ) to a file usable by Windows hyper-v (hypervisor) in CMD  
**The Format in CMD if you have a virtual box installed is:**  
`start  ...vboxmanage.exe clonehd <vdi file> <destination of vhd > --format VDH`  
>**Copy complete line and change directories:**  
>`start "" "E:\Program Files\Oracle\VirtualBox\vboxmanage.exe" clonehd "E:\Users\DELL\VirtualBox VMs\ubuntu\ubuntu-disk002.vdi" "f:\conv\ubuntuconverted.vhd" --format VHD`
---

#### Windows ??
docker file =>>
```dockerfile
	FROM eclipse-temurin:21
	COPY revenuecalculator-0.0.1-SNAPSHOT.jar /app.jar
	CMD ["java","-jar","/app.jar"]
```
  
get a process at a PORT ==>> `netstat -ano | find "8080"`  
To kill a process with PID ==>>  `taskkill /F /PID 11116`

---

###### _Rebase or a commit automatically aborts if an empty message or command_
- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740
100. First list item
       - First nested list item
         - Second nested list item
> This is a quote
>  [ghhhh](Git_Commands.md#git-commands)-
	[Markdown - Link](#Git-Commands)

multiple lines in coding for markdown use  
```
p
p
```





 
