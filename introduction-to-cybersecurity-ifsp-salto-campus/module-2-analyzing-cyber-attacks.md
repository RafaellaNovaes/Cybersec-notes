---
description: >-
  This module covers the most common attack vectors, including malware, social
  engineering techniques, denial of service attacks, and security
  vulnerabilities.
---

# Module 2: Analyzing Cyber Attacks

### Malware: Malicious Software

Malware (Malicious Software) is any software intentionally designed to cause harm to computer systems, networks, or users. It serves various purposes depending on the attacker's objectives:

* **Data Theft**: Extracting sensitive information such as passwords, financial data, or personal identifiers
* **System Invasion**: Gaining unauthorized access to systems and networks
* **Security Bypass**: Circumventing security measures and protections
* **Damage**: Corrupting, deleting, or destructing data and system functionality

Identifying and understanding different malware types is essential for developing effective detection, mitigation, and removal strategies.

#### Types of Malware

| Type       | Primary Characteristic           | Key Risk             | Common Targets      |
| ---------- | -------------------------------- | -------------------- | ------------------- |
| Spyware    | Monitors and steals data         | Espionage            | Personal devices    |
| Adware     | Displays unwanted advertisements | Resource consumption | Browsers            |
| Backdoor   | Provides hidden remote access    | Persistence          | Enterprise systems  |
| Ransomware | Encrypts and extorts data        | Critical data loss   | Organizations       |
| Scareware  | Deceives with false threats      | Social manipulation  | Inexperienced users |
| Rootkit    | Conceals itself in system        | Deep infection       | Operating systems   |
| Virus      | Infects files and replicates     | File corruption      | Executable files    |
| Trojan     | Disguises as legitimate software | Covert installation  | Applications        |
| Worm       | Self-replicates across networks  | Rapid spread         | Network systems     |

#### Detailed Malware Categories

**Spyware**

Spyware operates covertly to monitor user activities and steal sensitive information. This malware type:

* Monitors keyboard inputs (keylogging)
* Captures screen activities
* Tracks browsing history
* Harvests login credentials
* Records personal communications

The primary threat is unauthorized surveillance and data exfiltration without user knowledge.

**Adware**

While technically not always malicious, adware represents a significant nuisance and potential security risk:

* Displays intrusive advertisements
* Redirects web traffic to promotional sites
* Tracks browsing behavior for targeted advertising
* Consumes system resources

Adware often serves as a vector for other malware infections.

**Backdoor**

Backdoors create persistent unauthorized access points to systems:

* Bypasses normal authentication mechanisms
* Allows attackers to maintain access even after initial compromise
* Provides remote command execution capabilities
* Often installed by other malware or compromised software

Historical examples include Remote Access Trojans (RATs) that provide full system control.

**Ransomware**

Ransomware represents one of the most financially damaging malware categories:

1. Infects target systems
2. Encrypts critical files and data
3. Demands payment (typically in cryptocurrency) for decryption keys
4. Threatens data destruction or publication

Notable historical incidents include WannaCry (2017), which affected over 200,000 computers across 150 countries.

**Scareware**

Scareware employs psychological manipulation tactics:

* Displays false security warnings
* Simulates antivirus alerts
* Pressures users to purchase "security" software
* Actually installs additional malware

This technique exploits fear and urgency to compromise systems.

**Rootkit**

Rootkits operate at the deepest system levels:

* Conceal their presence from system monitoring tools
* Function at kernel or driver level
* Provide administrative access
* Extremely difficult to detect and remove

Examples include ZeroAccess and TDSS, which infected millions of systems.

**Virus**

Traditional computer viruses:

* Infect executable files
* Require user action to propagate (file execution)
* Replicate by modifying other programs
* Can destroy data or degrade system performance

Viruses represent one of the oldest and still relevant malware categories.

**Trojan**

Trojans operate through deception:

* Appear as legitimate software
* Perform advertised functions initially
* Execute hidden malicious actions simultaneously
* Do not self-replicate (require distribution)

Unlike viruses, Trojans don't copy themselves but instead provide entry points for additional threats.

**Worm**

Worms represent self-propagating network threats:

* Self-replicate automatically across networks
* Require no user interaction to spread
* Exploit network vulnerabilities
* Often form botnets for coordinated attacks

#### Malware Symptoms and Detection

While different malware types have distinct characteristics, they often produce similar system behaviors that indicate infection.

**System Performance Degradation**

Malware consumes system resources for its operations:

