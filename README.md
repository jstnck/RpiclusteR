# RpiclusteR


  My goal is to use my 3-node Raspberry Pi cluster to create data engineering projects, which can then be used as platforms for future data analytics and IoT projects.

## This Project!

  - This project demonstrates how to set up a Raspberry Pi Spark cluster as a back end for running R projects from my laptop
  - It focuses on building and configuring the cluster to perform storage and computation for a user running R scripts from their local machine.
  - Future projects will analyze data and demonstrate workflows using the RpiclusteR


### The tech stack used for the RpiclusteR is:
  - Three Raspberry Pi 4B's, connected with a POE switch. My laptop is connected on the same LAN
  - The RPis are running Ubuntu server 64bit 20.04
  - Each node in the cluster has Spark (2.4.5) on YARN installed
  - I'm also running a node on a virtual machine on my laptop for development and testing
  - The VM is running Ubuntu 18.04 using Virtualbox, and is deployed using Vagrant
  - The VM and the RPis are configured using Ansible Playbooks
  - I am developing an R data analytics project in VS Code, to connect to the Spark cluster using Sparklyr

### Current Status
  - The cluster is built and all nodes have java, scala, and spark installed
  
### Next Steps
  - Set environment variables on VM and RPi nodes
  - Configure manager node to listen for jobs (and figure out how YARN works)
  - Connect R to spark with sparklyr



## Credit
I am heavily inspired by many awesome Raspberry Pi youtube channels!
  - Davy Wybiral https://www.youtube.com/channel/UC6tqFmkqznYJTzidBerHA8g
  - Novaspirit Tech https://www.youtube.com/channel/UCrjKdwxaQMSV_NDywgKXVmw
  - Gary Explains https://www.youtube.com/channel/UCRjSO-juFtngAeJGJRMdIZw
  - Andreas Spiess https://www.youtube.com/channel/UCu7_D0o48KbfhpEohoP7YSQ
  - and more! I will do my best to keep adding to this list
  - all mistakes are my own
