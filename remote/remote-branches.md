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
In fact, there are no branches created realy, so if you try **git branch** you'll see no branches (so master is just a default name to use if you just commit without creating a new branch).
- Go ahead and create a new branch and switch to it.  
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
so we are not tracking a remote branch.

## Tracking a remote branch

- The push command has many options, but if these are not configured then the current branch is pushed to the corresponding upstream branch.  
The problem is that we don't have a current upstream branch, so we have to create one.  
We'll push using the suggested upstream configuration:
```
git push --set-upstream origin feature1
```
- Now we can see how are local feature1 branch tracks the remote one.
Type:
```
git branch -vv
```
- Let's repeat everything with another branch called feature2:
```
git checkout -b feature2
echo hello > feature2.txt
git add feature2.txt 
git commit -m "first commit for feature2"
git push --set-upstream origin feature2
```

## Remote Branches

- Use the follwing command to inspect all remotes:
```
git remote -v show
```
- Try the following to see ALL branches (including remote branches):
```
git branch -a
```
- Try this to see only remote branches:
```
git branch -r
```
- Add **-v** to see more details:
```
git branch -r -v
```
