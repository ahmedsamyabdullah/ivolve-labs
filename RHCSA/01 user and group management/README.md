# Labs RHCSA
# Lab 1: User and Group Management
====================================
step 1: 
create group named ivolve by using command 
sudo groupadd ivolve
then ensure this group created by using command
sudo tail /etc/group
![add group](./imgs/01%20add%20group.PNG)

Step 2:
Create user named ivolveuser by command => sudo useradd -m -s /bin/bash ivolveuser
![add user](./imgs/02%20add%20user.PNG)

Step 3:
assigne password to the user by command => sudo passwd ivolveuser
![assigned password](./imgs/03%20add%20password.PNG)

Step 4:
add ivolveuser to group ivolve by command => sudo usermod -aG ivolve ivolveuser
then check if user added by command => id ivolveuser
![add user to group](./imgs/04%20assign%20user%20to%20group.PNG)

Step 5:
config visudo file by command => sudo visudo 
then add this line => ivolveuser ALL=(ALL) NOPASSWD: /usr/bin/apt install nginx
![config visudo file](./imgs/05%20config%20visudo%20file.PNG)

Step 6:
test configuration by installing Nginx 
first switch to user ivolveuser by command => su - ivolveuser 
then test install nginx by command => sudo apt install nginx -y
should not ask password
![test install nginx without password](./imgs/06%20test%20install%20nginx.PNG)
to check if nginx installed
![check nginx installed](./imgs/06%20check%20nginx%20installed.PNG)



