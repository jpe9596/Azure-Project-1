Project Elk consists of building out a cloud network in Azure for a web appliction and setting up an ELK stack server to monitor network traffic. The deployed and configured ELK stack utillized Filebeat and Metricbeat data collection tools for log analysis.

Initially created a virtual network, deployed a jump box and installed Docker to spin up an Ansible container. Utilizing an ansible playbook, provisioned a DVWA web application onto two VMs.

Cloud network included virtual networks, virtual machines, network security groups, and load balancers.

ELK monitoring to detect: Log in attempts, file changes, password modifications, changes to sensitive files, adding new users, etc. 

I created a Resource Group, Virtual Network, Security Group, and a Jumpbox VM. The Security Group and Jumpbox help in securing the internal network. The internal network encompasses Web-1 and Web-2 VMs, running DVWA. Web-1 and Web-2 are accompanied by a Backend Pool and Load Balancer. The Load Balancer not only provides redundacy and efficient scalability as insurance against DoS attacks, it also provides utility as a line of defense since if an attacker was to penetrate the Security Group they arrive at the Jumpbox or Load Balancer, not the sensitive data in the Web boxes. 

Security Group rule configurations: First, I created an inbound rule allowing ssh-ing into the Jumpbox from my computer, setting its priority level to 500. I added an inbound security rule allowing ssh from my Jumpbox private IP to the internal network, giving it a priority value of 501. I ran ssh-keygen within my Jumpbox and added the public key to Web-1 and Web-2. Next, I allowed for web traffic through port 80 from my computer's public IP by created a Security Group inbound rule with a priority value of 510. Finally, I created an inbound rule providing the Load Balancer access to the network, with a priority value of 65001.

Docker was used to deploy the ansible container on the Jumpbox. Ansible is a provisioner which was used to deploy the DVWA website onto Web-1 and Web-2.

The Elk server is on its own virtual network and its running the ELK stack to monitor activity occurring on Web-1 and Web-2.

I can monitor the log activity through kibana.
