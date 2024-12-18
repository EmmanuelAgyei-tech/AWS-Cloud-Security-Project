This project focuses on designing and implementing a secure cloud infrastructure using Amazon Web Services (AWS). The goal is to securely host a web server and database server while applying network security best practices. Key tasks include:
Subnet creation for isolating resources.
Configuring traffic rules with Security Groups.
Deploying a secure LAMP stack on an Ubuntu instance.
Hardening SSH access for enhanced server security.
Skills Demonstrated:
AWS Services: EC2, Subnets, Security Groups.
Linux System Administration: SSH configuration, key-based authentication.
Network Security: Traffic control and server hardening.
LAMP Stack Deployment: Apache, MySQL, PHP installation and configuration.
Project Steps:
Goal: To create one public subnet for the web server and one private subnet for the database server.
Steps:
Configured a public subnet for the web server.
Configured a private subnet for the database server.
Outcome: Both subnets were successfully created to isolate the web and database resources
2. Launching Instances
Goal: Launch Ubuntu servers in the appropriate subnets.
Steps:
Launched an Ubuntu EC2 instance in the public subnet for the web server.
Launched an Ubuntu EC2 instance in the private subnet for the database server.
Outcome: Instances were successfully launched and connected.
3. Configuring Traffic Rules
Goal: Allow only required traffic to improve security.
Steps:
Allowed inbound SSH traffic to the web server.
Configured inbound HTTP/HTTPS traffic for the web server.
Allowed ICMP (ping) traffic from the web server to the database server.
Outcome: Traffic rules were successfully configured using AWS Security Groups.
4. LAMP Stack Deployment
Goal: Install and configure a LAMP stack (Linux, Apache, MySQL, PHP) on the web server.
Steps:
Installed Apache, MySQL, and PHP using the following commands:
sudo apt update  
sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y  
Configured Apache to display the default "It Works" page.
Outcome: LAMP stack was successfully installed and verified.
 SSH Configuration
Goal: Harden server access by enforcing public key authentication and disabling password-based login.
Steps:
Edited the SSH configuration file:
sudo nano /etc/ssh/sshd_config  
Disabled password authentication:
PasswordAuthentication no  
Enabled public key authentication:
PubkeyAuthentication yes  
Allowed root login with public key authentication:
PermitRootLogin yes  
Restarted the SSH service:
sudo systemctl restart sshd  
Added the public key to the root user’s authorized_keys file:
sudo mkdir -p /root/.ssh  
sudo nano /root/.ssh/authorized_keys  
sudo chmod 700 /root/.ssh  
sudo chmod 600 /root/.ssh/authorized_keys  
Tested root login via public key:
ssh -i /path/to/private-key.pem root@<server-ip>  
Outcome: SSH hardening was successfully completed, ensuring secure access to the server.
