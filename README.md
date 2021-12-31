# How to get going with git



## Setup ssh keys for github access


### Create ssh key

https://www.golinuxcloud.com/generate-ssh-key-linux/

https://zoomadmin.com/HowToLinux/LinuxCommand/ssh-keygen

-b = define number of bits in the key that will be created (4096)

-t = Specifies the type of key to create. The possible values are “dsa”, “ecdsa”, “ed25519”, or “rsa”

-f = Specify the filepath and name of key

-C = add a comment to the key


#### Create ssh key examples

ssh-keygen -t rsa -b 4096 -f my-own-rsa-key

ssh-keygen -t rsa -b 4096 -f my-own-rsa-key -C collinxsmith@gmail.com


#### Add key to host server

ssh-copy-id -i ~.ssh/key_name.pub user@host


#### Add key to ssh-agent

https://askubuntu.com/questions/20863/how-do-i-permanently-add-an-identity-for-ssh

nano ~/.bashrc

--------------------------------------------

eval $(ssh-agent)

ssh-add ~/.ssh/where_ever_privake_key_is

--------------------------------------------

https://medium.com/@ganeshpotnuru414_40411/setting-a-new-git-repo-to-existing-code-folder-a43e8bb7d914

### With an existing project / code base not yet in remote git repo

cd project-folder

git init

git remote add origin git@github.com:collinxsmith1/Project-x-Name.git

git add .

git commit -m "Commit Message"

git push --set-upstream origin master

git pull — rebase origin master

git push origin master

### Starting with existing code repo

cd project-folder

git clone git@github.com:collinxsmith1/Project-x-Name.git