I created a Resource Group, Virtual Network, Security Group, and a Jumpbox VM. The Security Group and Jumpbox help in securing the internal network. The internal network encompasses Web-1 and Web-2 VMs, running DVWA. Web-1 and Web-2 are accompanied by a Backend Pool and Load Balancer. The Load Balancer not only provides redundacy as insurance against DoS attacks, it also provides utility as a line of defense since if an attacker was to penetrate the Security Group they arrive at the Jumpbox or Load Balancer, not the sensitive data in the Web boxes. 

Docker was used to deploy the ansible container on the Jumpbox. Ansible is a provisioner which was used to deploy the DVWA website onto Web-1 and Web-2.

The Elk server is on its own virtual network and its running the ELK stack to monitor activity occurring on Web-1 and Web-2.

I can monitor the log activity through kibana 
