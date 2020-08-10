README


I created a resource group, virtual network, security group, and a Jumpbox VM. The security group and Jumpbox help in securing the internal network. The internal network encompasses Web-1 and Web-2 VMs, running DVWA. Web-1 and Web-2 are accompanied by a backend pool and loadbalancer.

Docker was used to deploy the ansible container on the jumpbox. Ansible is a provisioner which was used to deploy the DVWA website onto Web-1 and Web-2.

The Elk server is on its on virtual network and its running the ELK stack to monitor activity occurring on Web-1 and Web-2.
