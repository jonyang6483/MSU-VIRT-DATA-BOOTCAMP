# Fundamentals

To learn how SSH-keys work then read this short tutorial from Khan Academy which provides a nice interactive example.

# Overview

SSH stands for Secure Shell

SSH-keys are used as part of a security process so encrypted information can be transferred between two sources and decoded to an interpretable form such that there is confidence that the two sources are legitimate and not an unwanted third-party.

I typically call the two sources the local and remote machine.  In the case of GitHub, the local machine is your computer and the remote machine is the cloud-based GitHub account.  There are several other names used.

SSH-keys are generated with an algorithim on the local machine.  Two pairs of keys are created during this process.  One key is the private key and for our purposes it will be named something like id_{security protocol name} and the public key will look the same but have the suffix of .pub added to indicate that it is the public key.  It is important that we only share the public key (aka the contents inside the id_{security protocol name}.pub file).  The public key is used for encryption.  The private key is used for decryption.  There is a situation where these roles can be reversed but we still do not give out the private key under any circumstances.

The public key is just a text file and if you look inside it you will typically see text that indicates the protocol used and the email attached to the SSH key.  Sometimes people think the output of the ssh-key command in terminal/gitbash is the ssh-key but this is actually what is called the fingerprint and randomart image.  Here is an example:

![SSH Keys](00-Documents/images/ssh-images/ssh-generation-terminal.jpg)

The orange part of the image is the SSH key generation command using the ed25519 protocol.  There are several different algorithims that can generate the ssh-keys.

The inputs to for the image were not customized and I hit enter for each one.  
* The first request was 'enter file...' and this is asking me where to put the file and what to name it.  It provides the default in parethesis.  
* The second request was 'Enter passphrase...' and this is adding extra security so if someone gets my private key then they must provide a password to access it.
* The third request is just the confirmation of the above passphrase.
* Now the next part is a nice confirmation.  The green and yellow text is the location of the ssh-keys.  These are just text files.
* I believe everything else is used for manual verification of your authenticity so we will not bother with this.

The actual content inside the above generated public key looks like this:  
>```ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOgqz9ciCwISG9i1Mcwg/TYERR7GGppra9mJrPALWQC9 ejw.data@gmail.com``` 

**_Note_**:  This ssh-key is one line of text with two spaces (3 text groups).  It shows up differently based on your display window size but it shows first the protocol then a string of text with a slash and then the email address.  This code does not match the fingerprint shown in the image.

# Setting up SSH Keys:

1.  Check that Git is installed.  From terminal (mac) or GitBash (PC), type `git --version` and you should get a response.  If the response is somethign like `command not found` then install Git based on the Prework Instructions.
1.  Check that your name has been added to Git - PC/mac:  `git config --global user.name` 
1.  To set the name - PC/mac:  `git config --global user.name " Your Name"`
1. Check that your email has been added to Git - PC/mac:  `git config --global user.email`
1. To set the email (same as gihub/gitlab) - PC/mac:  `git config --global user.email “youremail@whatever.com”`
1.  Check to see if you have existing ssh-keys.  In termainal/GitBash, type `ls -al ~/.ssh`.  If you see a list of keys that have a format like discussed earlier then you will be able to use the copy commands to extract the contents (later in instructions).  The above command says "list all files in the root .ssh folder".  Even if you have keys you can overwrite them by following the next few steps.  

    **Note**:  If you recieve a message that you cannot use RSA protocol then use the one recommended.  GitLab supports these SSH key types:  RSA, ED25519, ED25519_SK, and ECDSA_SK.  I believe there are more problems using DSA and ECDSA.  First try to use ED25519 and if that does not work then try RSA (repeat the steps) 

1.  Generating a new SSH-key for PC/mac with ED25519
    * Do these steps in GitBash/terminal:
      *  `ssh-keygen -t ed25519 -C "your_email@example.com"`
      *  Asked to "Enter a file...":  press Enter
      *  Asked to "Enter passphrase ...":  press Enter
      *  Asked to "Enter same passphrase again":  press Enter
      *  Now you will see text like in the image above. 
    * Next start the ssh-agent:  
      * `eval "$(ssh-agent -s)"`
      * Should see a message like "Agent pid xxxx"
    * Next add the private key to the agent:
      * `ssh-add ~/.ssh/id_ed25519`      
    * Lastly, copy contents of public key:
      * PC: `clip < ~/.ssh/id_ed25519.pub`
      * mac:  `pbcopy < ~/.ssh/id_ed25519.pub`
    * If this works, you should be able to paste the key from the clipboard.  It should look like the example above.  This text needs to be added to both GitHub and GitLab.  Go to those steps below.  
