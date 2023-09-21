

## Create a demo repository

- Create a new **demo** repository in github and clone twice:
```
cd ../../a/demo/
git clone  <your demo repository url>
cd ../../b/demo/
git clone  <your demo repository url>
```

## Create basic feature1 branch (same in both places)

- Create a **feature1** branch in a and add something in it, then push.
```
git checkout -b feature1
echo hello > feature1.txt
git add feature1.txt 
git commit -m "first commit in feature1 in a"
git push --set-upstream origin feature1
```
- Verify that the branch was created in github, then get everything locally:
```
cd ../../b/demo/
git fetch
git branch -a
git branch feature1 origin/feature1
git checkout feature1
ls
```
(note that you could use **pull* to do the same)

## Create the problem

- Go to a, create a new file, commit and push to github:
```
cd ../../a/demo/
echo hello > file2.txt
git add file2.txt 
git commit -m "adding file2.txt ti feature1 in a"
git push
```
- Go to b, create a file, add, commit BUT DO NOT PUSH.  
Instead, **fetch**:
```
cd ../../b/demo/
echo hello > file3.txt 
git add file3.txt 
git commit -m "adding file3.txt to feature1 in b"
git fetch
```

## Looking at the changes in b

- A **git status** will show me the following:
```
git status
On branch feature1
Your branch and 'origin/feature1' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
```
- Using **git pull** and editing the comment I merged the missing commit into b:
```
git pull
```
- but this is not the end of it.  
Doing **git status** again will show the problem:  
Now b has information that is not updated to a (and to github).  
A **git push** will solve this.

## Looking at the changes in a

- The only thing left to do is in a local repository
- Do **git fetch** first to see, them **git pull** to merge
