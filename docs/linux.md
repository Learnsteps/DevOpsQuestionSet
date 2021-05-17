# Linux Question Set

**What does /proc file system contains?**

It contains the information of everything running in system and other resource consumption details. 


**What does free command do?**

Free command show information about memory in you system.

**How to make a new directory**

You can use mkdir commmand. 


**How can you see the process consuming most resources?**

You can use the top command.


**How to get free memory?**

***free -m***


**How to get dics space usage?**

***df -h*** [-h for human readable format]


**How to create an empty file?**

***touch filename***


**Where are the config files of most servers stored?**

Configs can generally be found in /etc. But is not mandatory you can override to configs from any place.


**Difference between TCP and UDP?**

**TCP:** Also known as Transmission control protocol makes sure that the connection  established between two hosts is reliable and also takes care of the orders in which packets will receive and retry if the packet delivery fails. To make the connection it also does a three way handshake to establish proper connection which also makes it slower than UDP. Reliability is added by acknowledgements and retries that TCP attempts to fulfil. 
UDP: In contrast User Datagram protocol doesn't take care of any of these, it just sends the data and forget about it. It is fast and unreliable. 


**Is IP a reliable protocol?**

No, Internet protocol is best effort delivery, it does ensure your packet will reach. Adding TCP with IP makes it reliable.


**What makes TCP/IP a reliable protocol?**

Features like retransmission of packet when it is lost and inorder delivery of packets and acknowledgements makes **TCP/IP** a reliable protocol.


**What is a Three way handshake?**

Three way handshake is a mechanism by which TCP establishes a connection with other computers. By this the client and server are aware of some basic information that is needed for data transfer.
Here are the exact steps:

1. A client node sends a **SYN** data packet to a server on the same or an external network. This packet is to ask if the server is open for new connections.

2. The server must have open ports that can accept and initiate connections. When the server receives the **SYN** packet from the client, it responds and returns a confirmation **SYN/ACK** packet.

3. The client receives the **SYN/ACK** from the server and responds with an **ACK** packet.

These are the three steps in a three way handshake. 


