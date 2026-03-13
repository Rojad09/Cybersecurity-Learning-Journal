# SOC - Refresher Notes
**Start Date:** 2026-3-04
**Status:** Updatiing
#### Currently getting a feel for the TryHackMe platform via their Cyber Security 101 course, which I plan to finish just for the accomplishment. While my main coursework is happening outside of THM, I would like to use the platform to broaden my form of study, putting a focus on some of their SOC simulation rooms which I found interesting. 
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

## Room: [Intro to Logs]


**Objective:** Learn the fundamental structure of system logs and how contextual correlation is used to piece together the full story of a cyber security incident.

**Key Concepts:**
* **Digital Footprints:** Just like tree rings reveal the history of a tree's life and environment, logs are the historical records of a digital system. Every interaction—from authentication attempts and file accesses to network connections and errors—leaves a digital footprint.
* **The Log File:** Because digital interactions happen at lightning speed, these individual footprints are aggregated into log files, which can grow exponentially in size depending on the system's activity level.



* **Anatomy of a Log Entry:** While specific formats vary by system, almost every useful log contains these core components:
    * **Timestamp:** Exactly *when* the event occurred.
    * **Source:** The system or application that generated the log.
    * **Event Type:** *What* kind of action took place.
    * **Details:** Contextual info like the initiating Username, Source IP address, or device User-Agent.

**The Investigation Framework (Contextual Correlation):**
A single log entry in isolation is rarely enough to prove a breach. The true power of logging is unlocked when you aggregate and cross-reference multiple sources (e.g., matching a VPN login IP with a Web Server access log). This allows an analyst to answer the critical questions of an incident.



| Investigation Question | Example Application (SwiftSpend Breach Scenario) |
| :--- | :--- |
| **What happened?** | An adversary accessed the SwiftSpend GitLab instance. |
| **When did it happen?** | Started at 22:10 on Wednesday, September 8th, 2023. |
| **Where did it happen?** | Originated from IP `10.10.133.168` inside the VPN users' segment. |
| **Who is responsible?** | A device using a specific Firefox/Linux User-Agent assigned to that VPN IP. |
| **Were they successful?** | Yes. Web proxy logs confirm they reached the target and maintained access via an uploaded web shell. |
| **What was the result?** | The adversary achieved Remote Code Execution (RCE) and performed post-exploitation activities. |

**Takeaways / Notes:**
* Logs are the absolute foundation of Incident Response. If a system isn't logging correctly—or if an attacker clears the event logs, the defense is flying completely blind.

**Log Types**

* **Objective:** Understand the different types of logs, how their data is formatted, and the industry standards that dictate how they should be generated, stored, and analyzed.
* **Key Concepts:**
  * **Log Types:** The most common categories that cover about 80% of typical use cases.
    * **Application Logs:** Specific app statuses, errors, and warnings.
    * **Audit Logs:** Operational activities crucial for regulatory compliance.
    * **Security Logs:** Logins, permission changes, and firewall activity.
    * **Server Logs:** Broad server-generated logs (system, event, error, access).
    * **System Logs:** Kernel activities, boot sequences, and hardware status.
    * **Network Logs:** Network traffic, connections, and related events.
    * **Database Logs:** Queries and updates within a DB system.
    * **Web Server Logs:** Requests processed by a web server (URLs, response codes).
  * **Log Formats:** Defines how data is structured and delimited within a log file. 
    * **Semi-structured:** Combines structured data with free-form text.
      * *Syslog Format:* Widely adopted protocol for system/network logs.
      * *Windows Event Log (EVTX):* Microsoft's proprietary format.
    * **Structured:** Strict, standardized formats that are highly conducive to parsing and automated analysis.
      * *CSV / TSV:* Field-delimited tabular data.
      * *JSON:* Highly readable and compatible with modern programming languages.
      * *W3C Extended Log Format (ELF):* Customizable, typically used by Microsoft IIS.
      * *XML:* Flexible and customizable markup language.
    * **Unstructured:** Free-form text. Context-rich but poses challenges for systematic parsing.
      * *NCSA Common Log Format (CLF):* Standard web server log for client requests (Apache default).
      * *NCSA Combined Log Format:* Extension of CLF that adds referrer and user agent data (Nginx default).
  * **Log Standards:** Guidelines specifying what to log, how to transmit securely, and retention periods.
    * *CEE (Common Event Expression):* MITRE standard providing a common log structure.
    * *OWASP Logging Cheat Sheet:* Developer guide for secure app logging mechanisms.
    * *Syslog Protocol:* Standard that separates message generation, storage, and analysis.
    * *NIST Special Publication 800-92:* Guide to computer security log management.
    * *Platform Specific:* Azure Monitor Logs, Google Cloud Logging, Oracle Cloud Infrastructure Logging.
