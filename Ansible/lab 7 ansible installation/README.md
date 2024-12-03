# Lab 7: ansible installation
****
Step 1:
Install Ansible:
command1=> sudo apt-add-repository --yes --update ppa:ansible/ansible
command2=> sudo apt install ansible -y
to verify => ansible --version
![install ansible](./lab7%20imgs/01%20install%20ansible.PNG)
****
Step 2:
Create inventory file that contains two servers servera and serverb
![inventory file](./lab7%20imgs/02%20inventory%20file.PNG)

to verify the inventory file by command => ansible-inventory -i path --list
![verify inventory](./lab7%20imgs/03%20verify%20inventory.PNG)
****
Step 3:
Check the Public Key Setup, command ls ~/.ssh
we should find id_rsa and id_rsa.pub
![public key](./lab7%20imgs/04%20private%20and%20public%20key.PNG)

Copy the Public Key to the Managed Nodes
![copy public key to servera](./lab7%20imgs/05%20copy%20public%20key%20to%20servera.PNG)
****
Step 4: 
verify ad hoc command via ping by using command => ansible -i inventory rhel_servers -m ping
![verify ansible via ping](./lab7%20imgs/06%20verify%20ping.PNG)

