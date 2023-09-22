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
- Verify that the master branch there does not really exist:
```
git branch
```
(so no branch currently exists)


## Branches

- You could **not** create a new branch unless the HEAD already points to some commit.  
It means that the **master** branch that you see (when using **git status**) is just a name that will be given to the branch that will be created when you create the first commit.
- Create (and switch-to) a new branch called feature1.  
```
git checkout -b feature1
```
- Again, since no commit was created, this branch was **not** really created.  
Use the following commands to make sure you understand what happened:
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
git checkout feature2
```
- Create a second file called feature2.txt.  
Edit feature1.txt and add a new line.
Add both files and commit. 
```
echo hello > feature2.txt
vi feature1.txt
git add feature1.txt feature2.txt 
git status
git commit -m "adding a new file and adding a line to old file (in branch feature2)"
```

## Merging

- Checkout to feature1 branch and see that feature2 changes disappeared.
```
git checkout feature1
ls
cat feature1.txt
```
- Merge branch feature2 into the current branch(feature1):
```
git merge feature2
```
- Inspect:
  - what is the current branch
  - what files and content you see
- Inspect each branch log:
```
git log
git log feature2
git log feature1
```