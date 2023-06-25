## Zimbra 10 Installation

This Ansible role automates the process of installing Zimbra 10 on a single server running different operating systems.

### Requirements

The server must be a fresh minimal installation of CentOS or Ubuntu. The network configuration should be static and already set up. For Ubuntu, the ufw firewall should be stopped and disabled. For CentOS/RHEL, SELinux should be disabled, and Firewalld should be turned off. Ensure that you have a proper Ansible setup and that there is connectivity from the Ansible server to the Zimbra server.

### Create Role to Install Zimbra

1. Go to the Ansible server and create a directory named `roles` and navigate into the `roles` directory.

   ```shell
   mkdir roles
   cd roles
   ```

2. Create the `ansible-zimbra-single` role using the following command:

   ```shell
   ansible-galaxy init ansible-zimbra-single
   ```

   This will create a directory named `ansible-zimbra-single`, and inside that directory, you will find the structure of the role.

   ```plaintext
   ansible-zimbra-single
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
   ```

   Note: In the repository, you will find all the files required to install Zimbra. Replace the existing files in the `defaults` directory with the provided role files in the repository.

3. Go back to the parent directory where you created the `roles` directory, and create a YAML file named `site.yml` with the following contents to run the roles for installing Zimbra:

   ```shell
   vi site.yml
   ```

   ```yaml
   ---
   - hosts: zimbra
     vars:
       zimbra_timezone: Asia/Kolkata
       zimbra_fqdn: mail.local.com
       zimbra_admin_password: supp0rt
     roles:
       - ansible-zimbra-single
   ```

   Save the file and exit.

Now you can use this configuration to automate the installation of Zimbra 10 using Ansible.