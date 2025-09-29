# Writing Detection rules
The first sep to writing a detection rule, is to understand the traffic you want to write it for, what you're looking for or trying to match within that traffic and lastly what should happen to that traffic when what we're looking for matches the contents of the packet.

A suricata detection rule in it's simplest form is this

action protocol src_ip src_port -> dest_ip dest_port (options)

"Action" defines what suricata will do with the packet, the available options for this section are
- Alert
- pass
- drop
- reject 
- rejectsrc
- rejectdst
- rejectboth

## Writing SPL queries
Splunk query Language allows you to sift through logs that have been ingested to suricata, the first step to writing SPL queries is defining the index--think of it like a storage container where logs collected by splunk are stored
for example, in this lab, all of the logs that will be identified will be analyzed are stored in an index named suricata, we can specify the index using ```index = "suricata"```
other useful metrics you might specify are the source  and source_type metric, this usually helps filter when you have logs from multiple locations and what type of logs they are. Splunk collects logs from just about everywhere but for this lab I'll be focusing on logs generated in the "/var/log/suricata/eve.json" of source type "suricata:json"
