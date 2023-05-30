
## Create a local repository

- Create your local repository by typing:  
**git init**
- Config git user name and email (these are not github user and email):
  - **git config --local user.name "Yuval Teacher"**
  - **git config --local user.email yuvalaws1@gmail.com**
- Create a file, add it to the staging area, then commit.


## Add a remote repository

- First, make sure that you select **SSH** in your repository, prior to copying the remote address.
- Then type the command to create a remote definition in your local git repository:  
**git remote add githubrem git@github.com:yuvalaws1/gittest.git**  
(I use githubrem as my name for a remote, you can choose another name)
- Verify the remote you have created:  
**git remote -v**


## Add SSH key

- We start by creating a pair of keys, as in the following example:  
**ssh-keygen -t ed25519 -C "yuvalaws1@gmail.com"**  
The response:  
Generating public/private ed25519 key pair.
- Now I can change the key name:  
Enter file in which to save the key (/home/yuval/.ssh/id_ed25519): /home/yuval/.ssh/yuvalaws1_all`  
- I left everything else empty
- To verify:  
**ls ~/.ssh**

## Add keys to the ssh agent

You can read about the ssh agent [here](https://levelup.gitconnected.com/ssh-agent-explained-cf947034e63d).  

**eval "$(ssh-agent -s)"**
**ssh-add ~/.ssh/yuvalaws1_all**

## Add the public key to github

Add the public key to github like this:  
- Cat the public key:  
**cat ~/.ssh/yuvalaws1.pub**
- Copy with your mouse
- Go to your account settings (top-right-settings)
- Click **SSH and GPG keys**.
- Click **New SSH key**.
- In the "Title" field, add a descriptive label for the new key. 
- Select the type of key (authentication in out case)
- In the "Key" field, paste your public key (including the email part)
- Click Add SSH key.

## Push your changes

- Push you changes (you are in a branch called **master** and we are setting the remote branch that we are pushing the changes into):  
**git push --set-upstream githubrem master**
- Refresh the github view to see the changes

