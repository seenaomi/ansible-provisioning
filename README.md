Automatic provisioning system based on Ansible and vagrant.
This system can provision designated computers/servers based on selected roles.
<br />


## General project file layout

    /opt/
          |-- proj/
                |-- env/      # Virtualenv
                |-- src/      # project source code

    /var/
          |-- log/
                |-- proj/                       # log directory for project-specific logs
                      |-- django.log            
                |-- {webservice}/
                      |-- proj_error.log        # web service logs, e.g. apache proj_errors.log
                      |-- proj_access.log
          |-- opt/
                |-- proj/                       # Dynamic content directories for media and static files
                      |-- media/
                      |-- proj_static/


## Included Roles


The `vagrant.yml` file has a sample setup for provisioning a VM using vagrant and all the above roles.

Notes on provisioning:
* CentOS 6.6 does not include a firewall. The base role downloads appropriate packages, but the firewall must be set up with `system-config-firewall-tui` over ssh.
* Make sure to enable SSH, HTTP and HTTPS when setting up the firewall!


REFERENCES
* Ansible best practices
* Linux File System Hierarchy document http://www.pathname.com/fhs/pub/fhs-2.3.html
* https://github.com/geerlingguy/ansible-role-apache
* https://github.com/zenzire/ansible-bootstrap-ubuntu
