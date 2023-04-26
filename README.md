# Permission-denied-publickey-error
How to fix git@github.com: Permission denied (publickey) error


When trying git push or git pull command, the following error may occur.

git@github.com: Permission denied (publickey). fatal: Could not read from remote repository. Please make sure you have the correct access rights
and the repository exists.

The reason this error occurs is that the ssh key connected to the git@github.com is not set

The solution to this is simple. You can create an ssh key and register this key to your account on github.

First create an ssh key.
** ssh-keygen -t rsa -C “your GitHub account email”** 


When you run ssh-keygen, a terminal window asks you to specify where to create a key.
If you just press Enter, it will be created in the default location ** (~/.ssh/id_rsa.pub)** .


Next, you will be asked to specify a password. If you want to specify a password, you can enter it or just press Enter.
Then it will say that the key has been created in ** ~/.ssh/id_rsa.pub** . Never disclose this key to anyone else. 
(If you make it public, it's like saying, just use my github to your heart's content)



Since the generated key needs to be registered on Github, copy the contents after ** cat ~/.ssh/id_rsa.pub**.

Set the created key to your Github account and you're done. ** First, log in to GitHub and go to Settings -> SSH and GPG Keys** .

** Click the New SSH key button, enter the title as desired, and insert the copied ssh key (~/.ssh/id_rsa.pub)**  key we created in the key input section below.

Now, if you do git pull or git push, you can see that the error is resolved.
