# Splunk setup

## Installing  Splunk
- Download Splunk enterprise with the command below
```bash
sudo wget -O splunk-9.4.2-e9664af3d956-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/9.4.2/linux/splunk-9.4.2-e9664af3d956-linux-amd64.deb"
```
- Install the package with the following command
```bash
sudo dpkg -i splunk-9.4.2-e9664af3d956-linux-amd64.deb

```
<img width="1301" height="604" alt="image" src="https://github.com/user-attachments/assets/112fa54b-731d-48ed-9d1b-24f92aafd0a1" />

- Navigate to Splunk's directory and start Splunk
```bash
cd /opt/splunk/bin

sudo ./splunk start
```
- Accept the terms and agreements
<img width="1292" height="705" alt="image" src="https://github.com/user-attachments/assets/2fce4bcb-b66f-4456-a2cb-f3ad04b7b831" />

- Create a Username and password and complete the installation process

<img width="1330" height="667" alt="image" src="https://github.com/user-attachments/assets/23e32e9c-b9bb-4976-91a6-6118b7960c3c" />

- The dashboard can now be accessed at http://<your server's address>:8000
<img width="1365" height="683" alt="image" src="https://github.com/user-attachments/assets/b333496f-9c8d-4f0c-aa5f-ee838d8899ec" />

## Configuring Splunk
Since this is a single-VM setup, there’s no need to install the Universal Forwarder. Instead, we will configure Splunk Enterprise to directly collect logs from the Suricata **eve.json** file.

- Create a new index
An index is essentially a log bucket, where splunk stores log data
```bash
sudo /opt/splunk/bin/splunk add index suricata
```
- Add the **eve.json** file to the Suricata index
```bash
sudo /opt/splunk/bin/splunk add monitor /var/log/suricata/eve.json -index suricata -sourcetype suricata:json
```
- restart Splunk 
```bash
sudo /opt/splunk/bin/splunk restart
```
<img width="1324" height="678" alt="image" src="https://github.com/user-attachments/assets/5e952535-9ad4-45e5-9b68-9fecc20430bc" />