**What does shebang tell? [#!/bin/bash]**

Shebang tells which interpreter path to use while running the script. 


**How to check the connection between two machines?**

It checks the connection whether anything is running on that port. You can test on the localhost also by using
***telnet host port.*** 


**How to see what all ports processes are running?**

***netstat -pln*** [p for process ID, L for listening port since program is listening and n for numerical address instead of host]


**How to see the last updated file in a directory?**

You can do ***ls -ltr*** and the files are sorted by time. 


**What do you mean by load average that you see?**

Load average is the average number of tasks that are waiting in the queue for the CPU time.


**What does the 3 numbers in load average specify?**

First number is the last one min average, second is 5 min average and third one is 15 min average. 


**What is OOM?**

OOM is Out of Memory Error. You get this error when a program needs memory and there is no free memory to allocate to it. 


**What is isolation of resources and how you can accomplish it?**

By isolation we mean that we want to isolate one entity from the other, this entity can be a resource like memory, cpu or processes. You can implement it in Linux using an unshare command. 


**What are containers?**

Containers are isolation that helps you in running a process in its own namespace with proper restrictions on resources that it can use. This helps you in better utilization of the resources and it also helps in keeping one process not affected from the other process. 


**What is a socket?**

Socket is a combination of port + ip + protocol. Sockets allow communication between two processes on the same or different hosts that are connected by internet. 


**How many IPS are there in 10.28.0.0/16 CIDR?**

This will be 2^32-16 IP which is 2^16 = 65536


**What is a reverse proxy?**

In reverse proxy, the client makes requests to the proxy and the proxy internally can make requests to multiple servers configured and return the response to the client. In this case the reverse proxy is protecting the original servers by not allowing the clients to know about them. In this case the client thinks that all the requests are served by the reverse proxy but in behind there can be many servers running and returning the resource you need. Examples of Reverse Proxy are - Nginx, HAProxy.


**What is a forward proxy?**

Forward proxy can be used to control and can imply restriction on  the traffic from the group of clients. For example if you want to restrict any site from your organization you can enable a forward proxy and then you will have to put restrictions on one central place. Example of forward proxy is squid proxy 


**What is DNS load balancing?**

DNS load balancing is used to allow the traffic to be distributed to different servers with the help of DNS servers. In this the DNS query resolves to multiple IP addresses in random order thus distributing the traffic. 
It is done by resolving a DNS to multiple IP addresses, for this you make these entries a DNS server that this DNS should resolve to these IPs.


**How many Root DNS servers are there in the world?**

There are a total of 13 Root server IPs in the world. There are multiple servers behind these ips and they use any cast for this. 


**Why are there only 13 root nameservers?**

The DNS packet is 512 Bytes[Limited at the time of DNS infrastructure decisions], with each IP address having 32 bytes for 13 total data is 416 bytes. 96 bytes are left for other data or IP to be added in future. 


**Why does DNS use UDP?**

It uses UDP because it is fast and these packets are small. We need DNS resolution to be fast. 


**Can DNS work on TCP?**

Yes it can work on TCP also but it will be slow due to the 3 way handshake.


**What does the /etc/resolv.conf file contain?**

It contains the configuration of the nameservers that our machine will query to and other options like timeout and retries. 


**What are Cgroups?**

Cgroups are linux kernel features which give functionality to restrict the amount of resources that can be used by any process. These resources can be CPU, memory, IO, network bandwidth etc.


**What are runlevels?**

Runlevels are the modes in which your system will boot in. There are 7 runlevels from 0-6
0: HALT

1. Single User No network
2. Multiple User No network
3. MultiUser networking
4. User defined, Generally not used. 
5. Most of the desktop displays with networking.
6. Reboot


**How to create a file and its recurring directory like /etc/test/innertest/file**

***mkdir -p***


**What are inodes?**

Inodes are the data structure that keeps all the metadata about any file. You can see inode numbers using ***ls -i***


**What is NAT?**

NAT (Network Address translator) is generally used when you want to hide one side of the network and show it as a single IP. NAT keeps a connection table so that it can forward the returning traffic to the private location. NAT makes changes to either source or the destination address in headers and then forwards the packet.


**Where do we use NAT?**

We use NAT where we want the world to see all of our machines under one IP address because of cases like whitelisting to particular resources etc. All you machine’s traffic goes through NAT to the world with the NAT box ips so they can identify that traffic as yours. 


**What type of NATs are there?**

**SNAT:** 

In this type of NAT, the source IP of the packet changes and then passes it to the i	interface. In this case, the destination will not be able to see who actually created the requests. SNAT allows hosts inside to connect to particular host outside.
All the hosts behind the SNAT are identified as one entity. This helps in scenarios where you want the third parties to whitelist your IP so that they can identify you
 
**DNAT:**

These are the NATs where destination IPs are changed in headers and then passed to the interface. DNAT allows hosts from outside to connect to a particular host inside.
This can be used in the example where you want to host it something locally with private ip and want your NAT box to forward to this host whenever someone tries to contact to NAT IP


**What do you mean by ssl offloading?**

SSL offloading is  the processing of getting the data from the encrypted traffic which is sent using https using ssl. To read more about SSL and how it works you can read about public key encryption. 


**How to check your distribution and version of you os?**

***lsb_release -a***


**How to check kernel version?**

***uname -a***


**How to count all the opened files by os?**

***lsof | wc -l***


**How to figure out process ID running with name apache?**

***ps -ef| grep apache***


**How to kill process with process ID 4?**

***kill -9 4***


**How to check the uptime of your machine?**

You can see it by typing the command w.


**What is the below permission specified? ***-rw-rw-r—*****

This means User that owns it can read and write but not execute, groups that own it read and write but cannot execute and others can only read it.


**What does d say here in permissions? ***drwx------*****

It notifies that it is a directory.


**How to continuously keep a look at the command and say you want to run it every 2 seconds?**

***watch -n2 command***


**How does DNS resolution happen?**

Whenever there is a request to resolve the dns below are the following steps that are taken in sequence. 

1. Checks the hosts file for any entry for that hostname
2. Check the local dns cache for any entry
3. Next it is checked if the DNS is present with your internet provider. 
4. If not, root servers are contacted. 
5. Root servers then tell you about the next server to look into for the dns.Root servers know all the details about the TLDs i.e. top level domains like .com, .in etc. It may not know about google.com but it will know .com might have that information so it returns that. 
6. Next .com is queried if google.com is with it or not. If not .com will keep the information of the nameservers which keeps the information about google.com and return them. 
7. Those servers are then queried to get the google.com mapped to an ip address. 


**How can you make a request using a terminal?**

You can use curl to make a request for something like this. ***curl host:port/resource***


**Which process has Process ID 1?**

Init process has process id 1. It is the first process that is launched after the boot process.


**What is the normal size of a packet in a network?**

Standard ethernet frame is 1518 bytes in size.


**What are jumbo frames?**

Jumbo frames are ethernet frames that are bigger than 1518 bytes. 


**What is swap memory?**

Swap memory is a way to increase virtual memory available to the host. What happens is it creates a swap partition and uses it along with RAM. Whenever RAM is full and a new process needs to be executed [Page Fault], the kernel takes a few pages out of the RAM and puts it in swap memory and uses the RAM for the next process. Once it needs the swapped out page back it can read from the swap space and put it back in memory. 


**What is a softlink?**

Soft Links are symbolic links to a file or folder in the linux system. It actually is nothing but a reference to the exact object. You can create soft links using these commands
***ln -s source[file_to_link] destination[link]***


**What is the port used by SSH?**

22


**What is the port used by DNS?**

53


**How can you get the number of threads spawned by process id 10?**

You can see the content of file ***/proc/10/status***
You can see a like num_threads that tells you about the number of threads for that process. 


**Where can you find syslogs?**

***/var/log/syslog***


**What is systemd?**

Systemd is a system and service manager for linux systems. It is the first process to come up after a successful boot process. Systemd takes care of all the services that need to be started after boot. It actually replaces the old generation init system process. 
It has few advantages over older init like it can launch processes in parallel, you can have post and pre scripts and optional scripts. It also has components like journald which takes care of logging. 


**What is journald?**

Journald is a service in systemd which collects aggregates and provides functionality to view those logs. 


**Where can you see the auth logs in the linux system ?**

This file logs all the events related to authentication and authorization. 
***/var/log/auth.log***


**What are crontabs?**

Crontab is a command used to edit the commands table that is run by cron. Crons are the commands that you want to run after a particular interval or a particular schedule. 


**How to run a script 5th minutes every hour?**

This is the format used to represent crontab * * * * * . First asterisk is minute, second is hour, third is day of month, fourth is year and fifth is day of week. Also there are 4 standard commands * for any value, ‘,’ for value list separator, ‘-’ for range of values and ‘/’ for step values. 
Below is the answer to the question. 

5 * * * * command. Read about the other asterisk as well. 


**What are the standard file descriptors?**

The standard file descriptor are Stdin, stdout and stderr


**How to write “Hello” to a file without opening it?**

***echo “Hello” >> filename***


**What is /dev/null?**

It is a special file in linux also called a null device. It can act as a blackhole means anything written to it is discarded instantly. It only returns EOF [end of file] when read from it. 


**What are lightweight processes in linux?**

Light weight processes are also called threads. 


**What is the difference between a thread and a process?**
Threads are lighter than process. Process has its own heap memory call stack and program counter while threads only have call stack and program counter they share the memory heap from the process to which it is spawned. 


**How can you see if IP forwarding is enabled or not?**

***sysctl net.ipv4.ip_forward*** or you can read the content of the file ***/proc/sys/net/ipv4/ip_forward***


**How to replace a few characters in file without opening it?**

***sed -i 's/old-text/new-text/g' filename***


**How to trace the route a packet is taking to reach an IP?**

You can use the traceroute utility. traceroute ip command will do it for you. 


**How to change the owner of a file?**

***chown user:group filename***


**What is nohup?**

It is used to run any command as a daemon or background process.It ignores the HUP signal. 


**How to see the top 10 lines of a file?**

***head -n 10 filename***


**How to see the Bottom 10 lines of a file?**

***tail -n 10 filename***


**How to count the number of lines that are there in a file?**

***cat filename| wc -l***


**How to see the directory path you are in?**

***pwd***


**What are daemons?**

Daemons are process that keeps running in background. These process get restarted by itself if killed or terminated. In linux these process are named as **processd** like **initd**, **systemd**, **journald** etc.


**How can you see the commands previously ran for that user?**

***history***


**How to list all mounted devices?**

***mount -l***


**How to see the status code of the last command you executed?**

To see the last command executed you try this command  ***`$?`. Note:*** This is not a printing error


**How to see all the environment variables?**

***export***


**How to set a new environment variable?**

***export name=value*** . This will temporarily save the env variable. If you want to use env variable whenever you launch shell you can put in your bash.rc or bash_profile.rc files. 


**How to see the number of CPUs?**

***nproc***


**What are huge pages?**

Huge pages are the pages that are larger than the normal convention of the linux system which is 4KB by default. You can see it by getconf PAGESIZE. Huge pages can vary from 2MB to 256 MB. It also depends on the kernel version. 


**What do you mean by loopback ip?**

Its localhost ip which is 127.0.0.1


**How to list all the corn tabs and how to edit?**

To list all cron tabs you can use ***crontab -l*** and to edit them you can use ***crontab -e***


**How to run a program as a background task?**

You can use ***nohup*** or ***append*** & at the end of command to run the program. 


**How to list tasks running in the background?**

You can use the ***`jobs`*** command to do that.
Try opening a file to exit and then press ctrl+z. This will put the process in the background now when you types job you will be able to see this process. 


**How to bring the background task to foreground?**

You can use 
***`fg %n`***
command to get the task from background to terminal. N is the task number which you get when you run bg.  


**What command do you use to see the boot messages?**

***dmesg*** will show all the boot messages. 


**How to change the nameserver you want your machine to query to while resolving dns?**

You can change it by editing /etc/resolv.conf file and adding your nameservers like this 
***nameserver ip1***
***nameserver ip2***


**What do you mean by CPU intensive process?**

CPU intensive processes are those which need a lot of CPU time for the work that they are doing. CPU intensive tasks are calculations like generating prime numbers etc.


**What do you mean by the IO intensive process?**

These are the processes that depend a lot on IO. These include read write from disk or buffer network calls etc. 


**How to list processes which are consuming the most CPU?**

***ps aux| awk '{print $3, $2, $11}'*** | head -n 15


**Which file to check for if the user exists or not?**

***/etc/passwd***


**How to stream the content of a file which is being written continuously?**

***tail -f filename***


**What are iptables?**

Iptables is a utility that is used to set, maintain and inspect the tables for IP packet filter rules in linux kernel


**How to list all iptables rules?**

***iptables -L***


**What is the name of a utility to take care of log rotation?**

***logrotated***


**How to check your file system for any errors?**

***fsck***


**How can you block all the packets coming from a particular IP?**

***iptables -A INPUT -s ipaddress -j DROP***


**How to see all the packets going to a particular IP?**

You can use tcpdump utility. These commands will help you to see those packets. 
***tcpdump -i eth0 src ipaddress***


**What is a TCP dump?**

Tcpdump is a tool to see the network packets and apply filters to those. You can also save the capture and see it later. It is widely used for packet analysis. 


**What happens when you type init 6?**

***System reboot***


**How to see all the logs after last boot in systemd?**

***journalctl -b***


**Which port https works on?**

***443***


**What is a sticky bit?**

When you set the sticky bit only the owner of the file can delete it. 


**Do you know about **“at”**?**

With **“at”** you can schedule a task but it will run only once. 


**What is cloud init?**

Cloud init is the command that runs and bootstrap the machine in cloud environments. Cloud init can run any bash commands. Generally these are used to provision the machines when they come up. So whenever you launch a machine in any cloud provider, they give you the option to run a cloud init script. 


**What are unit files?**

Unit file is a systemd file with which you can manage any particular service. Once you create this file for any commands you will be able to use systemd commands with it like sysctl service restart etc. 


**What is runc ?**

Runc is a component of containers which takes care of creating the containers. It does cgroups, unshare and other operations needed to create a container.


**What are shim containers?**

When you try to launch a container, the flow is containerd asks containerd-shim to launch container which calls runc to create container and then exits leaving a few of the things like file descriptors so that container can pass essential signals to containerd-shim. 
Its main purpose is to pass the important signals to the containerd.


**What do you know about CNI is kubernetes?**

The Container Network Interface (CNI) is a library definition, and a set of tools under the umbrella of the Cloud Native Computing Foundation (CNCF)project. 
CNI is an interface between network providers and kubernetes networking. Few of the CNI are callico, cillium, kube-router etc. 


**What do you know about OCI?**

OCI or open container initiative is  a foundation to design the open standard for containers. The project is to focus on developing standard interfaces which if someone follows can replace docker in kubernetes or other orchestrators  with some other container implementation which follows the same standards.  Currently it has two specifications, runtime specification and image specification.


**Two containers in one pod can talk to each other with what ip?**

***127.0.0.1 or localhost. For Example if a container  is running on port 8080 then other container can  access it using  localhost:8080 or 127.0.0.1:8080***


**What is a veth pair?**

Veth pair is just like a network wire. It is two virtual ethernet interfaces. It is used to connect two devices like bridge to bridge or bridge to container. It is done by placing one end of the veth pair in the container's namespace and the other in the bridge. 


**What do you mean by VPC peering?**

VPC peering is connecting two VPC so that machines in one VPC can access the machines in another VPC like a private network. One thing that you have to keep in mind is that their cidr should not overlap. 


**What do you understand by IAAC?**

Infrastructure as a code is a process by which you define your infrastructure as a definition files in code using one or the other way. It is a process to make the management of infrastructure easy. The main benefit of IAAC comes when you define everything using code and put it in VCS(Version Control System like git). It becomes very easy to track changes in the infrastructure.


**According to you what are the important components that every software should have?**

Important components can be logging, monitoring, alerting, exception reporting, continuous integration, test cases and documentation. These are few important components that any software should have. You can also read about 12 factor applications. It contains standards that you can follow. . 


**How much should an application log?**

When you talk about logging in application you have to keep this in mind that if you log too much you application will be busy most of the time logging stuff. If it is too less then you may miss small errors that should be caught by looking at logs. Thus, the amount of logging is very important. There are some default log levels that are supported by most of the languages and frameworks. These are default, debug, info, error, warning and critical. In general you log level should be error but should be dynamically configurable so that if you see problems you can change the log level to debug and see the logs. Changing the log levels dynamically is tough to implement but it is a great feature to have. 


**Which port ping works on?** 

***22***


**What is the maximum size any filename can have in linux?**

***255 characters***


**How to see what system calls are being executed by a process?**

strace utility can be used for the same


**What is a nice value of a process?**

Nice command is used to change the niceness of the process, a nice range lies between -20 to 19. Nice add priority to the process execution. Nice is priority by user and priority is by kernel. PR[Priority] = 20 + NI [NICE]. So with nice you can actually ask the kernel to process your tasks before a few of the lower priority kernel assigned tasks. 


**What is redirection in linux?**

Redirection is a way to change the input, output and error standard devices. 


**What types of redirections are there?**

There are three types of redirection: 
1. Input redirection
2. Output redirection
3. Error redirection


**How to see if the DNS is getting resolved or not?**

You can use ***dig*** or ***nslookup commands***. In dig you have to look for the answer section. In nslookup you can look for the address section.  


**How to see which nameservers are used for dns resolution?**

You can use ***dig +trace*** to get the trace of all the nameserver that are getting called in resolution


**You have a very huge file which command will you use to see the file content?**

***less** utility can be used for this purpose. 


**What is the difference between > and >> operator?**

‘>’ operator is used for writing files from the start. 
‘>>’ appends to the file. 


**What happens when you type this command on a file with one line?  Cat filename> filename**

It will be an empty file. This will happen because when you use > you file is opened for writing. And a descriptor will be returned. Another descriptor is from cat command which is used to read the file. When you open a file it will be empty so you write nothing to the opened file descriptor.  


**What happens when you do cat filename>> filename?**

It will be an infinite loop in which your file is appended with a test in each loop. A file descriptor will keep writing and another will keep reading to the same file and writing it back so it will be an infinite loop. 


**What does home directory contain?**

Home directory contains all the users information that is there in the system like keys. 


**You have to give ssh permission to a user, you have his public key how will you do it?**

You can add the public key in ***.ssh/authorized_keys** and it will give the user access.


**What does the known_hosts file do?**

It contains the signature of the hosts that have accessed it. 


**What do you know about CAP theorem?**

CAP theorem states that among Consistency, Availability and Partitioning it is only possible to get two of them at a time. It can be kept in mind when designing a very  large system. In large scale distributed databases which are partitioned you can only achieve either consistency or availability. 


**How to generate ssh keys?**

You can use ***ssh-keygen*** utility to do it. 


**What permission should a private key have?**

***400***


**You have proper permissions, how can you switch to a particular user?**

***sudo su -l username**


**How can you execute the last command that was run in linux?**

***`!!`*** will execute the last command


**Without opening a file you have to create a file and write “hello” in it. How will you do it?**

***echo “hello” > filename***


**How to see the IP of a machine?**

`ip a` or `ifconfig` in older systems. 


**What are in-memory databases?**

In memory databases are the ones where which keeps its data in memory which makes them very fast. Few examples are redis, memcache etc. 


**What do you mean by scalability?**

Scalability means that your system should be able to cope up with the growing use without any change in architecture just by adding a few extra machines. Creating scalable systems is very tough. 


**What do you mean by reliability?**

Reliability can be expressed as a system that can work what it is intended to do in harsh circumstances. 


**What is VVV in big data?**

Velocity, Variety and Volume


**What are microservices?**

Microservice is an architecture in which you try to break up your whole software into smaller systems and let them do the task that is assigned to them. There are a lot of advantages that come with it. Few of them are: 

1. Faster and smaller deployments. 
2. Small changes can be made without thinking of the whole system. 
3. Smaller teams can handle their services with ease. 


**What do you mean by monolith?**

Monoliths are a big piece of software. They are huge code bases. You can say monolith is the opposite of microservice. Some of the advantages of monolith are :-

1. Testing is easier than microservices
2. Managing monolith is easier than microservices


**What do you mean by high availability?**

High availability means that even a few components of your system goes down your system should be working fine. For example there are 5 instances of your service running, even if your 2 instances go down your service will still be working. This is high availability. 


**What are stateless applications?**

Stateless applications are the one which don’t save any data locally on their servers. This is very important if you want your service to be horizontally scalable. 
Imagine if you are saving some data on disk you can not launch another instance and run the same service on that as it may not be aware of the data on the first machine and that will cause problems. In these scenarios you generally build stateless service and save the data to remote DB. 


**What is horizontal scaling?**

Horizontal Scaling means you can scale your service by running more instances of your service on different locations and don’t need to make any changes to it. 


**What is the difference between scaling out and scaling up?**

Scaling out simply means horizontal scaling in which you launch more instances of the same machine while in scaling up you do vertical upgrades of the machines. 


**What is session stickiness?**

It means that a user who accessed service to a particular instance of will be redirected to the same instance of service based on defined parameters. 
Session stickiness works on a few parameters that can be any one of headers, routes or cookies. Based on these parameters the proxy of load balancer takes decision where to route the traffic. 


**In 7 layer architecture, in which layer does IP is used?**

It stands in the 3rd layer which is the network layer. 


**In 7 layer architecture, in which layer does TCP is used?**

It stands in 4th layer which is transport layer 


**How to copy a file from one machine to another?**

You can use SCP utility.


**Do you know which mathematical terms public key encryption uses?**

Prime numbers and modulo.


**How to see current time in linux?**

***date***


**How to see the difference between two files in linux?**

***diff file1 file2***


**What is an ephemeral memory?**

Ephemeral memory is one where the data is lost on a reboot. It is generally faster than disks and slower than RAM. 


**What is verbose mode?**

The Verbose mode is one in which your program emits log about each step and what it is doing. It is used for debugging purposes. 

**What does pipe | does?**

You can use this to pass the output of one program as an argument to another one. 


**How can you pass output of one script to another in bash?**

***Script2 | script2***


**What is CFS scheduling?**

Completely Fair Scheduling is the scheduling algorithm which is by default used in most of the linux operating systems. It tries to optimize the utilization of CPU while increasing interactive performance. 


**What do you mean by preemptive scheduling?**

Preemptive scheduling is one where the CPU can trigger an interrupt to start running the other high priority task. It is the one in which a process can leave the CPU before reaching its waiting state or final state which is not the case with non-preemptive scheduling. In current days most of the algorithms used in scheduling are preemptive. 


**Which system call is used to create a process?**

***fork()***


**Which system call is used to open a file?**

***open()***


**Do you know about GDB?**

GDB stands for GNU debugger. It is debugger and can be attached to many programming languages for debugging purposes. Few of these languages are C, C++, go, fortran etc.


**What is a grub?**

Grub is a grand unified bootloader. Grub is the first program that runs when you start your machine. It loads the operating system to the memory and then transfers the control to it. 


**What does ICMP stand for, name one tool that uses it?**

It stands for Internet Control Message Protocol. Ping is one of the most common tools that uses it. It is used for debugging networks.


**There is already a file with the name filename. You run this command touch filename. Now what will happen?**

It will change the timestamp of the file. 


**When you see linux man pages you see there are many types of commands one is command(2) and other can command(1) or any number what these numbers specify?**

These numbers specify which section these values belong to. This is the list:

1. User commands
2. System Calls
3. C library functions
4. Devices and special files. 
5. File formats and conversions. 
6. Game et. al.
7. Miscellaneous
8. System administration tool and daemons.


**What is tty?**

Tty is a teletypewriter. When you run tty it shows you the file to which the current terminal is attached. 


**What is pty?**

These are pseudo teletypes that act as a virtual terminal to process reading and writing to it but these teletypes are controlled by some other  process. 


**How to list all hidden files in a directory?**

***ls -a***


**How to make a file or script executable?**

***chmod a+x filename***


**How to find the files modified in the last 5 days?**

***find / -mtime -50***


**How to find the files accessed in the last 5 days?**

***find / -atime -50***


**Do you know what bastian servers are?**

These are the jump servers used to get access inside any VPC(Private subnet) It is the box launched in the Public subnet of VPC to get inside the Private Subnet. 


**How to add and remove soft links in linux?**

For adding links: ***ln -s file link**
For removing link: ***unlink***


**What do you know about packet encapsulation?**

Packet encapsulation is a process in which the lower levels in the OSI layer encapsulate the packets that are passed to it by the upper layer. For example a packet from a transport layer when moving to a network layer is encapsulated with extra information like header and source destination ip address. 


**What do you mean by VPC peering?**

VPC is a process in which two VPCs are connected in such a way that they are treated as a local network. 


**What is the difference between cron and anacron?**

With crontab you can schedule a job to be run after any interval or at a particular time. With anacorn you can schedule a job only on  a daily basis.


**What are the system calls used for process management?**

***fork() exec() wait() and exit()***


**What are linux aliases?**

Alias in bash instructs the bash to replace a particular string with a predefined command. You can add this alias in .bashrc or or .bash_profile something like this
alias l=’ls’
So when you type l, ls will get executed. 


**How to run a simple web server using python?**

***python -m SimpleHTTPServer***


**How to verify if the given json is valid?**

***python -m json.tool < data.json**


**When you open a terminal you want to execute a few scripts or commands, how can you do it?**

You can put them in ***.bashrc**