* **Tools & Commands:**
  * `cat [filename]` : Linux command used to read and output the contents of standard log files (e.g., `.txt`, `.json`, `.log`).
  * `Get-WinEvent -Path "[path_to_file.evtx]"` : PowerShell command used to read and parse proprietary Windows Event Logs.
* **Key Takeaways:** Understanding the specific format and standard of a log file is critical because it dictates exactly which parsing tools and techniques you need to use for troubleshooting, incident response, and threat hunting.

**Log Collection, Management, and Centralisation**

* **Objective:** Understand the lifecycle of log data—from collection and time synchronization to secure management and centralisation—and perform a practical configuration to route specific logs using `rsyslog`.
* **Key Concepts:**
  * **Log Collection:** The process of aggregating logs from diverse sources (servers, networks, databases, apps).
    * **Time Synchronisation:** Absolutely critical for maintaining an accurate, chronological timeline of events across different systems. Usually achieved using **NTP (Network Time Protocol)**.
    * **Collection Steps:** Identify Sources -> Choose Collector -> Configure Parameters (enable NTP, prioritize events) -> Test Collection.
  * **Log Management:** Ensuring gathered logs are securely stored, systematically organized, and easily retrievable.
    * **Management Steps:** Secure Storage (consider retention periods) -> Organisation (by source/type) -> Regular Backups -> Periodic Review.
  * **Log Centralisation:** Unifying logs into a single system (like Elastic Stack or Splunk) for rapid incident response and in-depth analysis.
    * **Centralisation Steps:** Choose System -> Integrate Sources -> Set Up Real-Time Monitoring & Alerts -> Integrate with Incident Management protocols.
* **Tools & Commands:**
  * `ntpdate pool.ntp.org` : Manually synchronizes a Linux system's time with a public NTP server.
  * `date` : Displays the current system date and time to verify synchronization.
  * `scp` or `rsync` : Command-line utilities used for manual log collection and file transfer if automated remote log forwarding isn't set up.
  * **rsyslog Configuration Commands:**
    * `sudo systemctl status rsyslog` : Checks if the `rsyslog` service is installed and running.
    * `nano /etc/rsyslog.d/98-websrv-02-sshd.conf` : Creates or edits a custom `rsyslog` configuration file (you can also use `vi`, `vim`, or `gedit`).
    * `$FileCreateMode 0644` : An `rsyslog` directive placed inside the `.conf` file to set standard read/write permissions for the newly created log file.
    * `:programname, isequal, "sshd" /var/log/websrv-02/rsyslog_sshd.log` : The specific `rsyslog` rule that filters logs matching the program "sshd" and routes them to a dedicated file.
    * `sudo systemctl restart rsyslog` : Applies the configuration changes by restarting the service.
    * `ssh localhost` : Initiates a local SSH connection. This is a great way to generate immediate test logs to verify your new `rsyslog` routing works.
* **Key Takeaways:** Maintaining time accuracy across all systems via **NTP** is the absolute bedrock of log analysis; without it, tracking an adversary's exact sequence of events is nearly impossible. Mastering tools like `rsyslog` allows you to filter the noise and centralize high-value data (like SSH authentications) for much faster threat hunting.

**Log Storage, Retention, and Deletion**

