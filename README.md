
#this project will CONFIGURE servers through ansible
# netwotkautomation by ANSIBLE
# done by SIDDAVATAM.SALMANUDDIN AHAMAD
#BTH 

2. Create ssh key pairs (ssh-keygen -t rsa) 
- remember the path where the keys are .
- remember that the server key file permissions should be 400, if not try "chmod 400 <private key path> "

3. edit my config file and save the config file in /.ssh/
#######
the config file has the ip address of my servers and is commented indicating where to change ip address with your ip addresses.
#######

4. type the following commands in ubuntu, replace "<path in your system .....>" with the path of your system.

###############################################################
rsync  home/.ssh/server_key  bastionET2598:home/.ssh/server_key

#here home/.ssh/server_key is my private key path in my laptop, and i saved it in bastion server at path  ~/.ssh/server_key

#note- if you save at other place, your private keys, please change path in config file, in hosts(the file which you get in repository ) file 

rsync  home/.ssh/config  bastionET2598:home/.ssh/config
###############################################################

3. after the above steps are done, run the below command in your system ubuntu terminal

$cd home/salman_ansible
$ ansible-playbook -i hosts automation.yaml

- ansible playbook with take some time to deploy on each server so keep paitence to get it completed.
