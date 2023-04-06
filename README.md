# findxpl

Script that reads a list of installed linux system packages and finds exploits stored on exploitdb.

# Description

This is only a script I wrote to automate exploit researching based on packages alread installed in a Linux System.
During Privileve Escalation phase, I missed something to automate the task of searching ExploitDB to find exploits related to a specific vulnerable Linux package. So, I did this.

# Requirements

It needs:

- exploitdb package. The script already check this and warns you if it doesn't find the exploitdb binary (searchssploit).
- A system package list.
  - For DEBIAN like systems: dpkg -l > package-list.
  - For RHEL like systems: rpm -qa > package-list

# Usage

$ chmod u+x findxpl.sh

$./findxpl.sh [package-list] ['Exploit title'] ['term|to|be|searched']

$./findxpl.sh [package-list.txt] ['Privilege Escalation'] ['Linux | Apache 2.4.10']

$./findxpl.sh [package-list.txt] ['Remote Code Execution'] ['Linux | Apache 2.4.10 | rce']

[*] Either the 'Exploit title' and the 'terms|to|be|searched' need to be passed always between single quotes as shown above.

# Output

Once the execution finishes, a folder called 'exploits' will be created.
It will store the exploit's suggestions for each system package assigned by its name.

# Tested on

Distributor ID:	Kali
Description:	Kali GNU/Linux Rolling
Release:	2023.1
Codename:	kali-rolling
