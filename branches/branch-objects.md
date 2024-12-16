


## First commit with two files
Create a directory and init a git repository in it:
```
mkdir d1
cd d1
git init
```
Now, type the following:
```
echo "hello" > f1
echo "world" > f2

git add f1 f2
git commit -m "first commit"
```

## Browse the objects that were created

Find the commit hash:
```
git rev-parse HEAD
```
In my case it returned : 066a08ad1bc5203922d38b99d1b624f80c08d2ff  
Since this is the case, I could see the file here:
```
$> ls .git/objects/06
6a08ad1bc5203922d38b99d1b624f80c08d2ff
```
But to be able to read this binary file in a "human" way, I'll use:
```
$ git cat-file -p 066a08ad1bc5203922d38b99d1b624f80c08d2ff 
tree 5603be14a56674240486979d4eab8e4b87ae2bda
author Yuval <yuval.shaul@gmail.com> 1734351257 -0500
committer Yuval <yuval.shaul@gmail.com> 1734351257 -0500

first commit
$>
```
I can see that it points to a tree object.  
Since the hash starts with 56, the file is under the **objects/56** directory (under .git):
```
$> ls .git/objects/56
03be14a56674240486979d4eab8e4b87ae2bda
$>
``` 
But, to read it I'll use:
```
$> git cat-file -p 5603be14a56674240486979d4eab8e4b87ae2bda
100644 blob ce013625030ba8dba906f756967f9e9ca394464a	f1
100644 blob cc628ccd10742baea8241c5924df992b5c019f71	f2
$> 
```
And I can read this as well:
```
$ git cat-file -p ce013625030ba8dba906f756967f9e9ca394464a 
hello
$> git cat-file -p cc628ccd10742baea8241c5924df992b5c019f71
world
$>
```