* **Objective:** Understand where logs are stored, how long they should be kept using different storage tiers, and the best practices for safely deleting them to balance cost, compliance, and security.
* **Key Concepts:**
  * **Log Storage Locations:** Logs can be stored locally, in a centralized repository, or in the cloud. Choosing a location depends on:
    * **Security & Compliance:** Adhering to organizational protocols and industry regulations.
    * **Accessibility & Capacity:** How fast logs need to be searched and the sheer volume of data generated.
    * **Cost & Disaster Recovery:** Budget constraints and ensuring logs survive system failures.
  * **Log Retention (Storage Tiers):** Storage isn't infinite. Organizations balance historical data needs against cost by using tiers:
    * **Hot Storage:** Logs from the past **3-6 months**. Highly accessible with near real-time query speeds.
    * **Warm Storage:** Logs from **6 months to 2 years**. Acts as a data lake; easily accessible but not as immediate as Hot storage.
    * **Cold Storage:** Archived or compressed logs from **2-5 years**. Not easily accessible; mostly used for retroactive analysis or scoping.
  * **Log Deletion:** Must be executed carefully with a well-defined policy.
    * **Purpose:** Maintains a manageable log size, complies with privacy laws (like **GDPR** which requires deleting unnecessary data), and keeps storage costs down.
  * **Best Practices:**
    * Define policies based on both business needs and legal requirements.
    * **Automate** storage, retention, and deletion to ensure consistency and prevent human error.
    * **Encrypt** sensitive logs.
    * Always perform regular **backups**, especially right before a scheduled deletion.

* **Key Takeaways:** A strong logging pipeline categorizes data into Hot, Warm, and Cold tiers to save money while keeping critical, recent logs instantly searchable for incident response. Always automate your retention policies, and never delete without backing up first!

**Log analysis process, tools, and techniques**

**Objective:** Understand the end-to-end log analysis pipeline, the tools used for rapid vs. complex analysis, and the core techniques for deriving actionable insights from raw data.

### The Log Analysis Pipeline
* **Data Sources:** The origin systems or applications configured to log system events or user activities.
* **Parsing:** Breaking down raw log data from various formats into manageable, understandable components.
* **Normalisation:** Standardizing parsed data into a uniform format, allowing you to easily compare logs from entirely different sources.
* **Sorting:** Organizing data by parameters like time, source, or severity for efficient retrieval and pattern identification.
* **Classification:** Categorizing logs (often automated via machine learning) to quickly filter and focus on the most critical events.
* **Enrichment:** Adding external context to logs, such as geographical data, user details, or threat intelligence, to provide a complete picture.
* **Correlation:** Linking related records across different events to detect complex security threats or system issues that would otherwise remain hidden.
* **Visualisation:** Representing large volumes of data graphically (charts, heat maps) to intuitively spot trends and anomalies.
* **Reporting:** Summarizing data into structured formats to support decision-making, management reviews, and compliance audits.

### Log Analysis Techniques
* **Pattern Recognition:** Identifying recurring sequences to establish normal behavior or detect regular threats.
* **Anomaly Detection:** Spotting specific data points that deviate from the expected baseline.
* **Correlation Analysis:** Discovering relationships, causation, and dependencies between different system components (vital for root cause analysis).
* **Timeline Analysis:** Reviewing logs chronologically to understand performance trends and periodic behaviors over time.
* **Machine Learning & AI:** Automating tedious processes like classification and enrichment, and providing predictive insights.
* **Statistical Analysis:** Using mathematical methods like regression analysis to validate assumptions and make data-driven decisions.

### Tools & Commands
* `cat`, `grep`, `sed`, `sort`, `uniq`, `awk`: Default Linux command-line tools used for rapid, ad-hoc log parsing, especially during active incident response.
* `sha256sum`: Linux command used to take the hash of a log file during collection to ensure its integrity and admissibility in a court of law.
* `Get-FileHash`: The Windows PowerShell cmdlet equivalent for hashing files.
* **EZ-Tools:** A suite of Windows-based tools used for rapid parsing and analysis.
* **Splunk / ELK (Elastic Stack):** Enterprise Security Information and Event Management (SIEM) tools used for complex, large-scale log analysis tasks.

### Key Takeaways
Logs are only useful if you can trust them. Proper acquisition is critical—always take a file hash (`sha256sum` or `Get-FileHash`) the moment you collect a log to ensure its integrity and legal admissibility.

