# CI/CD of Docker image using jenkins, Ansible and Git
## Description
Here im explaining the details of contines deployment of Docker image. Here i'm using Jenkins as CI/CD pipeline, the docker image building from git repository and the ansible-playbook is using for to pull,build docker image and create container with application. 
## Features
- Easy to deploy a container using compose file. We can create more than one containers using a compose file.
- compose file writing in a .yml file
## Pre-Requests
- Install Java and jenkins in the host machine.
- Install Git on the host macine also install Ansible
- Create two more servers for build image and test application.
- Create hosts file and the build and test servers details.
##### Ansible Modules used
- [shell](https://docs.ansible.com/ansible/2.9/modules/shell_module.html)
- [yum](https://docs.ansible.com/ansible/2.9/modules/yum_module.html)
- [pip](https://docs.ansible.com/ansible/2.9/modules/pip_module.html)
- [docker_login](https://docs.ansible.com/ansible/2.9/modules/docker_login_module.html)
- [docker_image](https://docs.ansible.com/ansible/2.9/modules/docker_image_module.html)
- [docker_container](https://docs.ansible.com/ansible/2.9/modules/docker_container_module.html)
- [git](https://docs.ansible.com/ansible/2.9/modules/git_module.html)
- [service](https://docs.ansible.com/ansible/2.9/modules/service_module.html)
#### Jenkins Installtion
```
yum install java-1.8.0-openjdk-devel -y
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum -y install jenkins
systemctl start jenkins ; systemctl enable jenkins
```
#### Additional packages in host machine
```
# yum install git -y
# amazon-linux-extras install ansible -y
```
#### Important Jenkins Configuration
Provide repository URL of application
![alt_text](https://i.ibb.co/64GhDzw/chrome-f-FROA1-YDBJ.png)

Prvide ansible playbook file path and hosts file oath
![alt_text](https://i.ibb.co/NsMyVbm/chrome-13-Ba-IMMTz-D.png)

Webohook configuration in git repository and inform about this in Jenkins
![alt_text](https://i.ibb.co/TRCWpjG/webhook.png)
![alt_text](https://i.ibb.co/zXC8zwX/chrome-Anmm-Kb7-I9r.png)
## Behind the Playbook
The playboom has two hosts. One for build server and another for test server.
For more details please check main.yml file.
## Architecture
![alt_text](https://i.ibb.co/K0XvV5w/docker-jenkins.png)

### ⚙️ Connect with Me

<p align="center">
<a href="mailto:lakshmipriya458@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/lakshmipriya-p-c-7b5a2b88/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a> 
