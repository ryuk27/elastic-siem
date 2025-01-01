# Elastic Stack SIEM Home Lab

The project explains how to set up a home lab for Elastic Stack Security Information and Event Management (SIEM) using the Elastic Web portal and a Kali Linux VM. You'll also learn to generate security events on the Kali VM, configure an agent to send data to the SIEM, and analyze the logs effectively.


## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Overview of Tasks](#overview-of-tasks)
3. [Task 1: Set up an Elastic Account](#task-1-set-up-an-elastic-account)
4. [Task 2: Setting up the Linux VM](#task-2-setting-up-the-linux-vm)
5. [Task 3: Setting up the Agent to Collect Logs](#task-3-setting-up-the-agent-to-collect-logs)
6. [Task 4: Generating Security Events on the Kali VM](#task-4-generating-security-events-on-the-kali-vm)
7. [Task 5: Querying for Security Events in the Elastic SIEM](#task-5-querying-for-security-events-in-the-elastic-siem)
8. [Task 6: Create a Dashboard to Visualize Events](#task-6-create-a-dashboard-to-visualize-events)
9. [Task 7: Create an Alert](#task-7-create-an-alert)
10. [Conclusion](#conclusion)

---

## Prerequisites
Before starting, ensure you have:
- VirtualBox or VMware
- Basic knowledge of Linux and virtualization software

---

## Overview of Tasks
1. Set up a free Elastic account.
2. Install the Kali VM.
3. Configure the Elastic Agent on the Linux VM to collect and forward logs.
4. Generate security events on the Kali VM.
5. Query for security events in the Elastic SIEM.
6. Create a Dashboard to visualize security events.
7. Create alerts for security events.

---

## Task 1: Set up an Elastic Account
1. Sign up at [Elastic Cloud](https://cloud.elastic.co/registration).
2. Log in to the Elastic Cloud console.
3. Click “Start your free trial.”
4. Create a deployment and select “Elasticsearch” as the deployment type.
5. Choose a region and deployment size, then create the deployment.
6. Wait for configuration to complete.
![image](https://github.com/user-attachments/assets/ff852ec4-5f72-429d-b220-3a75ce4f18ed)

---

## Task 2: Setting up the Linux VM
1. Download the Kali Linux VM from [Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines).
2. Create a new VM using VirtualBox or VMware.
3. Start the VM and follow the prompts to install Kali Linux.
4. Log in using credentials: `kali` (username) and `kali` (password).
![image](https://github.com/user-attachments/assets/56a27b1a-861b-4255-8e41-ee2367c9bc80)

---

## Task 3: Setting up the Agent to Collect Logs
1. Log in to the Elastic SIEM instance.
2. Navigate to “Integrations” and search for “Elastic Defend.”
![image](https://github.com/user-attachments/assets/2d0af930-a9a3-400d-8b7b-ace691f1e51e)

3. Install the Elastic Defend agent on your Kali VM.
4. Run the command provided in the Elastic portal on your Kali terminal.
![Screenshot 2025-01-01 010538](https://github.com/user-attachments/assets/79abe86f-a807-4d0a-98b3-f9c559329906)

![Screenshot 2025-01-01 010812](https://github.com/user-attachments/assets/513a53e1-9b51-4736-999c-dbe6058f40ac)

5. Verify installation using: `sudo systemctl status elastic-agent.service`.
![Screenshot 2025-01-01 011025](https://github.com/user-attachments/assets/21c6e477-73bb-419c-ab2f-e9a2e52c50fd)

---

## Task 4: Generating Security Events on the Kali VM
1. Ensure Nmap is installed (`sudo apt-get install nmap` if not preinstalled).
2. Run Nmap scans (`sudo nmap <ip-address>`) to generate security events.
3. Experiment with various Nmap commands like:
   - `nmap -sS <ip-address>`
   - `nmap -sT <ip-address>`
   - `nmap -p- <ip-address>`
![Screenshot 2025-01-01 011757](https://github.com/user-attachments/assets/0bbb9769-8a76-4074-9222-6c503f686cba)

---

## Task 5: Querying for Security Events in the Elastic SIEM
1. Navigate to “Logs” under “Observability” in your Elastic deployment.
2. Use queries like `event.action: "nmap_scan"` or `process.args: "sudo"`.
3. View and analyze the results in the logs table.

---

## Task 6: Create a Dashboard to Visualize Events
1. Go to “Dashboards” under “Analytics” in the Elastic web portal.
2. Create a new dashboard and add visualizations.
![image](https://github.com/user-attachments/assets/07c179af-05bf-45b2-8b4d-00b6ad517878)

3. Use metrics like “Count” (vertical field) and “Timestamp” (horizontal field).
4. Save your dashboard for future use.
![image](https://github.com/user-attachments/assets/3747c62e-4787-4c4e-a211-5dd0eaa8373e)

---

## Task 7: Create an Alert
1. Navigate to “Alerts” under “Security.”
2. Create a custom rule with conditions for Nmap scan events.
![Screenshot 2025-01-01 014449](https://github.com/user-attachments/assets/7bc27fee-a1a4-4dff-93e5-a39e775f6c8d)

![Screenshot 2025-01-01 014520](https://github.com/user-attachments/assets/6e535ebd-51aa-4ef9-b51e-d902df7b7f4f)

3. Define actions like sending notifications or triggering webhooks.
![Screenshot 2025-01-01 014601](https://github.com/user-attachments/assets/278841bd-68b2-4ae1-a44f-c8747489b013)

4. Enable the rule to monitor logs and trigger alerts for specific events.
![Screenshot 2025-01-01 014614](https://github.com/user-attachments/assets/8f55b49a-314f-474b-a4ff-55e3f8a25028)

![Screenshot 2025-01-01 014729](https://github.com/user-attachments/assets/d19ae116-aeb2-42a9-8452-a2721197370b)


6. Final Outcome
![Screenshot 2025-01-01 122235](https://github.com/user-attachments/assets/54e49566-e58a-47f4-9e67-850a020335bc)


---

## Conclusion
The project provides a hands-on approach to setting up a SIEM home lab using Elastic Stack and Kali Linux. It equips you with practical skills for configuring, monitoring, and analyzing security events.
