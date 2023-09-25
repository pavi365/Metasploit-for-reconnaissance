# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/839a5940-f6e1-4b4b-9290-28ecfd29d07e)

## Invoke msfconsole:

## OUTPUT:
![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/90642bd7-8d35-4990-ad97-e285434cecf0)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/d45626b2-77a3-4019-915f-f8a485fc1da5)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/4a4c97b3-30a1-482f-900a-219bf650bab3)

## Step4: 
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/d0ad02cf-1ec2-4564-a3c8-232e86d1f143)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/1af4ccc1-94db-4263-948d-ea4d3dd71edc)

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/376b8bec-e8b8-4435-816b-540d7193eb64)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/c01a47ed-2bf4-42e5-93f9-280dfd70a20c)

The info command provides information regarding a module or platform

## OUTPUT:

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/764b2574-355e-4cda-b35f-ba269c782cb8)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/8877cd4f-9641-4160-8620-aa3e278b8267)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/7d4e2d24-cdc8-4e7c-98e8-23a0beb14da5)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/8f276a30-88d6-41e3-8146-a176ddbdd75f)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/d0f7dc03-acb9-47eb-978c-65648a07b2b5)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/820808df-a524-4555-80a1-bbf854bb1db2)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/pavi365/Metasploit-for-reconnaissance/assets/115135775/66257847-7ea2-477a-90f9-aee3192570d5)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