---

## Room: [Log Operations]

**Learning Objectives**
* Understanding the logic of log management and configuration
* Familiarise with log configuration approaches
* Experience the log configuration process

**Log Configuration**

**Objective:** Understand the four primary purposes of log configuration—Security, Operational, Legal, and Debug—and how they dictate what data a system should record.



### Security Purposes
* **Focus:** Detecting and responding to anomalies, threat activity, and unauthorized access.
* **Key Areas:** Logging user authentication data, verifying user activity, monitoring system integrity, and ensuring data confidentiality.

### Operational Purposes
* **Focus:** Maintaining system continuity, reliability, and performance.
* **Key Areas:** Troubleshooting system errors, capacity planning, service billing, and proactively generating status reports for system components.

### Legal & Compliance Purposes
* **Focus:** Ensuring the organization adheres to required laws, obligations, and industry standards.
* **Key Frameworks:** ISO 27001, COBIT, GDPR, PCI DSS, HIPAA, FISMA.
* **Example (PCI DSS Logging Compliance):** Requires an active central log management system, a strict 12-month log retention policy (with the most recent 3 months immediately searchable), and yearly audit checks.

### Debug Purposes
* **Focus:** Enhancing system features and discovering potential bugs or fault conditions.
* **Key Areas:** Usually restricted to testing and development environments (rarely implemented in production). Used to increase application visibility, improve efficiency, and speed up the development process.

### Key Takeaways
Log configuration is never a one-size-fits-all approach. A well-designed logging environment must perfectly balance the immediate need to catch active cyber threats (Security) with the strict, long-term retention requirements of industry regulations (Legal).

**Deciding Logging Purpose**

* **Objective:** Understand how to transition from defining your logging purpose to building an actionable implementation plan through structured team brainstorming.


* **Key Concepts:**
* **The Planning Meeting:** Far from a passive activity, this is the critical first step to get the ball rolling, consider multiple technical aspects, and create your foundational draft plan.
* **Post-Meeting Steps:** Once the initial questions are answered, the team must create a detailed plan, choose specific tools/technologies, and establish the actual monitoring and analysis processes.
* **Strategic Questioning:** Every implementation is unique, but asking standard baseline questions ensures no major operational or security gaps are missed before spending budget on tools.

* **Key Planning Questions to Ask:**
* **Scope & Purpose:** What exact assets will we log, and what is the specific purpose? Are there extra commitments required to achieve this?
* **Data Volume:** How much data are we planning to log versus how much data do we *actually* need to log?
* **Logistics & Analysis:** How are we going to collect the logs, where will they be stored, and how will they be analyzed?
* **Compliance & Security:** Are there specific laws, regulations, or standards we must comply with based on the data we are collecting? How will we protect these logs from tampering?
* **Resources:** Do we realistically have the budget, workforce, and resources necessary to plan, implement, and maintain this logging pipeline?

* **Key Takeaways:** Never jump straight into configuring tools. Always start with a structured brainstorming session to align your team on scope, budget, and compliance requirements so you don't end up collecting useless data or violating privacy laws.

**Configuration Dilemma: Planning and Implementation**

* **Objective:** Understand the challenge of balancing mandatory logging requirements (like basic security and compliance) with the proactive aspirations of threat hunting, all while managing costs and resources.

### The Configuration Dilemma
* **The Core Challenge:** Finding the practical balance between technical requirements, scope, log details, and price (which includes financial costs, manual labor, and infrastructure investments).
* **Key Stakeholders:** A successful log configuration plan requires input from system administrators, legal advisors, financial advisors, and management.
* **Meeting Objective:** Fulfill the non-negotiable operational and security requirements first, *then* evaluate if it is feasible to collect additional data for deeper insights.
* **Risk Assessment:** Conducting a comprehensive risk assessment that prioritizes security, compliance, and legal needs is the best way to navigate this dilemma and justify costs.

### Requirements vs. Aspirations


