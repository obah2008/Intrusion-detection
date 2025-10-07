# Writing Detection rules
The first sep to writing a detection rule, is to understand the traffic you want to write it for, what you're looking for or trying to match within that traffic and lastly what should happen to that traffic when what we're looking for matches the contents of the packet.

A suricata detection rule in it's simplest form is this

action protocol src_ip src_port -> dest_ip dest_port (options)

the action field defines what suricata will do with the packet, the available options for this section are
- Alert
- pass
- drop
- reject 
- rejectsrc
- rejectdst
- rejectboth

the protocol field tells suricata what type of traffic this rule applies to, the field can contain the following values

1. Network/Transport layer protocols
    - IP
    - UDP
    - TCP
    - ICMP
    
2. Application layer protocols
    - Http
    - DNS
    - FTP
    - RDP
    - SSH
  
the src_ip field determines what source IP address suricata looks for, This field can be a single address or a range of addresses or we can specify traffic from our internal network{$HOME_NET} or external network{$EXTERNAL_NET}, it can also have the value any, meaning all IP addresses that match the rules other parameters 

src_port field specifies what port suricata monitors

->/<-> specify the packet flow

dest_ip similar to src_ip but specifies the destination IP address

dest_port Specifies the destination Port to be monitored


options, they are contained in the parenthesis after the dest_port field, consisting of keyword value pairs separated by a paremthesis. It defines detection logic, metadata, and behavioral actions applied when the rule header matches network traffic. 

Some of the key pairs suricata uses are: 

- Option    [Description]
- content	[Matches a specific string or byte pattern in the payload]
- nocase	[Makes content match case-insensitive]
- offset	[Sets where in the payload to begin searching]
- depth	    [Limits how far into the payload to search]
- ttl	    [Match a specific Time To Live value (IPv4)]
- tos	    [Match a specific Type of Service (IPv4)]
- fragbits	[Match fragmentation flags in IP header]

#### Practical Rule Writing


## Writing SPL queries
Splunk query Language allows you to sift through logs that have been ingested to suricata, the first step to writing SPL queries is defining the index--think of it like a storage container where logs collected by splunk are stored
for example, in this lab, all of the logs that will be identified will be analyzed are stored in an index named suricata, we can specify the index using ```index = "suricata"```
other useful metrics you might specify are the source  and source_type metric, this usually helps filter when you have logs from multiple locations and what type of logs they are. Splunk collects logs from just about everywhere but for this lab I'll be focusing on logs generated in the "/var/log/suricata/eve.json" of source type "suricata:json"
