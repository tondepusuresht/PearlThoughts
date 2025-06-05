automates the deployment of a Yii2 PHP application using:
1.Docker Swarm on an EC2 instance
2.NGINX as a host-based reverse proxy
3.Ansible for provisioning and deployment
Requirements:-
Ansible,AWS EC2,Docker,Docker Compose,NGINX,Git  
Project Structure:
Created struture in this floder

 Setup Instructions:-
1.Launch an EC2 instance any Linux OS
2.Ensure port 80, 22, and 9000 are open in the security group
3.Attach an SSH key (PEM)
Clone This Repo:-
the clone repo in source amd Update Inventory File
Run the Playbook:-
ansible-playbook -i inventory playbook.yml
check in browser http://<-ec2-public-ip>/