* **Base Requirements (The "Reactive" Mindset):**
  * Focuses primarily on **Incident Detection**.
  * Crucial for defending against known threats and building a solid logging foundation.
  * **Key Questions Answered:** What happened? When did it happen (timestamps)? Where did it happen (network, path)? Who or what caused it? Which log source reported it?

* **Aspirations for Better Insights (The "Proactive" Mindset):**
  * Focuses primarily on **Threat Hunting**.
  * Crucial for defending against advanced, sophisticated, or zero-day threats.
  * Requires significantly more resources (storage, compute power, and analyst time).
  * **Key Questions Answered:** Can we get more granular details? How accurate is this data? What exactly is affected? What will the adversary do next? What specific actions should we take to remediate?

### Key Takeaways
You must build your baseline first to establish a solid incident detection and response foundation. However, to survive in the modern, ever-evolving threat landscape, your operational vision must eventually expand to include those proactive, resource-heavy threat hunting aspirations.

**Principles and Difficulties**

* **Objective:** Understand the core principles required to build an effective logging pipeline and anticipate the common technical and operational challenges you will face.
* **Key Concepts:**

### Logging Principles
A proper logging operation requires active resource utilization and strict adherence to foundational principles to ensure efficiency.

| Category | Core Principles |
| :--- | :--- |
| **Collection** | Define the logging purpose. Collect only what you need and use. Actively avoid logging irrelevant data (noise). |
| **Format** | Log at the correct level of detail. Implement a consistent format across systems. Ensure timestamps are strictly accurate and synchronized (NTP). |
| **Archiving & Accessibility** | Define and enforce retention policies. Ensure critical logs are readily available for analysis. Always create backups of stored data. |
| **Monitoring & Alerting** | Create alerts *only* for important, noteworthy cases. Focus strictly on actionable alerts to avoid alert fatigue/noise. |
| **Security** | Protect logs with strict access controls. Implement encryption where required. Use dedicated, isolated log management solutions. |
| **Continuous Change** | Understand that log sources and messages constantly evolve. Be open to continuous system changes and actively train your personnel. |

### Logging Challenges
Most log management challenges can be mitigated during the initial planning phase, but you must be prepared to handle the following hurdles.

| Category | Common Challenges |
| :--- | :--- |
| **Data Volume & Noise** | Juggling multiple data sources with varying log volumes. Some apps generate too little data, while others create massive, noisy datasets that obscure actual threats. |
| **System Performance** | Log collection agents can drastically slow down host performance. Managing agent updates across large networks is overwhelming. Legacy ("ancient") systems are often too fragile to touch. |
| **Process & Archive** | Parsing disparate data formats is time-consuming and error-prone. Balancing retention limits against strict compliance regulations is a constant struggle. |
| **Security** | Securing the log data itself from tampering or unauthorized access is a massive undertaking. |
| **Analysis** | Correlating data across multiple sources requires significant computing power and expertise. Achieving this in real-time while avoiding false positives/negatives is highly complex. |
| **Miscellaneous** | Lack of planning, budget, or technical skills. Focusing entirely on *collecting* logs rather than actually *analyzing* them. Ignoring the human factor (burnout, misconfigurations). |

* **Key Takeaways:** You can collect all the data in the world, but if you don't have the compute power, budget, or skilled personnel to actually analyze it, your logging pipeline is useless. Adhere to the principles, anticipate the data volume challenges, and focus on actionable alerts.

---

## Room: [Log Fundamentals]

**Use Cases Of Logs**
* **Security Events Monitoring** - Logs help us detect anomalous behavior when real-time monitoring is used.
* **Incident Investigation and Forensics** - Logs are the traces of every kind of activity. It offers detailed information on what happened during the incident. The security team utilizes the logs to perform root cause analysis of incidents.
* **Troubleshooting** - As the logs also record the errors in systems or applications, they can be used to diagnose issues and helpful in fixing them.
* **Performance Monitoring** - Logs can also provide valuable insights into the performance of applications.
* **Auditing and Compliance** - Logs play a major role in Auditing and Compliance, making it easier with its capability to establish a trail of different kinds of activities.