* Elevated CPU usage (system becomes slow)
* Overall system slowdown beyond normal performance
* Frequent system freezes or crashes
* Programs closing unexpectedly

These symptoms occur because malware operates in the background, competing for system resources.

**Network and Internet Issues**

Network anomalies may indicate malware presence:

* Significantly slower internet browsing
* Unstable or frequently dropping connections
* Unexplained network problems without clear cause

These symptoms suggest malware may be either stealing data or commandeering your internet connection (such as through botnet participation).

**Suspicious System Modifications**

Unauthorized system changes indicate compromise:

* Files modified or deleted without user action
* Unknown files or icons appearing on the system
* Configuration settings altered without user intervention

Such modifications represent classic invasion indicators or automated malware actions.

**Unusual System Behavior**

Anomalous system activity should trigger investigation:

* Unknown processes running in system memory
* Programs opening and closing independently
* System appears to operate autonomously
* Unexpected network traffic or activity

**Unauthorized Activities**

User-facing evidence of compromise includes:

* Emails sent from your account without authorization
* Suspicious account activity or unauthorized logins
* Compromised online accounts with altered credentials

#### Malware Detection and Removal

**Recommended Security Tools**

| Tool             | Type           | Platform       | Purpose                  |
| ---------------- | -------------- | -------------- | ------------------------ |
| Windows Defender | Antivirus      | Windows        | Built-in protection      |
| Malwarebytes     | Anti-malware   | Multi-platform | Specialized detection    |
| Avast            | Antivirus      | Multi-platform | Comprehensive protection |
| Norton           | Security Suite | Multi-platform | Full-featured defense    |
| Kaspersky        | Antivirus      | Multi-platform | Advanced detection       |

***

### Social Engineering

Social engineering represents the manipulation of human psychology to compromise security. Rather than exploiting technical vulnerabilities, social engineers target the human element of security systems.

The most dangerous attacks:

* Do not rely on code or technical exploits
* Target organizational weaknesses through human interaction
* Succeed through manipulation and deception

This is why organizations invest heavily in:

* Employee security training and awareness programs
* Security policies and procedures
* Continuous security education

Attackers often target humans as "the weakest link" rather than technical systems, making social engineering profoundly effective.

#### Primary Social Engineering Methods

**Pretexting (Fabrication)**

Pretexting involves creating a false scenario to extract sensitive information:

**Methodology:**

* Attacker fabricates a convincing story
* Impersonates a trusted authority figure or organization
* Requests sensitive data based on the fabricated context

**Real-world Examples:**

* "I'm calling from your bank to verify recent transactions"
* "I'm from IT support; your password needs immediate reset"
* "I'm from HR updating employment records; I need your SSN"
* "I'm a maintenance technician; I need access to the server room"

**Detection Indicators:**

* Unexpected contact requesting sensitive information
* Artificial urgency or pressure to act immediately
* Requests inconsistent with normal procedures
* Caller cannot be verified through official channels

**Protective Measures:**

* Never provide passwords or sensitive data via unsolicited contact
* Verify caller identity through official company numbers
* Establish policy: legitimate organizations never request passwords
* Train employees to recognize pretexting attempts

**Tailgating (Physical Infiltration)**

Tailgating exploits physical security by gaining access to restricted areas:

**Methodology:**

* Attacker follows authorized personnel through secure access points
* Exploits courtesy or distraction of legitimate employees
* Gains physical access to sensitive areas (data centers, server rooms)

**Real-world Examples:**

* Following someone through a badge-controlled door
* Posing as a delivery person to gain building access
* Offering to "help carry" items to bypass security checkpoints
* Requesting badge access due to forgotten credentials

**Detection Indicators:**

* Unknown individuals in restricted areas
* People without visible identification badges
* Unusual requests for building or system access
* Nervous or evasive behavior around security measures

**Protective Measures:**

* Never hold doors for unknown individuals
* Challenge people without proper identification
* Implement turnstile or security vestibule systems
* Train employees on tailgating awareness
* Conduct regular security awareness drills

**Historical Example:** Kevin Mitnick, a renowned hacker, frequently used tailgating and social engineering to access physical facilities and system resources.

**Quid Pro Quo (Exchange Agreement)**

Quid pro quo attacks exploit reciprocity by offering value in exchange for information:

**Methodology:**

* Attacker offers something of perceived value
* Exploits human curiosity or need
* Extracts information or access as exchange

**Real-world Examples:**

* "Win $1000 if you provide your personal information"
* "Claim a prize by entering your credit card details"
* "Free antivirus download (actually contains malware)"
* "Test our new product with administrator access"

