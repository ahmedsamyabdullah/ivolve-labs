# Lab 8: ansible playbooks for web server config
****
Step 1:
Create playbook named install_nginx.yml and write the following contents<br>
![install nginx](./lab8%20imgs/01%20install%20nginx.PNG)
****
Step 2:
Run Playbook<br>
command => ansible-playbook -i inventory install_nginx.yml --ask-become-pass <br>
we use (--ask-become-pass) to avoid issue about missing sudo password
![run playbook](./lab8%20imgs/02%20run%20playbook.PNG)
 
Verify that Nginx was installed in rhel_servers <br>
command => sudo systemctl status nginx.serviice
![verify nginx](./lab8%20imgs/03%20verify%20nginx%20installed.PNG)

