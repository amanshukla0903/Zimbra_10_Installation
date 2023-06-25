# Zimbra_10_Installation
This Ansible role automates the process of installing Zimbra10 on a single server running different operating systems.

**Requirements**

The server must be a fresh minimal installation of CentOS or Ubuntu.
The network configuration should be static and already set up.
For Ubuntu, the ufw firewall should be stopped and disabled. For CentOS/RHEL, SELinux should be disabled, and Firewalld should be turned off.
Ensure that you have a proper Ansible setup and that there is connectivity from the Ansible server to the Zimbra server.