**Detection Indicators:**

* Offers that seem unusually favorable
* Requests for personal or sensitive data
* Files or links from unknown sources
* Promises with artificial urgency or limited availability

**Protective Measures:**

* Adopt skepticism toward unsolicited offers
* Verify offers through official channels
* Never click links in unexpected emails
* Recognize that "too good to be true" usually is

#### Social Engineering Variations

**Phishing**

Phishing involves sending fraudulent emails to steal credentials:

**Characteristics:**

* Mass distribution of deceptive emails
* Designed to capture login credentials
* Often distributes malware
* Installs backdoors or remote access tools

**Example Attack:**

```
From: support@paypa1.com (note: uses "1" instead of "l")
Subject: Account Verification Required
Content: Click here to confirm identity
Result: Redirects to fraudulent website identical to legitimate site
```

**Spear Phishing**

Spear phishing targets specific individuals with personalized information:

**Characteristics:**

* Highly targeted attack against specific person
* Uses personal information from research (LinkedIn, social media)
* Includes correct department, project names, and details
* Far more convincing than generic phishing

**Example Attack:**

```
From: manager@company.com (actually spoofed)
Subject: Project X Documentation Needed Urgently
Content: John, please send the Q4 project files immediately
Result: Significantly higher success rate than generic phishing
```

**Vishing (Voice Phishing)**

Vishing conducts phishing attacks via telephone:

**Characteristics:**

* Impersonates technical support or legitimate organizations
* Claims account compromise or fraud detection
* Requests credential confirmation
* Creates immediate urgency

**Common Example:** "We detected fraud on your account. Please confirm your current password..."\
\
Psychological Factors Exploited

| Factor      | Exploitation Method                 | Example                         |
| ----------- | ----------------------------------- | ------------------------------- |
| Trust       | Impersonating trusted entities      | "I'm calling from your bank"    |
| Authority   | Simulating positions of power       | "I'm from IT management"        |
| Urgency     | Creating time pressure              | "You have 5 minutes to act"     |
| Gain/Fear   | Offering reward or threatening loss | "You'll lose access unless..."  |
| Guilt       | Making target feel responsible      | "You didn't update your system" |
| Reciprocity | Offering help to extract assistance | "I helped you; now help me"     |

#### Organizational Protection Strategies

**1. Employee Training:**

* Regular security awareness programs
* Phishing simulation exercises with feedback
* Recognition of social engineering tactics
* Reporting mechanisms for suspicious activities

**2. Technical Controls:**

* Multi-factor authentication on all systems
* Email filtering for suspicious content
* Rate limiting for invalid login attempts
* Monitoring for unusual access patterns

**3. Security Culture:**

* Zero-trust organizational approach
* Incident reporting without punishment
* Leadership emphasis on security importance
* Regular policy reviews and updates

#### Key Takeaways

* Social engineering exploits psychology, not technology
* Humans represent the final security barrier
* Training and awareness are critical defenses
* Organizational culture significantly impacts vulnerability
* Verification through official channels prevents most attacks

***

### Denial of Service (DoS) Attacks

A Denial of Service (DoS) attack attempts to render a system, service, or network unavailable to legitimate users. Rather than stealing data or gaining access, attackers simply prevent normal operation.\
\
**Potential Targets:** Websites and web applications, Email services and communication systems, Network infrastructure, Enterprise servers, Mobile applications, Critical infrastructure (power, water systems)

**Attack Outcomes:** Service slowdown or degradation, Complete service outages, System crashes and restarts, Prolonged unavailability, Significant financial losses.

**Primary DoS Attack Methods**

**Volume-Based Attacks (Traffic Flooding)**

Volume-based attacks overwhelm systems with excessive traffic:

**Mechanism:**

1. Attacker generates massive amounts of traffic
2. Targets systems cannot process incoming requests
3. System resources become exhausted
4. Service becomes unavailable to legitimate users

**Technical Example:**

```
Attacker capacity: 1,000,000 requests/second
Server capacity: 100,000 requests/second
Result: 900,000 requests dropped
Outcome: Service offline or severely degraded
```

**Attack Types:**

* HTTP request floods
* DNS query floods
* UDP packet floods
* ICMP ping floods
* DNS amplification attacks

**Protocol-Based Attacks (Malformed Packets)**

Protocol attacks exploit weaknesses in network protocols:

**Mechanism:**

