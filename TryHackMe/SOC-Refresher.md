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

## Room: [Next Room]
