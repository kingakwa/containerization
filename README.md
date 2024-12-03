# containerization

CONTAINERIZATION
DOCKER
======
Docker -- Is a containerization multi-platform software use to create, build
 ship, share and deploy applications as containers
 Build applications 
 ship applications 
 deploy applications
IQ: How many environmentS are you supporting in your CURRENT role??
 Development environment 
 Testing/QA/Stage environment 
 Production environment
Containers --> contains are everything required for an application to run 
 (App Files (code), Dependencies 
 (Softwares +Libraries), ENV vars & Other Configuration files) 
 which is required for a piece of application/process to run.
 app.war -----> Virtual Machine 
 java and Tomcat installed and configured
 
Containerise the following applications 
 app code = app.war + 
 Dependencies = tomcat9 + openjdk11+
 app code = app.ear + 
 dependencies = openjdk11+ + jboss/wildFly 
 app code = app.jar + 
 dependencies = java1.8+ 
 
vertualisation deployments most of the times faces environmental issues/differences
 dev --- application working well in dev
 test --- application working well in test
 prod --- application failing in pod
Containerization Software/Runtime include --> :
 Docker, = over 80% usage 
 Rocket, 
 Pod man, 
 CRI-O, 
 Core-OS,
 Container-D. 
 
Docker: 
 Is a containerization multi-platform software use to; 
 create, build, ship, share and deploy containerize applications 
O.S --> Cross Platform (Docker can be installed in any O.S)
 Docker Can Be Installed on Linux, Windows OS, macOS 
 Desktops as well as servers.
For you to install docker, it all depends on the edition 
Docker is available in 2 Editions:
1) Docker CE: --> Community Edition (Free to use)
2) Docker EE: --> Enterprise Edition (Commercial/Licensed)
 CE+
 ---
 1) Vendor Support = docker.io 
 2) Additional Features like DTR (Docker Trusted Registry),
 3) UCP (Universal Control Plane) GUI.
Docker Desktop (Local Laptops/Desktops) --> 
https://docs.docker.com/engine/install/#desktop
Linux Flavors :
CentOS
Amazon Linux
 Red Hat :
Ubuntu
Debian
Fedora
SUSE Linux …etc.
Officially, Docker CE is not supported for Red Hat.
Install Docker on Ubuntu
###########################
#!/bin/bash
sudo apt update
sudo apt upgrade
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu 
$(lsb_release -cs) stable"
sudo apt update
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker ubuntu
sudo su - ubuntu
OR
#!/bin/bash
sudo hostnamectl set-hostname docker
sudo apt update -y
sudo apt install docker.io -y
sudo service docker start
sudo docker info 
sudo usermod -aG docker ubuntu
sudo su - ubuntu 
======================================
# Amazon Linux
###########################
#!/bin/bash
sudo amazon-linux-extras install docker -y
sudo service docker start
sudo systemctl enable docker
sudo docker run hello-world
sudo systemctl status docker
sudo usermod aG docker ec2-user
sudo su - ec2-user
NB:
Add Regular users to docker group for them to run docker commands/tasks 
sudo usermod -aG docker <username>