* Attacker sends malformed or invalid packets
* Packets violate protocol specifications
* Systems cannot process invalid data correctly
* Results in crashes, hangs, or resource exhaustion

**Real-world Examples:**

**Teardrop Attack:**

* Sends overlapping IP fragments
* Systems cannot reassemble fragments correctly
* Kernel-level crash on vulnerable systems

**Ping of Death:**

* ICMP packets exceed maximum size (65,535 bytes)
* Vulnerable systems crash when processing
* Largely mitigated in modern systems

**SYN Flood:**

* Attacker sends thousands of incomplete TCP connection requests
* Server allocates resources for each connection attempt
* Resources exhaust before legitimate connections established
* Service becomes unavailable

**SYN Flood Mechanism:**

```
Normal connection: Client SYN → Server SYN-ACK → Client ACK
SYN Flood: Client SYN → Server SYN-ACK → (No ACK from attacker)
Result: Server left with incomplete connections consuming resources
```

***

### Distributed Denial of Service (DDoS)

A Distributed Denial of Service (DDoS) attack coordinates multiple computers to attack a single target simultaneously, creating a distributed attack that is more powerful and difficult to defend against than standard DoS attacks.

#### DoS vs DDoS Comparison

| Characteristic | DoS                         | DDoS                             |
| -------------- | --------------------------- | -------------------------------- |
| Origin         | Single computer             | Hundreds or thousands            |
| Power          | Limited by single source    | Massively scalable               |
| Detection      | Straightforward (single IP) | Difficult (distributed IPs)      |
| Scale          | Typical range: Gbps         | Can exceed Tbps                  |
| Frequency      | Relatively rare             | Increasingly common              |
| Mitigation     | Relatively simple           | Requires advanced infrastructure |

#### DDoS Attack Operation

**Botnet Creation**

DDoS attacks typically operate through botnets:

1. **Infection Phase:** Attacker distributes malware to compromise multiple computers
2. **Zombie Creation:** Infected computers become "zombies" under attacker control
3. **Botnet Formation:** Thousands of compromised machines form a coordinated network
4. **Attack Activation:** Attacker sends command to activate simultaneous attacks

**Attack Execution**

```
Command Center (Attacker)
    ↓
Botnet Network (Compromised Computers)
    ├── Computer 1
    ├── Computer 2
    ├── Computer 3
    └── ... (thousands more)
    ↓
Target System
Result: Overwhelmed by coordinated traffic from thousands of sources
```

#### Historical DDoS Incidents

**Dyn Attack (2016)**

* **Target:** Dyn DNS service (Netflix, Twitter, Spotify, GitHub)
* **Botnet:** Mirai (100,000+ compromised IoT devices)
* **Traffic Volume:** 1.2 Tbps
* **Impact:** Approximately half the internet rendered inaccessible
* **Duration:** Several hours
* **Financial Impact:** Billions in losses

**GitHub Attack (2018)**

* **Volume:** 1.35 Tbps (largest recorded at the time)
* **Duration:** 17 minutes
* **Sources:** Multiple botnet sources
* **Response:** Cloudflare mitigation

**Cloudflare Attack (2014)**

* **Volume:** 400 Gbps
* **Duration:** Multiple weeks
* **Tactic:** Multi-layer attack approach
* **Impact:** Demonstrated evolving attack sophistication

#### DDoS Mitigation Strategies

**Individual/Small Organization Level**

* Implement Content Delivery Networks (CDNs)
* Configure firewall rate limiting
* Subscribe to DDoS protection services
* Maintain updated security infrastructure

**Enterprise Level**

| Solution                       | Function                               |
| ------------------------------ | -------------------------------------- |
| Rate Limiting                  | Blocks excessive requests from same IP |
| Web Application Firewall (WAF) | Filters malformed/suspicious requests  |
| CDN with DDoS Protection       | Distributes traffic, absorbs attacks   |
| Anycast Network                | Distributes traffic geographically     |
| SIEM/IDS                       | Detects attack patterns                |
| Blackhole Routing              | Discards all traffic during attack     |

**Advanced Mitigation**

**Scrubbing Centers:** Third-party services that filter traffic before reaching your infrastructure

```
Internet Traffic → Scrubbing Center (filters malicious traffic) → Your Server
```

#### Key DDoS Concepts

* Botnets are created through malware distribution
* DDoS attacks originate from victims' compromised devices
* Both attack targets and botnet members are victims
* Modern DDoS attacks operate at multiple layers simultaneously
* Effective defense requires layered approach

***

