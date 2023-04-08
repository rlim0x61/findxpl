# findxpl

Script that reads a list of installed linux system packages and finds exploits stored on exploitdb.

# Disclaimer

This is just a script to find exploit codes. It doesn't make anything further. However I don't assume any responsibilities for anyone who somehow decide to misuse this.
Therefore you must only use this script in IT assets' vulnerability tests or analysis for which you have proper and formal authorization from its owners. 

# findxpl.sh checksum
MD5SUM: 4cedb8da33bdec59b9bd7a0fe4a49e26  findxpl.sh // 
SHA1SUM: 474884c05230d4ab9fb19980ae8c04ebe880e9e7  findxpl.sh //
SHA256SUM: c7fe10f863c8eb80fe0130c81fd665fd8e81af1f95e086790c17b735d36f2219  findxpl.sh 

# Description

This is a script I wrote to automate exploit researching based on packages already installed in a Linux System.
During some pentest projects Privileve Escalation phase, I missed something to automate the task of searching ExploitDB to find exploits related to a list of all installed Linux packages. 

# Requirements

It needs:

- Exploitdb package. The script already checks for that and warns you if it doesn't find the exploitdb binary (searchssploit).
- A system package list.
  - For DEBIAN like systems: dpkg -l > package-list.
  - For RHEL like systems: rpm -qa > package-list

# Usage

$ git clone [repo-url.git]

$ chmod u+x findxpl.sh

$./findxpl.sh [package-list] ['Exploit title'] ['term|to|be|searched']

$./findxpl.sh [package-list.txt] ['Privilege Escalation'] ['Linux | Apache 2.4.10']

$./findxpl.sh [package-list.txt] ['Remote Code Execution'] ['Linux | Apache 2.4.10 | rce']

[*] Either the 'Exploit title' and the 'terms|to|be|searched' need to be passed always between single quotes as shown above.

![image](https://user-images.githubusercontent.com/39169975/230729665-60d3a69e-2679-4252-96d4-40b298502fc1.png)
![image](https://user-images.githubusercontent.com/39169975/230729693-c483d4e5-004a-497e-afef-1142d1dd138a.png)

# Output

Once the execution finishes, a folder called 'exploits' will be created.
It will store the exploit's suggestions for each system package assigned by its name.
You should review the exploits case by case considering your goals.

# Bugs or Tips

You can report here and I thank you for that.

# Tested on

Distributor ID:	Kali
Description:	Kali GNU/Linux Rolling
Release:	2023.1
Codename:	kali-rolling
