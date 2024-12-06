# Lab 10 => Ansible Roles
****
Step 1:
- Prepare inventory file
![inventory](./lab10%20imgs/01%20inventory.PNG)
****
Step 2:
- Create Structures dirs and files three roles (jenkins,docker,openshit_cli)
- Commands :
    $ansible-galaxy init jenkins
    $ansible-galaxy init docker
    $ansible-galaxy init openshift_cli
![create roles](./lab10%20imgs/02%20create%20roles.PNG)
****
Step 3: 
- jenkins role tree
![jenkins tree](./lab10%20imgs/03%20jenkins%20tree.PNG)

- Install jenkins in path jenkins/tasks/main.yml
![install jenkins](./lab10%20imgs/04%20install%20jenkins.PNG)
****
Step 4: 
- docker role tree
![docker tree](./lab10%20imgs/05%20docker%20tree.PNG)

- Install docker in path docker/tasks/main.yml
![install docker](./lab10%20imgs/06%20install%20docker.PNG)
****
Step 5: 
- openshift role tree
![openshift tree](./lab10%20imgs/07%20openshift%20tree.PNG)

- Install openshift in path openshift/tasks/main.yml
![install openshift](./lab10%20imgs/08%20install%20openshift.PNG)
****
Step 6:
- Create the Playbook that call these roles named lab10.yml
![lab10 playbook](./lab10%20imgs/09%20lab10%20playbook.PNG)

- Run playbook by command => $ansible-playbook lab10.yml -i ./inventory --ask-become-pass





