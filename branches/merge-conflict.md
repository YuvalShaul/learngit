# Merge Conflicts

## Preparations

Use your previous knowledge to preoare the following:

- A repository called *demo**
- A branch called **feature1** with:
  - a file called file.txt
  - The file has 3 lines with the following content (copy and paste exactly these characters):
  ```
  1111111111
  2222222222
  3333333333
  ```
- A branch called **feature2** that:
  - start when last section was completed (so feature2 has the same file and content)
  - Editted file.txt and added changed the middle line like this:
  ```
  1111111111
  2--------2
  3333333333
  ```
- Add a new file to feature2 that is called file2.txt
- Add and commit this to feature2
- Go back to feature1
- Edit the file to this state:
```
1111111111
2++++++++2
3333333333
```
- Add and commit

## See Conflict!!!

- Go to branch feature1 and try to merge feature2:
```
git checkout feature1
git merge feature2
```
- You should see a conflict.  
  - Note that all changes were not done, even the new file that has no conflicts.  
  (use **git status** to see this)
  - Edit file.txt to see how it was changed by the conflict.
- Make the changes, by writing what you really want to be written to line 2.
- Add everything that is not added
- Commit
