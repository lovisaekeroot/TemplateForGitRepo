# TemplateForGitRepo
This is a template for creating and working with a GitHub repository for myself.
Note: This is not for working with branches. Only with one main branch for simplicity.

## Step 0:
Have "install git" made in the terminal on the local computer. 
Set username and email in the terminal as well:

> git config --global user.name lovisaekeroot

> git config --global user.email loviisa_ekerot@hotmail.com


#### Confirm set username correctly:
You can check that you have set the user name correctly by the command:

> git config --global user.name

You should see your username printed out below the given command.

Exactly the same but for "user.email"

## Step 1:
Create a GitHub Repository with a name and have the "Add README.md" added in the creation of the repository.

## Step 2:
Use SSH Keys to connect the local computers with the GitHub repository. Do this by using the following commands in the terminal on your computer:

#### 1. Generate a SSH Key (one for each computer and change to your own email):
ssh-keygen -t ed25519 -C loviisa_ekerot@hotmail.com 

-> "Generating public/private ed25519 key pair."

-> Enter file in which to save the key: [Only click enter, do not enter anything]

-> Enter passphrase (empty for no passphrase): [Only click enter, not needed]

-> Enter same passphrase again: [Click enter again]

-> Your identification has been saved in /Users/user/.ssh/id_ed25519

-> (More information about public key and key fingerprint. Do not have to remember)

#### 2. Begin the ssh-agent:
eval "$(ssh-agent -s)"

-> Agent pid 8584

#### 3. Check if .ssh config-file exists
open ~/.ssh/config

If a new window is opened, the file exists. Skip 2.4 and go to 2.6
#### 4. Generate/Create a .ssh config-file
touch ~/.ssh/config

#### 5. Open the .ssh config-file again (step 3)
open ~/.ssh/config

#### 6. Add the following in the config file
Host *

  AddKeysToAgent yes
  
  UseKeychain yes
  
  IdentityFile ~/.ssh/id_ed25519
 
--> Save the new information by having "CTRL + S"

#### 7. Add the SSH Key to your account
ssh-add -K ~/.ssh/id_ed25519

Enter the passphrase if given, otherwise only click "Enter"

-> Identity added: /Users/user/.ssh/id_ed25519 (user.email)

#### 8. Copy the SSH Key
pbcopy < ~/.ssh/id_ed25519.pub

#### 9. Save the SSH Key in GitHub for it to be saved for the computer
Go to the GitHub webpage again. Go to "Profile --> Settings --> SSH and GPG keys".

By the section "SSH keys", click on "New SSH key". Enter a proper name for the key as the "Title", and paste in the key in "Key" that was copied in step 2.8

Click on "Add SSH key"

## Step 3:
Now your SSH Key is stored in GitHub and connected to your local computer.

Lets try to connect to your GitHub Repository!

By doing step 2, it should not be needed for you to enter the SSH key for each pull or push when using Git in your project.

## Step 4:
Go to your repository in the GitHub webpage. Click on "Code -> SSH" and copy the link that is presented.

#### Connect the repository to your local computer
In the terminal, go to the folder in the local computer where you want to connecct your GitHub repository. This is the folder that you can push and pull files from and to. 

REMEMBER: It is important that you stand in this folder in the terminal when you do either push or pull! It is the connection between GitHub and your computer.

When standing in the folder in the terminal, enter the following command:

git clone git@github.com:lovisaekeroot/Precisit.git (git clone copied_webadress)

-> Cloning into 'Repository'...

-> remote: Multiple remote messages

-> Receiving objects: 100%, done

-> Resolving deltas: 100%, done

## Step 5:
Check such that the repository is correctly cloned by enter the command in the terminal:
ls

-> Repository_Name

## Step 6:
Move into the repository in the local computer to check that everything is there:
cd Repository_Name

-> do another "ls" command to see the files in the repository

## Step 7:
If you can see all files in the repository by entering "ls" in step 6, the connection is finished! Congratulations, your connection to your repository is done correctly! 

# CONGRATULATIONS!
YOU DID IT! Celebration time!


# Working with Git - Good stuff

## Git pull
One good thing to do before starting to work with a file in the repository is to always pull down the latest version of the repository:

> git pull

## Adding/updating a (new) file
When a new file is created and should be added into the repository, do the following:

> git add .

> git commit -m "Some message for what it is, ex: Adding README.md"

> git push

In the end of this you should see some "main -> main" without any error messages!

## KEEP UP THE GOOD WORK!

Links used to create the template:

https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git

https://docs.github.com/en/get-started/quickstart/set-up-git

https://opensource.com/article/18/1/step-step-guide-git

https://www.linuxfordevices.com/tutorials/linux/connect-to-github-with-ssh

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

https://docs.github.com/en/get-started/quickstart/hello-world
