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
