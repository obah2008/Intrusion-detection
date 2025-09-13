# Suricata setup

## Objectives
The purpose of the project is to gain hands-on skills with Suricata by practicing basic incident simulation and response. It will include the following:

- Installing Suricata  
- Configuring Suricata  
- Creating Suricata rules  
- Network intrusion detection with Suricata  

## Tools Used
Not taking into account the hypervisor (VMware), the tools I'll be using in this project are:

- **Suricata** – The primary network intrusion detection system for this project.  
- **Attack Simulation Tool** – Undecided  

## Acknowledgments
This project was made possible through Hackersploit's Suricata guide video over on [YouTube](https://www.youtube.com/watch?v=91i7InHVOso&t=464s).  

## Installing & Configuring Suricata

### Installation
Install Suricata and its dependencies using the commands below:

```bash
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:oisf/suricata-stable
sudo apt-get update
sudo apt-get install suricata
```

### Configuration
Open the Suricata configuration file:

```bash
sudo nano /etc/suricata/suricata.yaml
```

Make the following changes:
- Change af-packet interface to the network interface Suricata will monitor
- Change HOME_NET to your device subnet address
- Set cross-platform libpcap capture support to your device interface
- Enable community-id by setting it to true

#### Enabling Rules
List the rules that come with Suricata:
```bash
sudo suricata-update list-sources
```
Enable a specific rule source:
```bash
sudo suricata-update enable-source <rule_name>
```

Update Suricata to include the new rules:

```bash
sudo suricata-update
```
View the rules Suricata has enabled:

```bash
cat /var/lib/suricata/rules/suricata.rules
```

#### Testing & Running Suricata
Test the configuration:

```bash
sudo suricata -T -c /etc/suricata/suricata.yaml -i <interface>
```
Start the Suricata service:

```bash
sudo systemctl start suricata.service
sudo systemctl status suricata.service
```
#### Test if suricata is working properly

Use the `testmynids` url
```bash
curl http://testmynids.org/uid/index.html
```

```bash
cat /var/log/suricata/fast.log
```
