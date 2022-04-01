# ks
Step-by-step guide (Windows) OSX Steps below
Establish an SSH Key
Open Windows explorer.
Type in the following path location in the navigation bar "C:\Users\"
Locate the "{USERNAME}" folder, right-click and select "Git Bash Here".
In the command line enter the following ssh-keygen -t rsa -C "your_email@example.com"

Press enter until you see a key fingerprint generated with the command line, then you can close the command window.
In your open Windows explorer window, go into your usernames folder, "C:\Users\{USERNAME}\", now a ".ssh" folder should exist.
If you do not see a ".ssh" folder it may be hidden and requires a Windows settings change, see that here.
Open your ".ssh" folder and you should see two files, one of which is a MS Publisher Document (your public key), the other is your private key.

Provide GitHub a Public Key
Open a web browser and go to: https://github.com/settings/keys
Login with your GitHub credentials.
Click on "New SSH Key" button.
Open your MS Publisher document within your .ssh folder (notepad may be easier to open in), copy then entire public key including email at the end.
Provide a SSH title, and your SSH public key value.
Click the 'Add SSH Key' button.
Click the Enable SSO drop down, to enable Meredith Single Sign On access with SSH public key.
Provide Atlassian SourceTree a Private Key
Open SourceTree.
Click Tools > Options
On the General tab, locate the 'SSH Client Configuration' section, change drop down to "OpenSSH".
Click the elipses (...) button, go to your .ssh folder and select the "id_rsa" or your private SSH key file, select Open.
On the General tab, click the 'OK' button at the bottom of the form and close SourceTree.
Clone GitHub repository to SourceTree client
      Example:
Open a web browser and go to: https://github.com/MeredithCorp/katalon.studio or https://github.com/MeredithCorp/postman.newman
Login with you GitHub credentials.

Click on the green "Clone or Download" drop down button.
Click on the "Use SSH" link.
Copy the path provided.
In Atlassian SourceTree, Click the "+" button to add a new local repo tab.
Click the "Clone" button, paste the SSH link into the Source Path / URL field.
Create a folder "katalon.studio" or "postman.newman" within your local "C:/repos/" folder location.
Set the "Destination Path" to the "katalon.studio" or "postman.newman" located "C:/repos/katalon.studio" or "C:/repos/postman.newman".
Provide a local repo name and click the "Clone" button.
Step-by-step guide (OSX)
Establish an SSH Key

Open terminal
Navigate to ssh directory

$ cd ~/.ssh
Generate public/private rsa key pair using your own email address. NOTE: use your email alias address

$ ssh-keygen -t rsa -C "<your_meredith_email@meredith.com>"
Enter the file to save the key, or press enter for the default location. Default is .ssh/id_rsa, but if you already have this in use you can input a new file like: /Users/<you>/.ssh/id_rsa_katalon 

Press enter twice when prompted, or supply a passphrase

Verify identification and public key files were created like: .ssh/id_rsa_katalon and .ssh/id_rsa_katalon.pub 



Provide GitHub a Public Key

In your browser, login to github.com
Navigate to https://github.com/settings/keys
Click 'New SSH Key'
Give the key a title
paste the entire key into the key section. The end of the key will show your email address.
to open the key file, switch back to terminal and enter the following using your own public key: 

$ open -e .ssh/id_rsa_katalon.pub
Click 'Add SSH key'
Click the Enable SSO drop down, to enable Meredith Single Sign On access with SSH public key.
Provide Atlassian SourceTree a Private Key

Open SourceTree.
Click Preferences->General
Fill out your Github user info
Click Preferences->Accounts
On the Account tab, click "Add..."
Select Github, and select Oauth as the connection type
Click "Connect Account" and you'll be taken to a Github page which will authorize you via SSO
Click Save.





Please confirm your 'known_hosts' file was created within your .ssh folder. It has been noticed in some Mac instances where this does not happen preventing cloning. To resolving this, run the below snippet within the .ssh folder. Restart SourceTree and attempt cloning.

RUN

ssh-keyscan github.com >> ~/.ssh/known_hosts


Clone GitHub repository to SourceTree client
      Example:

Open a web browser and go to: https://github.com/MeredithCorp/katalon.studio
Login with you GitHub credentials.

Click on the green "Clone or Download" drop down button.
Click on the "Use SSH" link.
Copy the path provided.
In Atlassian SourceTree, select remote button.
Click the carrot next to New and select "Clone from URL"
In the pop-up window, paste SSH link that you copied into the Source URL field and then click away so it can search.
Click in the "Destination Path" field and select you katalon.studio folder.
If it does not exist, create a folder with the name repos in this location, "Users/{username}/Documents/repos/".
Then create a sub-folder called "katalon.studio" under the repos folder you just created.

The local repo name should auto-populate and click the "Clone" button.





