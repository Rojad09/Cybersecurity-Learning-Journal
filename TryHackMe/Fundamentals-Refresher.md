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
