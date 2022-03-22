# Elk-Stack-Project1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Elk-Stack-Project1/project diagram.PNG

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  ELk-install.yml
  Filebeat-playbook.yml
  metricbeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting request to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_a load balancers off loading fuctions can help protect against DDos attacks. helps limit the access to your servers by requiring all users to go through a secure jumpbox before accessing the vunrable servers

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_it moniters log files while also fowarding and centralizing log data
- _TODO: What does Metricbeat record?_montiers the services running on your servers and converts it to metric data to be viewed in an output that you set.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function  | IP Address    | Operating System |
|----------|-----------|---------------|------------------|
| Jump Box | Gateway   | 20.25.101.182 | Linux            |
| Web 1    | web server| 10.0.0.6      | Linux            |
| Web 2    | web server| 10.0.0.7      | Linux            |
| ELK-vm-1 | ELK server| 20.109.109.187| Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox provisoner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 172.73.12.120

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_I accessed the ELK VM through my jump box, but more specifically the awesome_grothendieck container. the ip for this machine would be 20.25.101.182

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 172.73.12.120        |
| web 1    | NO                  | 20.25.101.182        |
| web 2    | NO                  | 20.25.101.182        |
| ELK-VM-1 | NO                  | 20.25.101.182        | 

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ you can configure an entire application network no matter where its deployed. Another big advantage is once you have a playbook correct and running you can resuse them to deploy again if needed easily

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... 
- once connected to a docker container runn the following commands:
- nano playbook_name.yml
- write out playbook or copy content from elk-install.txt in this repository
- sudo ansible playbook playbook_name.yml
- vist site http://<ELK.VM.External.IP>:5601/app/kibana
- head to the log data/ docker page and scroll to bottom to the check data button and press it.
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
