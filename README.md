Diagram of the Virtual Network created for this project.x

![](./Diagrams/Elk_Diagram.png)

## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

<!-- _TODO: Enter the playbook file.-->
![](./Ansible/Elk.yml) 

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
# What aspect of security do load balancers protect?
   - Load Balancers are meant to protect the Availability of the website

#What is the advantage of a jump box?
   - The advantage of a jumpbox, espeically a cloud based one, is that it is within the netowrk of your servers so you can connect via private IP 
	and restrict public access to the servers. Additionally you can restrict who connects to the jumpbox.  

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file systems and system metrics.
- What does Filebeat watch for?
   - Filebeat collects, parses and visualizes common log data

- What does Metricbeat record?_
   - Metricbeat records system and service metrics, this can be used to monitor the performance of the server and external services

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    |DVWA host | 10.0.0.5   | Linux            |
| Web-2    |DVWA host | 10.0.0.6   | Linux            |
| Web-3    |DVWA host | 10.0.0.7   | Linux            |
| ELK      | Monitor  | 10.1.0.4   | Linux            | 

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet.
Access to this machine is only allowed from the following IP addresses:
- 98.245.18.195

Machines within the network can only be accessed by ssh from the docker container on the jumbox.
- Which machine did you allow to access your ELK VM?
   - The Elk machine has the public key of the docker container on the jumbox provisioner, 
     therefore it is what is used to access the ELK VM 
- What was its IP address?_
   - 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 98.245.72.194        |
| Web-1    | No                  | 10.0.0.1-254         |
| Web-2    | No                  | 10.0.0.1-254         |
| Web-3    | No                  | 10.0.0.1-254         | 
| Elk      | No                  | 10.0.0.1-254         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because the network admin is able to quickly create new microservices

The playbook implements the following tasks:
<!--#TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.-->
- Installs Docker
- Installs Docker module with python3-pip
- Increases vm memory
- Downloads elk image & sepecifies ports 


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

<!--#[TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)-->

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6
- 10.0.0.7

We have installed the following Beats on these machines:
- Used Installed Filebeat on the Web Server machines (10.0.0.5-7)
   - 
<!--#TODO: Specify which Beats you successfully installed_-->

These Beats allow us to collect the following information from each machine:
<!--- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see.--> 
<!-- E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._-->

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

<!--TODO: Answer the following questions to fill in the blanks:--> 
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._-->
