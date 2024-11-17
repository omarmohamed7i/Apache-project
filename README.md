# Apache-project

### This Ansible playbook automates the configuration of multiple virtual hosts on an Apache web server, including:

  Creating DocumentRoot directories for each virtual host.
  Configuring virtual hosts with specific settings, including custom log files and authentication.
  Creating private directories under each virtual host and protecting them with password-based authentication.

### Prerequisites:

  Ansible installed on your system.
  An inventory file defining your target hosts.
  SELinux configured to allow HTTPd to listen on port 88.

  ## Usage:

  Clone the repository:
  Bash

  git clone https://github.com/your_username/ansible-virtual-hosts.git


### Edit the inventory file:

  Add your target hosts and their IP addresses.

### Edit the group_vars/all.yml file:

  Customize variables like apache_user, apache_group, and apache_config_dir as needed.

## Run the playbook:

ansible-playbook -i inventory site.yml

#### Role Details:

  tasks/main.yml: Defines the tasks to be executed.
  templates/virtualhost.conf.j2: Jinja2 template for virtual host configuration.
  templates/htaccess.j2: Jinja2 template for .htaccess configuration.
  vars/main.yml: Defines variables specific to the Apache role.

#### Additional Notes:

  SELinux: Ensure SELinux policies are configured to allow necessary access to log files and private directories.
  Password File: Use the htpasswd command to create password files for each virtual host.
  Security: Implement strong password policies and consider using HTTPS to protect sensitive data.
  Testing: Thoroughly test your configurations to ensure they work as expected.

Remember to adapt the playbook to your specific needs and security requirements.
