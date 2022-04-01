# ks
 Step-by-step guide
Setup new Bitbucket Repository
Go to BitBucket
Go to desired Bitbucket project  https://stash.meredith.com/projects/MQA

Set User Access

Go to Settings
Select repository permissions > User access
Set Group Access
Go to Settings
Select repository permissions > Group Access
Set "im dev" & "imdevelopers" to read & write permissions.
Set public access keys
Go to Settings
Select Access keys.
Note each machine attempting to access the repository may need a newly generated .ssh public access key. e.g., For virtual machines, if a user has multiple .ssh keys generated across each VM, each of those keys will need provided to the repository in order to access the repository.
Clone repository.
Click 'Clone' button, select Clone in SoureTree (must have SourceTree installed).
Within SourceTree, select a cloning location and name for your new cloned repository.
If a new or empty repository, anything added to this repository would then need to be committed & pushed to BitBucket. Otherwise, any existing files from the cloned repository should be cloned down to your local repository copy.
