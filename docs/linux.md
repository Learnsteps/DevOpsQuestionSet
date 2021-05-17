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

