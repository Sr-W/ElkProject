# ElkProject

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Ihttps://drive.google.com/file/d/1IGVeEpffeZ5KBeb0CJePYOzPAM8C5OUZ/view?usp=sharing)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YML file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file. Ansibleplaybook.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly stable and redundant, in addition to restricting DOS to the network.
- _TODO: What aspect of security do load balancers protect?  A load balancer receives traffic from the internet and distributes the traffic across several servers within the load balancer network. A jump box is a system on a network used to access and manage devices in a separate security zone.

 What is the advantage of a jump box? The advantage of a jump box 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Data and system User.
- _TODO: What does Filebeat watch for? Collect information about the file system.
- _TODO: What does Metricbeat record? Collects system metrics such as uptime.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
JUMPBOX | REDTEAMVM | DYNAMIC IP; 12.345.567.89 | LINUX
DVWA1 | WEB APPLICATION | DYNAMIC IP; 12.345.567.89/ PRIVATE IP; 10.0.0.1 | LINUX
DVAW2 | WEB APPLICATION | DYNAMIC IP; 12.345.567.89/ PRIVATE IP; 10.0.0.1 | LINUX
ELK SERVER | SECURITY WEB APPLICATION DATABASE| DYNAMIC IP; 12.345.567.89 | LINUX

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the ELK SERVER machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses PUBLIC IP ADDRESSES TO DVWA 1&2.

Machines within the network can only be accessed by THE JUMPBOX.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? PERSONAL IP ADDRESS.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box     | Yes          |  PERSONAL IP ADDRESS         |
|  DVWA 1      |   NO      |    PRIVATE IP ADDRESS               |        
| DVWA 2      |   NO      |    PRIVATE IP ADDRESS               |
|ELK SERVER |   YES   |  PERSONAL IP ADDRESS      |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because…
- _TODO: What is the main advantage of automating configuration with Ansible? Ansible is fast and performs all functions over SSH and doesn't require agent installation. The main advantage is Ansible can be run from the command line without the use of configuration files for simple tasks.



The playbook implements the following tasks:
CREATED A NEW VM CALLED ELK
DOWNLOAD AND CONFIGURE THE CONTAINER 
LAUNCH AND EXPOSE THE CONTAINER 
IMPLEMENT IDENTITY AND ACCESS MANAGEMENT

- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
Create a new VM. Deploy a new VM into the network. 
This VM will host the ELK server. 
Download and configure the container. 
Download and configure the elk-docker container onto this new VM. 
Launch and expose the container. 
Launch the elk-docker container to start the ELK server.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: DVWA 1: 10.0.0.10 DVWA2: 10.0.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed FILE AND METRIC BEATS.

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.

FILEBEAT COLLECTS DATA FROM THE FILESYSTEM AND MONITORS LOGS OF EVENTS. METRICBEATS COLLECTS METRIC DATA FROM THE FILE SYSTEM SUCH AS UPTIME FROM THE SERVER.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the DEBIAN INSTALLATION FILE TO PLAYBOOK.YML.
- Update the HOST file to include DVWA PRIVATE IP AND ELK SERVER IP.
- Run the playbook, and navigate to CURL LOCALHOST/SETUP.PHP  to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:
- _Which file is the playbook? FILEBEAT-PLAYBOOK.YML & METRICBEAT-PLAYBOOK.YML

Where do you copy it? /ETC/ANSIBLE/

Which file do you update to make Ansible run the playbook on a specific machine? HOST FILE

How do I specify which machine to install the ELK server on versus which to install Filebeat on? FILEBEAT.YML

Which URL do you navigate to in order to check that the ELK server is running? HTTP://ELKSERVERIP:5601

As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc. 
NANO HOSTS
NANO +1106 FILEBEAT.YML
ANSIBLE-PLAYBOOK FILEBEAT-PLAYBOOK.YML
ANSIBLE-PLAYBOOK METRICBEAT-PLAYBOOK.YML