<br>

1.  **This is an alternate SSH key method that does not need to be used** unless after doing `Step 7` above and ALL the remaining steps from `Pasting Public Key into GitLab` downwards results in permission denied messages in the last step of this document.  If the process fails then come back to this step and try this key generation method and redo the steps from this point further down the document.Generating a new SSH-key for PC/Mac with RSA
    * Do these steps in GitBash/terminal:
      *  `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
      *  Asked to "Enter a file...":  press Enter
      *  Asked to "Enter passphrase ...":  press Enter
      *  Asked to "Enter same passphrase again":  press Enter
      *  Now you will see text like in the image above.  
    * Next start the ssh-agent:  
      * `eval "$(ssh-agent -s)"`
      * Should see a message like "Agent pid xxxx"
    * Next add the private key to the agent:
      * `ssh-add ~/.ssh/id_rsa`
    * Lastly, copy contents of public key:
      * PC: `clip < ~/.ssh/id_rsa.pub`
      * mac:  `pbcopy < ~/.ssh/id_rsa.pub`
    * If this works, you should be able to paste the key from the clipboard.  It should look like the example above.  This text needs to be added to both GitHub and GitLab.  Go to those steps below.
    
<br>  

Pasting Public Key into GitLab

  1. Login to GitLab:
  1. Go to the profile icon in the upper right corner and select "Preferences"

  ![GitLab Profile](00-Documents/images/ssh-images/gitlab-profile.png) 
  1. Slect "SSH Keys" from the left menu

  ![GitLab Menu](00-Documents/images/ssh-images/gitlab-ssh-key-menu.png)

  1.  Paste the Public Key into the large input box
    * PC:  CTRL + V
    * mac:  CMD + V
    * Right Click
  1.  The title can be anything and the expiration date can be left blank.
  1.  Select "Add Key"

  ![GitLab Add Key](00-Documents/images/ssh-images/gitlab-ssh-key-add.png)

  <br>

  >### You must also do this process for GitHub
## Pasting Public Key into GitHub

1.  Login to GitHub Account. 
1.  Go the the profile icon in the upper right corner and select "Settings"
![GitLab Profile](00-Documents/images/ssh-images/git-hub-profile.png)  
1.  Select "SSH Keys" from the left menu
![GitLab Menu](00-Documents/images/ssh-images/git-hub-ssh-key-menu.png)
1.  Paste the Public Key into the large input box
    * PC:  CTRL + V
    * mac:  CMD + V
    * Right Click
1.  The title can be anything and the expiration date can be left blank.
![GitLab Add Key](00-Documents/images/ssh-images/gitlab-ssh-key-add.png)

>**The Same Public Key can be used for both websites**

<br>
<br>
If there are errors then we may need to do some updates or other changes.  The documents below cover some of the most common issues.  The GitHub documents are probably the best resources.  

<br>
<br>

## Testing Connections in Terminal/GitBash
1.  All the commands should be done in GitBash (PC) or Terminal (mac)
1.  Check SSH Key for GitLab - Type: `ssh -T git@nu.bootcampcontent.com` and then hit enter. (Please note that there's one space between `ssh` and the hyphen, no spaces between the hyphen and the `T`, and the remaining `'git@....`. You might see a message saying that the authenticity of the host can't be established. This is nothing to worry about. When prompted with "Are you sure you want to continue connecting (yes/no/[fingerprint])?" Please type "yes" and then hit enter. If this succeeds, you'll see "Welcome to GitLab, @'your username'! 
1.  Check SSH Key for GitHub - Type: `ssh -T git@github.com` and then hit enter. If this succeeds, you will see "Hi 'yourusername'! You've successfully authenticated, but GitHub does not provide shell access."
1.  That is everything.  If you get those messages then you should be ready to go.  If you don't get those messsages then most likely you did not do all the steps and need to go back to the beginning and do all steps.  

## References:

* [Check if Public Keys Already Exist](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)
* [Generating SSH Keys and Adding Public Key to GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* [Copy Public Key to Clipboard](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

* [GitLab Documentation](https://docs.gitlab.com/ee/ssh/)