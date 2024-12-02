# Labs RHCSA
# Lab 6: SSH Configuration
****
General info:
- using ubuntu vm and RHEL9 vm
****
Step 1:
Generate SSH key on ubuntu vm by => ssh-keygen -t rsa -b 4096
![generate ssh key](./lab6%20imgs/01%20generate%20ssh%20key.PNG)

The command creates:
1- Private key: ~/.ssh/id_rsa
2- Public key: ~/.ssh/id_rsa.pub
****
Step 2:
Transfer the public key to RHEL9 VM by command => ssh-copy-id ahmedsamy@192.168.1.9
![copy ssh id](./lab6%20imgs/02%20copy%20ssh%20to%20rhel.PNG)
****

Step 3:
Test the SSH Connection to connect with RHEL9 by command => ssh ahmedsamy@192.168.1.9
![test ssh](./lab6%20imgs/03%20test%20ssh.PNG)
****

Step 4:
connect directly by command => ssh ivolve
first-> vim ~/.ssh/config
and add this text
![connection directly](./lab6%20imgs/04%20add%20connection%20directly.PNG)
****

Step 5:
Test ssh ivolve connect directly to RHEL9 server
![test connect diirectly](./lab6%20imgs/05%20test%20connection%20directly.PNG)


