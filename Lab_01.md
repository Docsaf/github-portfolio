# Lab 01: Infrastructure Audit
**Name:** [Dr. Safi]
**Date:** [01/26/2026]
**Status:** In Progress

## 🎯 Objective
To document the 2021 Facebook outage and practice using GitHub for enterprise documentation.

## 🛠️ Tools Used
* **Git Bash:** For version control.
* **VS Code:** For editing Markdown files.
* **GitHub:** For hosting the repository.

---
### 🔬 Case Study Deep Dive: The Facebook BGP Outage
**Incident Date:** October 4, 2021
**Duration:** ~6 Hours

#### 1. The Root Cause (BGP Withdrawal)
The outage began when a routine maintenance command was issued to assess global backbone capacity. This command unintentionally disconnected Facebook’s data centers from the wider internet.
* **Technical Explanation:** The command caused Facebook's routers to withdraw their **BGP (Border Gateway Protocol)** advertisements.
* **The Result:** BGP acts as the "GPS of the Internet." When the routes were withdrawn, the rest of the internet (ISPs, browsers) suddenly had no map to find `facebook.com`.

#### 2. The Cascading Failure (DNS)
Because the BGP routes were gone, Facebook's **DNS (Domain Name System)** servers became unreachable.
* **Symptom:** Users saw "NXDOMAIN" errors (domain not found) because their browsers couldn't resolve the IP address for Facebook, Instagram, or WhatsApp.
* **Confusion:** To the outside world, it looked like Facebook had been deleted from the internet entirely.

#### 3. The Recovery Challenge (Locked Out)
Recovery was delayed because the network failure cut off the engineers' remote access tools.
* **The "Locked Keys" Problem:** Engineers could not remotely log in to the routers to fix the bad configuration because the network was down.
* **Physical Security:** Even physical access was hampered because the electronic badge readers on the server room doors relied on the network to verify credentials. Engineers had to physically break into cages or use backup keys to access the hardware.

#### 4. Prevention Takeaway
This incident highlights the importance of **Out-of-Band Management (OOB)**. Critical infrastructure should always have a backup access method (like a separate modem or distinct network line) that does not rely on the primary network being up.

## 💡 Lessons Learned
I learned that **Configuration Management** is critical. In the future, automated checks should be in place to prevent a single bad command from taking down an entire network.

## 📸 Proof of Work
*(We will add a screenshot here in the next step)*
![My Terminal Success](terminal.png)