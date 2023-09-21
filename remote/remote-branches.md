# Remote Branches



## Create Repositories

- Go to your github account anc create a public repository.  
(I have created one called **demo**)  
This is just a training session, so you will remove this repository when you're done.
- Localy, create a working directory, and 2 directories under that:
```
mkdir workgit
cd workgit/
mkdir a
mkdir b
```
- Clone your **demo** repository into **a** and **b**:
```
cd a/
clone <your repository url>
cd ../b/
clone <your repository url>
```
## Brance feature1

- Goto your demo repository in **a**, and check git status:
```
cd ../a/demo
git status
```
- As you can see, you are in the master branch.  
Go ahead and create a new branch and switch to it.  
Then create a file, add, commit and try to push:
```
git checkout -b feature1
echo hello > feature1.txt
git add feature1.txt 
git push
``` 
- The last push command fails with something like this:
```
fatal: The current branch feature1 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature1
```

osboxes@osboxes:~/Documents/workgit/a/demo$ git push --set-upstream origin feature1
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 230 bytes | 230.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:YuvalShaul/demo.git
 * [new branch]      feature1 -> feature1
Branch 'feature1' set up to track remote branch 'feature1' from 'origin'.
osboxes@osboxes:~/Documents/workgit/a/demo$ 
osboxes@osboxes:~/Documents/workgit/a/demo$ 
osboxes@osboxes:~/Documents/workgit/a/demo$ git branch -vv
* feature1 2d7600d [origin/feature1] creating feature 1
osboxes@osboxes:~/Documents/workgit/a/demo$ 

