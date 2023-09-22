# Branching Basics

## Creating a repository

- Create a new directory called demo (could be anywhere you are comfortable working at), **cd** into this directory and initiage a git repository:
```
mkdir demo
cd demo
git init
```
- Check the status of this repository:
```
git status
```
- Verify that the master branch there does not really ewxist:
```
git branch
```
(so no branch currently exists)


## Branches

- You could not create a new branch unless the HEAD already points to some commit.  It means that the **master** branch that you see as output of the **git status** command is just a name that will be given to the branch that will be created when you create the first commit.
- Create-and-switch-to a new branch called feature1.  
```
git checkout -b feature1
```
- Again, since no commit was created, no branch was really created.  
Use the following to make sure you understand what happened:
```
git branch
git status
```
- Create a file, add it and commit:
```
echo hello > feature1.txt
git add feature1.txt
git commit -m "adding first file"
```
- Create a second branch called feature2 (but do not switch to it yet):
```
git branch feature2
```
- Now switch to the new branch:
```
git checkout feature1
```



## Merging
