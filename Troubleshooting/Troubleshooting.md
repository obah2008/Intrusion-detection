## Issue 1:
Ran to this same issue while installing Splunk as I did in my last lab. Splunk fails to start with the following error
```bash
Warning: cannot create "/opt/splunk/var/log/splunk"  
Warning: cannot create "/opt/splunk/var/log/introspection"  
Warning: cannot create "/opt/splunk/var/log/watchdog"  
Warning: cannot create "/opt/splunk/var/log/client_events"  
Warning: cannot create "/opt/splunk/etc/licenses/download-trial"  
```

## Fix: Just use **Sudo**
Run the command again, but this time with sudo infront of it
```bash
sudo /opt/splunk/bin/splunk start
```
## Issue 2:
Ran into this error, while trying to run a Splunk search
```spl
Search not executed: The minimum free disk space (5000MB) reached for /opt/splunk/var/run/splunk/dispatch. user=obah., concurrency_category="historical", concurrency_context="user_instance-wide", current_concurrency=0, concurrency_limit=5000
```

## Fix: Turns out I had almost run out of space on the host VM. 
Allocate more space to the virtual machine
