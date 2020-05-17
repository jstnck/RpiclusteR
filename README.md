# RpiclusteR


  The Raspberry Pi is a fun and practical tool for learning to code and building DIY data projects. Since I've been in covid19 isolation, I decided to add two more Raspberry Pi's to my collection and learn about distributed computing. The goal is to use my 3 node cluster to create a platform for future data engineering, data analytics, and IoT projects. 

## This Project:

  This project demonstrates how to set up a Raspberry Pi Spark cluster as a back end for running R projects from a local machine (in this case my laptop).
  - It focuses on installing and configuring Spark on each node. The cluster executes R jobs sent from a local machine and returns the results. 
  - Future projects will analyze data and demonstrate workflows using the RpiclusteR

### R and Spark

  One of the reasons I love R for data analysis is it allows you to quickly run snippets of code and view the results. This allows for fast iteration through a number of different approaches for solving a problem, be it data wranging, statistical analysis, machine learning, or tasks you can do in R 
  - One of the common complaints about R is that it is slow - code can take longer to execute than other languages when performing computations on larger datasets. This limits R as a tool for fast iteration, as you often have to wait over 10 mins (or sometimes much, much longer) for a command to run.
  - While there are many ways to speed up R (see the great DataCamp course [Writing Efficient R Code](https://www.datacamp.com/courses/writing-efficient-r-code)), I decided to see if I could write R code on my laptop, while having my RPi cluster execute the commands. This will (hopefully) speed up execution time, and keep my laptop resources free for the 731 tabs I have open in firefox. 
  - To do this, R uses the sparklyr package to communicate and send jobs to Spark. The dplyr packages from the tidyverse communicates well with SparkSQL, which queries data held in a Spark DataFrame.
  

### Raspberry Pi
  When checking out someone's Raspberry Pi project, one of the most common things you will hear is "this isn't practical or efficient, but here's my cool project".
  - Right now this definitely applies to the RpiclusteR, so  benchmarking and optimizing performace will come next. 



## Tech Stack:
Hardware:
  - Three Raspberry Pi 4B's, connected with a POE switch. 
  - My laptop, connected on the same LAN as the RPis

OS:
  - The RPis are running Ubuntu server 64bit 20.04, my laptop is running Ubuntu Desktop 20.04

Spark:
  - Each node in the cluster has Spark (2.4.5) on YARN installed
  - R will connect to Spark with the spraklyr package

Development:
  - I'm also running Spark on a virtual machine on my laptop for development and testing
  - The VM is running Ubuntu 18.04 using Virtualbox, and is deployed using Vagrant
  
Configuration:
  - The VM and the RPis are configured using Ansible Playbooks

Testing:
  - I am developing an R data analytics project in VS Code, to connect to the Spark cluster using Sparklyr
  - I will also be benchmarking the cluster using the rbenchmark package

### Current Status
  - The cluster is built and all nodes have java, scala, and spark installed
  - The VM is being used to configure spark
  
### Next Steps
  - Set environment variables on VM and RPi nodes
  - Configure manager node to listen for jobs and share work with worker nodes (aka figure out how YARN works)
  - Connect R on my local machine to spark on the RPis with sparklyr



## Credit
I am heavily inspired by many awesome Raspberry Pi youtube channels!
  - [Davy Wybiral](https://www.youtube.com/channel/UC6tqFmkqznYJTzidBerHA8g)
  - [Novaspirit Tech](https://www.youtube.com/channel/UCrjKdwxaQMSV_NDywgKXVmw)
  - [Gary Explains](https://www.youtube.com/channel/UCRjSO-juFtngAeJGJRMdIZw)
  - [Andreas Spiess](https://www.youtube.com/channel/UCu7_D0o48KbfhpEohoP7YSQ)
  - and more! I will do my best to keep adding to this list
  - all mistakes are my own
