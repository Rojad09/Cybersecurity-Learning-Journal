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

