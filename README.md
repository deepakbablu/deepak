# Ansible-vagrant-3-tier-architecture

Here We have used vagrant and ansible to automate our build process. where vagrant is used for creation of Infracture and Ansible is used as configuration management tool. For deployment we can use kubernet. Where we will use cluster IP and node port our application. We will give cluster ip to DB port and Node port to application so that it will be access from internet. 

#### Requirements

- Vagrant 
- Ansible 
# source file to write vagrant is: https://developer.hashicorp.com/vagrant/docs/providers

#### To run playbook

    
    $ cd assigment
    $ vagrant up

#### Landing page

    http://localhost:9090/
    http://localhost:9090/db   
# We can use local host or 127.0.0.1 ip address


