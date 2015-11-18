# DevOps - TECH TALK - Nagios

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
