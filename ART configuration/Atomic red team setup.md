# Atomic Red Team
## What is Atomic Red Team
ART is a library of **tests** that simulate adversary behaviours and techniques based on MITRE framework. These tests are called **Atomics**, a pretty explosive name in my opnion.

## Why Atomic Red Team
Now besides the bad jokes what else are we doing in this lab, that is in regards to Red canary's Atomic red team: 
1) Generating telemetary: ART is going to be responsible for generating all of the malicious traffic we'll be responding to in this lab
2) Detection Validation: ART will be incharge of making sure the custom rules I write actually work, so ti's incharge of over

## Installing ART
Since we are installing atomic red team on Linux(Ubuntu to be specific) We'll need to install **PowerShell core** so let's quickly do that:

### installing PowerShell core
Following Official documentation from microsoft, which you can check over [here](https://learn.microsoft.com/en-us/powershell/scripting/install/install-debian?view=powershell-7.5)

- Download the Microsoft repository GPG keys using the command below
```bash
wget -q https://packages.microsoft.com/config/debian/$VERSION_ID/packages-microsoft-prod.deb
```
- Register the GPG keys
```bash
sudo dpkg -i packages-microsoft-prod.deb
```
-  Delete the GPG keys
```bash
rm packages-microsoft-prod.deb
```

- Install PowerShell
```bash
sudo apt-get install -y powershell
```
<img width="1357" height="668" alt="image" src="https://github.com/user-attachments/assets/ea12f842-d8f9-4e6b-8623-17a91f4a9d0d" />
- Start PowerShell
pwsh


### installing ART
Now that we have powershell installed, we can move on to installing Red canary's Atomic red team, see [here](https://github.com/redcanaryco/invoke-atomicredteam/wiki/Installing-Invoke-AtomicRedTeam) for official documentation

- Install ART and the Atomics folder
```pwsh
IEX (IWR 'https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1' -UseBasicParsing);
Install-AtomicRedTeam -getAtomics -Force
```
<img width="1220" height="693" alt="image" src="https://github.com/user-attachments/assets/f78e84eb-405e-45ce-ad8d-187d2d4ca338" />

- Run tests
Now that we have both the invoke atomic engine and the Atomics folder, we can check if they work properly by running an atomic test, for this I have picked Atomic T1016
```pwsh
invoke-AtomicTest T1016
```
