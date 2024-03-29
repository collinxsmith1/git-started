# How to get going with git


https://devdojo.com/guide/git/ssh-keys

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

ssh-keygen -t rsa -b 4096 -f my-own-rsa-key -C example@gmail.com


#### Add key to host server

ssh-copy-id -i ~.ssh/key_name.pub user@host


#### Add key to ssh-agent

https://askubuntu.com/questions/20863/how-do-i-permanently-add-an-identity-for-ssh

nano ~/.bashrc

--------------------------------------------

eval $(ssh-agent)

ssh-add ~/.ssh/where_ever_privake_key_is

--------------------------------------------

## .ssh directory permissions

~/ home directory : 755 (drwxr-xr-x)

~/.ssh/ directory : 700 (drwx------)

~/.ssh/authorized_keys : 640 (-rw-r-----)

~/.ssh/config : 640 (-rw-r-----)

~/.ssh/*.pub public keys : 644 (-rw-r--r--)

~/.ssh/id_rsa private keys : 600 (-rw-------)

~/.ssh/known_hosts : 600 (-rw-------)

your home directory should not be writeable by the group or others (at most 755 (drwxr-xr-x)).

The only important things are that nothing in .ssh is writeable to anyone else and none of the secret keys are readable to anyone else

--------------------------------------------

## git init the project codebase

https://medium.com/@ganeshpotnuru414_40411/setting-a-new-git-repo-to-existing-code-folder-a43e8bb7d914

https://gist.github.com/hatamiarash7/c5a975f9b03edc71da878b835ec5e4dd

### With an existing project / code base not yet in remote git repo

cd project-folder

git init

git add .

git commit -m "Commit Message"

git branch -M main

git remote add origin git@github.com:collinxsmith1/Project-x-Name.git

git push -u origin main


### Starting with existing code repo

cd project-folder

git clone git@github.com:collinxsmith1/Project-x-Name.git