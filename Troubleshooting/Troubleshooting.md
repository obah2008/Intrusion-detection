## Issue 1:
Ran to this same issue while installing Splunk as I did in my last lab. Splunk fails to start with the following error
```bash
Warning: cannot create "/opt/splunk/var/log/splunk"  
Warning: cannot create "/opt/splunk/var/log/introspection"  
Warning: cannot create "/opt/splunk/var/log/watchdog"  
Warning: cannot create "/opt/splunk/var/log/client_events"  
Warning: cannot create "/opt/splunk/etc/licenses/download-trial"  
```

## fix: Just use **Sudo**
Run the command again, but this time with sudo infront of it
```bash
sudo /opt/splunk/bin/splunk start
```