### On-Path Attacks (Man-in-the-Middle)

On-Path attacks, also known as Man-in-the-Middle (MitM) attacks, occur when an attacker intercepts communications between two parties without their knowledge.

**Attack Flow:**

```
User → [Attacker intercepts] → Server
All data passes through attacker before reaching destination
```

#### Attack Mechanism

1. User initiates connection to legitimate service
2. Attacker intercepts this connection
3. Data travels through attacker's system before reaching destination
4. Communication appears normal to both parties
5. Attacker gains access to all transmitted data

#### Attacker Capabilities in MitM Attacks

Once positioned between parties, attackers can:

* Steal passwords and credentials
* Capture financial information and bank details
* Read private messages and communications
* Modify information in transit
* Inject malicious content
* Impersonate either party

#### Attack Prerequisites

* Network access (same network as target)
* Ability to intercept traffic
* Ability to spoof legitimate services
* Technical knowledge of network protocols

***

### Password Attacks

assword attacks represent techniques to discover, crack, or bypass authentication credentials. Since username/password authentication remains the most common authentication method, it remains a primary attack target.

#### Password Attack Types

**Password Spraying**

Password spraying tests common passwords against multiple accounts:

**Characteristics:**

* Tests only a few common passwords (123456, qwerty, password)
* Attempts against many different accounts
* Avoids account lockout mechanisms

**Advantages for Attacker:**

* Bypasses account lockout policies
* Low detection probability
* Requires minimal computing resources

**Dictionary Attacks**

Dictionary attacks use pre-compiled lists of common passwords:

**Methodology:**

* Tests words from password dictionaries
* Includes common password variations
* More intelligent than random brute force
* Higher success rate against weak passwords

**Brute Force Attacks**

Brute force attacks attempt all possible password combinations:

**Characteristics:**

* Tests every combination: letters + numbers + symbols
* Slow but eventually effective (without adequate protections)
* Requires significant computational resources
* Guaranteed to eventually find password (if no protections)

**Rainbow Table Attacks**

Rainbow tables use precomputed hash tables:

**Methodology:**

* Uses tables with pre-calculated password hashes
* Compares target hashes against table
* Significantly faster than brute force
* Effective against unsalted passwords

**Traffic Interception**

Traffic interception captures passwords during transmission:

**Requirements:**

* Network access between user and service
* Absence of encryption or weak encryption
* Typically occurs on unsecured networks

**Examples:**

* Public Wi-Fi without security
* Compromised network infrastructure
* Unencrypted protocols (HTTP, FTP, Telnet)

#### Protection Against Password Attacks

* Strong, unique passwords for all accounts
* Multi-factor authentication (2FA/MFA)
* Password managers for secure storage
* Regular password changes when compromised
* Account lockout after failed attempts
* Encrypted authentication protocols (HTTPS, SSH)

***

### Exploits and Security Vulnerabilities

**Vulnerability:** Any defect in software or hardware that can be exploited to compromise system security.

**Exploit:** A program or technique specifically designed to take advantage of a known security vulnerability.

#### Hardware Vulnerabilities

Hardware vulnerabilities are flaws in physical computing components that cannot be corrected through software updates:

**Rowhammer**

Rowhammer exploits physical proximity of DRAM cells:

**Mechanism:**

* Repeatedly accesses specific memory addresses ("hammering")
* Causes interference between adjacent memory cells
* Can corrupt data in nearby memory locations
* Particularly dangerous in shared systems

**Impact:**

* Data corruption in critical applications
* Privilege escalation opportunities
* Difficult to detect and prevent

**Meltdown and Spectre**

Discovered by Google researchers, these vulnerabilities affect CPUs manufactured since 1995:

**Meltdown:**

* Reads entire system memory
* Affects Intel and ARM processors
* Allows access to all data in memory
* Requires patches at operating system level

**Spectre:**

* Accesses data from other running programs
* Affects most modern processors
* More difficult to patch completely
* Ongoing research into mitigations

**Characteristics:**

* Depend on specific hardware implementations
* More commonly used in targeted attacks
* Can be executed multiple times without detection
* Difficult to detect through standard monitoring

**Protection for Users:**

* Keep systems fully updated
* Apply microcode patches from manufacturers
* Monitor for suspicious activity
* Consider disabling certain performance features for maximum security

#### Software Vulnerabilities

Software vulnerabilities result from coding errors and insecure practices in programs and operating systems:

**Attacker Capabilities:**

* Unauthorized system access
* Remote command execution
* Complete system control

