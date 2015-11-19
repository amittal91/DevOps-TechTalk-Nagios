# DevOps - TECH TALK - Nagios

###Team
* Apoorv Mittal - amittal
* Ashwin Oke    - aboke
* Nikhil Dalmia - nkdalmia
* Nisarg Gandhi - ndgandh2

###What is Nagios?

Nagios is a **monitoring tool** which monitors your entire IT infrastructure to ensure systems, applications, services, and business processes are functioning properly. In the event of a failure, Nagios can alert technical staff of the problem, allowing them to begin remediation processes before outages affect business processes, end-users, or customers. **Nagios Core** serves as the basic event scheduler, event processor, and alert manager for elements that are monitored. It features several APIs that are used to extend its capabilities to perform additional tasks, is implemented as a daemon written in C for performance reasons, & is designed to run natively on Linux/*nix systems.

Some of the many features of Nagios Core include:

* Monitoring of network services (SMTP, POP3, HTTP, NNTP, PING, etc.)
* Monitoring of host resources (processor load, disk usage, etc.)
* Simple plugin design that allows users to easily develop their own service checks
* Parallelized service checks
* Ability to define network host hierarchy using "parent" hosts, allowing detection of and distinction between hosts that are down and those that are unreachable
* Contact notifications when service or host problems occur and get resolved (via email, pager, or user-defined method)
* Ability to define event handlers to be run during service or host events for proactive problem resolution
* Automatic log file rotation
* Support for implementing redundant monitoring hosts
* Optional web interface for viewing current network status, notification and problem history, log file, etc.

###Setup Instructions

To set up nagios, two digitalocean droplets were provisioned - one acting as a monitoring server and the other as the host which is supposed to be monitored remotely.
In brief, to setup nagios you have to do the following steps
<br><br>*1. Server*
* Install Linux, Apache, MySQL, PHP (LAMP) stack
* Install *nagios core*
* Install Nagios Plugins
* Install NRPE - Nagios Remote Plugin Executor

A detailed tutorial about setup can be found [here](https://www.digitalocean.com/community/tutorials/how-to-install-nagios-4-and-monitor-your-servers-on-ubuntu-14-04)

*2. Remote Host*
* Install linux-nrpe-agent
* Allow the nagios-Server to access the remote host

A detailed tutorial about setup can be found [here](https://assets.nagios.com/downloads/nagiosxi/docs/Installing_The_XI_Linux_Agent.pdf)

*3. Setting up email notification*
* Install POSTFIX
* Install Heirloom-MailX

A detailed tutorial about setup can be found [here](http://www.telnetport25.com/2012/02/configuring-e-mail-notifications-in-nagios-core/)

*4 Make changes in configuration files*
* Replace /usr/local/nagios/etc/objects/command.cfg with commands.cfg provided [here](https://github.com/amittal91/DevOps-TechTalk-Nagios/tree/master/Config-Server)
* Add (NagiosRemoteHost2.cfg)[https://github.com/amittal91/DevOps-TechTalk-Nagios/tree/master/Config-Server] to /usr/local/nagios/etc/objects/ . Change the IP address in the file to your remote host's IP
* Add your contact information in /usr/local/nagios/etc/objects/contacts.cfg

The configuration files needed to be replaced in the server and host have been provided in the repo.

###Advantages

* *Comprehensive Monitoring in a Single Tool*: Monitoring of all mission-critical infrastructure
components – including applications, services, operating systems, network protocols, systems
metrics, and network infrastructure. 

* *Consolidated, Central Visibility*: Provides central view of your entire IT operations network
and business processes. Central, aggregated view of multiple monitoring server instances
improves visibility and shortens problem reaction times for IT operations staff.

* *Scalability*: Monitor thousands of devices with a single monitoring server. Distributed monitoring architectures allow for monitoring 100,000+ node environments.

###Disadvantages

* The user interface is sloppy. Probably because it's very old.
* Documentation not updated. The documentation given on the website refers to Ubuntu 6.x and 7.x