**Windows Event Viewer Log Analysis**
* **Objective:** Understand the primary Windows event log categories, learn to navigate the built-in Event Viewer utility, and filter logs to track specific security events using critical Event IDs.
* **Key Concepts:**
  * **Core Windows Log Categories:** Windows segregates logs into specific files based on their category.
    * **Application:** Information, errors, warnings, and compatibility issues related to installed software.
    * **System:** OS-level operations, driver issues, hardware status, system startup/shutdown, and background services.
    * **Security:** The most critical log for analysts. Tracks user authentication, account modifications, and security policy changes.
  * **Event Log Fields:** When you double-click a log entry, you see detailed metadata.
    
    * **Description:** Detailed information about the specific activity.
    * **Log Name:** The file where the log is stored.
    * **Logged:** The exact timestamp of the activity.
    * **Event ID:** A unique numerical identifier for a specific type of activity.
  * **Crucial Windows Event IDs:** While you don't need to memorize all of them, these are foundational for tracking user activity and potential compromise:

| Event ID | Description |
| :--- | :--- |
| **4624** | A user account successfully logged in. |
| **4625** | A user account failed to login. |
| **4634** | A user account successfully logged off. |
| **4720** | A user account was created. |
| **4722** | A user account was enabled. |
| **4724** | An attempt was made to reset an account’s password. |
| **4725** | A user account was disabled. |
| **4726** | A user account was deleted. |

* **Tools & Techniques:**
  * **Event Viewer:** The built-in Windows GUI utility used to view and search logs (accessible via the Start Menu).
    
  * **Filter Current Log:** A powerful feature within Event Viewer that allows you to narrow down thousands of events to just the ones you care about. 
    
    * *Technique:* Click 'Filter Current Log' on the right-hand pane, and type a specific ID (e.g., `4624`) into the `<All Event IDs>` field to instantly isolate successful logins.

* **Key Takeaways:** You don't need external parsing tools to start hunting on a Windows machine; the built-in Event Viewer is highly capable. Knowing just a handful of Event IDs (like 4624 and 4625) allows you to quickly filter out noise and spot brute-force attacks or unauthorized access.

**Web Server Access Logs Analysis** 
* **Objective:** Understand the structure of a standard web server access log and use basic Linux command-line utilities to manually parse, filter, and analyze the data.
* **Key Concepts:**
  * **Web Server Access Logs:** Every request made to a website (viewing a page, logging in, uploading a file) is recorded by the web server. 
  * **Default Apache Log Location:** Typically found at `/var/log/apache2/access.log` on Linux systems.
  * **Log Entry Breakdown:** A standard Apache log entry contains several crucial fields:
    * **IP Address:** The IP of the user making the request (e.g., `172.16.0.1`).
    * **Timestamp:** When the request occurred (e.g., `[06/Jun/2024:13:58:44]`).
    * **Request:** Contains the **HTTP Method** (like `GET` or `POST`) and the **URL/Resource** being requested (like `/products`).
    * **Status Code:** The server's response code (e.g., `200` for success, `404` for not found, `500` for server error).
    * **User-Agent:** Metadata about the user's Operating System and browser.



* **Tools & Commands:**
  * `cat [filename]` : Displays the entire contents of a log file in the terminal.
    * *Pro-Tip:* You can combine rotated log files into a single file for easier analysis using: `cat access1.log access2.log > combined_access.log`
  * `grep "[string]" [filename]` : Searches the log file for specific strings or patterns and outputs only the matching lines (e.g., `grep "192.168.1.1" access.log`).
  * `less [filename]` : Opens the log file in a paginated view, allowing you to scroll through massive files without flooding your terminal.
    * **less Navigation Shortcuts:**
      * `Spacebar` : Move forward one page.
      * `b` : Move backward one page.
      * `/pattern` : Type `/` followed by your search term and hit `Enter` to search within the file.
      * `n` : Jump to the *next* occurrence of your search term.
      * `N` : Jump to the *previous* occurrence of your search term.

* **Key Takeaways:** Web logs are incredibly noisy. Mastering `grep` allows you to instantly slice through the noise to track a specific attacker's IP address, while `less` is perfect for carefully reviewing the chronological events immediately before and after an attack.

---

## Room: [Next Room]
