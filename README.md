# Zimbra_10_Installation
This Ansible role automates the process of installing Zimbra10 on a single server running different operating systems.

**Requirements**

The server must be a fresh minimal installation of CentOS or Ubuntu.
The network configuration should be static and already set up.
For Ubuntu, the ufw firewall should be stopped and disabled. For CentOS/RHEL, SELinux should be disabled, and Firewalld should be turned off.
Ensure that you have a proper Ansible setup and that there is connectivity from the Ansible server to the Zimbra server.

# Create Role to install the Zimbra

1. Go onto the Ansible server and create a directory name roles and move into the roles directory.
   
    mkdir roles
    cd roles

2. Now create your role by name ansible-zimbra-single using below command

   ansible-galaxy init ansible-zimbra-single

 This will create a directory with name anisble-zimbra-single and you can check that the structure of role will be present inside that directory.

  tree anisble-zimbra-single
anisble-zimbra-single
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml

8 directories, 8 files

3. In the repository you will get all the files required to install the zimbra. So, replace the defaults with the provided role files in the     repository.

4. Go back to the directory from where you have created the directory roles and create a yml file as below to run the roles for installing the Zimbra.

vi site.yml 
--- 
- hosts: zimbra
  vars:
    zimbra_timezone: Asia/Kolkata
    zimbra_fqdn: mail.local.com
    zimbra_admin_password: supp0rt
  roles:
    - ansible-zimbra-single