**Example: SYNful Knock**

**Vulnerability:** Affected enterprise routers

**Attack Vector:** Installation of modified system firmware

**Impact:**

* Complete network monitoring capability
* Ability to infect other connected devices
* Persistent network-level compromise

**Prevention:**

* Verify integrity of downloaded files
* Restrict physical device access
* Maintain current system updates
* Download software only from official sources

#### Software Vulnerability Categories

Common software vulnerabilities typically result from programming errors and insecure practices:

| Vulnerability Type | Problem                            | Typical Cause                |
| ------------------ | ---------------------------------- | ---------------------------- |
| Buffer Overflow    | Excessive data written to memory   | Inadequate input validation  |
| Unvalidated Input  | Malicious data accepted            | Missing input sanitization   |
| Race Condition     | Timing-related errors              | Asynchronous operation flaws |
| Weak Practices     | Inadequate security implementation | Poor coding standards        |
| Access Control     | Incorrect permission settings      | Misconfiguration             |

#### Software Updates and Patches

**Purpose:** Correct identified vulnerabilities and maintain system security

**Major Update Providers:**

* Microsoft (Windows, Office, Edge)
* Apple (macOS, iOS, Safari)
* Adobe (Creative Suite, Reader)
* Mozilla (Firefox)
* Google (Chrome, Android)
* Linux distributions

**Criticality:** Regular updates are essential because:

* New vulnerabilities are discovered continuously
* Attackers exploit known vulnerabilities rapidly
* Unpatched systems represent easy targets

**Vulnerability Discovery:**

| Source                  | Role                           | Examples                    |
| ----------------------- | ------------------------------ | --------------------------- |
| Companies               | Internal research teams        | Microsoft Security Research |
| Independent Researchers | Security community             | Individual security experts |
| Specialized Teams       | Focused vulnerability research | Google Project Zero         |

**Project Zero:** Google's dedicated team focused on finding and responsibly disclosing zero-day vulnerabilities across all major platforms.

***

### Cryptocurrency and Cybersecurity

Cryptocurrency is digital money protected by cryptography. It enables:

* Purchasing products and services
* Money transfers
* Payment for services
* Investment and trading

#### Key Components

**Digital Wallets:** Secure storage locations for cryptocurrency holdings

**Blockchain:** Public, decentralized ledger recording all transactions

**Mining:** Process where miners verify transactions by solving mathematical problems

**Independence:** Operates without reliance on banks or government institutions

#### Transaction Process

```
User initiates transaction
    ↓
Transaction broadcasts to network
    ↓
Miners verify transaction legitimacy
    ↓
Transaction recorded in blockchain
    ↓
Transaction complete and permanent
```

#### Cryptojacking

Cryptojacking occurs when attackers use victims' devices to mine cryptocurrency without authorization:

**Characteristics:**

* Does not directly steal data (unlike other malware)
* Does not crash or disable systems
* Silently uses system resources for attacker profit
* Generates continuous passive income for attacker

**Impact:**

* Reduced system performance
* Increased electricity consumption
* Hardware degradation through prolonged high usage
* Device battery drain

**Detection:**

* Unusual CPU usage without user activity
* Elevated system temperatures
* Faster battery drain on mobile devices
* Performance degradation

***

### Key Takeaways

* Malware encompasses diverse threats requiring different detection strategies
* Social engineering exploits human psychology more effectively than technical attacks
* Distributed attacks (DDoS) originate from compromised user devices
* Multiple attack vectors (password, protocol, application layer) require layered defenses
* Hardware and software vulnerabilities require different mitigation approaches
* Understanding attack methodologies enables effective defensive strategies

***

### Related Concepts

The concepts covered in this module interconnect with other security domains:

* **Malware Distribution:** Often uses social engineering for initial compromise
* **Botnet Creation:** Basis for DDoS attacks and cryptojacking
* **Vulnerability Exploitation:** Enables malware delivery and persistence
* **Defense in Depth:** Required to counter multiple simultaneous attack vectors

***

### Module Summary

Module 2 has covered the primary attack methodologies used in modern cyber threats. Understanding these attack techniques is essential for developing effective defensive strategies covered in subsequent modules.

**Key Learning Outcomes:**

* Identify different malware types and their characteristics
* Recognize social engineering attack patterns
* Understand DoS and DDoS attack mechanisms
* Comprehend password attack methodologies
* Understand hardware and software vulnerabilities

**Next Steps:** Module 3 addresses protective measures and defensive strategies to counter the attacks described in this module.
