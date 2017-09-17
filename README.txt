Step by Step creating Running Environment
1. Setup Virtualbox and Vagrant on local machine
2. Starting environment - vagrant up
3. Clean env - vagrant destroy -f

# I am using ansible provisioner to setup machines and services
Environment
Automation of the spin-up and installation of a single-machine  architecture. 
OS Used :ubuntu/trusty64 (14.04 LTS)
HAProxy :HAProxy will provide high availability load balancing and proxy server for TCP and HTTP-based applications that spreads requests across multiple servers.
Webserver :NGINX
DB Server :mysql-server
           python-mysqldb
IP Range  :
haproxy.vm.network "private_network", ip: "192.168.50.222"
webapps.vm.network "private_network", ip: "192.168.50.223"
db.vm.network "private_network", ip: "192.168.50.224"
Configuration Management:Ansible

#Install Ansible on Vagrant host using below command
#Playbook to query from YML
Step 1:
haproxy.vm.provision "ansible" do |ansible|
ansible.playbook = "setup-haproxy.yml"
Step 2:
webapps.vm.provision "ansible" do |ansible|
ansible.playbook = "setup-webapps.yml"
Step 3:
db.vm.provision "ansible" do |ansible|
ansible.playbook = "setup-db.yml"

Web Tier:NGINX
DB Server: My Sql
Environment Established:
Step 1 : Download and Installed Vagrant from                        
          www.vagrantup.com/downloads.html  

Step 2 : Check for the vagrant version
Step 3 : Downloaded Oracle Virtual Box(Version 5.1.28 r117968  
         (Qt5.6.2)

Step 4 : Created a New Git Repositery:
Step 5 : Download the Repositery on Local Machine.
Step 6 : Contents of Git Repositery  
         YML Files for HA proxy,DB and Web server
         Uploaded Vagrantfile which will describe the type of  
         machine required for a project, and how to configure 
         and provision these machines using Anisble
         Read me File for step by step Demonstation
         Roles:Task/Templates
         Task are YML Template for step by step start  
         of services
         Templates have config for NGINX and HAproxy
         nginxapp.conf/haproxy_template.cfg

Step 6:  Use command cmd and get inside the directory which  
         is downloaded from the Github and stored on your  
         local machine Spin up command Vagrant up
         It will take approx 1 Hour or less to spin up the   
         Machines