## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram.ng.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

![elk-install.yml](elk-install.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? A load balancer protects the performance of the webserver by redirecting the client to the most available server.
 What is the advantage of a jump box?_ A jumpbox enables ssh connection to all over VMs

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the metrics and system files
- _TODO: What does Filebeat watch for?_ files opened and requested
- _TODO: What does Metricbeat record?_ usage of the computer CPU, RAM etc

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|  Jumpbox |  contains ansible     |  10.1.0.4 |               |linux |
|web 3|web server|         10.1.0.7 |        linux|
|web 4| web server|          10.1.0.8|         linux|
| Elk | web server |          10.1.1.4|         linux| 
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My public IP

Machines within the network can only be accessed by the jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? 
What was its IP address?_


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes             | 10.0.0.1 10.0.0.2    |
| web 2         |  no                   | 10.1.0.7                     |
|  web 4        |   no                  |   10.1.0.8                   |
 |elk  |            yes                   |  10.1.1.4|
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_reduces human error . automation of the VM set up

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... install docker.io, Install pip3,Install Docker python module,Use more memory,download and launch a docker elk container
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps output](Images/docker_ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_10.1.0.7,10.1.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ filebeat 

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._ filebeat logs amount of traffic on each file on the server and the return status code. example. taffice data

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the yml_____ file to ansible_____.
- Update the _host ____ file to include... IP address
- Run the playbook, and navigate to VM Machine____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ Elk.yml copy to ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ update host file  and include elk ip address
- _Which URL do you navigate to in order to check that the ELK server is running? 40.83.167.1

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
