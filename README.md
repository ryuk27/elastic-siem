# Elastic Stack SIEM Home Lab Guide

This guide explains how to set up a home lab for Elastic Stack Security Information and Event Management (SIEM) using the Elastic Web portal and a Kali Linux VM. You'll also learn to generate security events on the Kali VM, configure an agent to send data to the SIEM, and analyze the logs effectively.


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

---

## Task 2: Setting up the Linux VM
1. Download the Kali Linux VM from [Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines).
2. Create a new VM using VirtualBox or VMware.
3. Start the VM and follow the prompts to install Kali Linux.
4. Log in using credentials: `kali` (username) and `kali` (password).

---

## Task 3: Setting up the Agent to Collect Logs
1. Log in to the Elastic SIEM instance.
2. Navigate to “Integrations” and search for “Elastic Defend.”
3. Install the Elastic Defend agent on your Kali VM.
4. Run the command provided in the Elastic portal on your Kali terminal.
5. Verify installation using: `sudo systemctl status elastic-agent.service`.

---

## Task 4: Generating Security Events on the Kali VM
1. Ensure Nmap is installed (`sudo apt-get install nmap` if not preinstalled).
2. Run Nmap scans (`sudo nmap <ip-address>`) to generate security events.
3. Experiment with various Nmap commands like:
   - `nmap -sS <ip-address>`
   - `nmap -sT <ip-address>`
   - `nmap -p- <ip-address>`

---

## Task 5: Querying for Security Events in the Elastic SIEM
1. Navigate to “Logs” under “Observability” in your Elastic deployment.
2. Use queries like `event.action: "nmap_scan"` or `process.args: "sudo"`.
3. View and analyze the results in the logs table.

---

## Task 6: Create a Dashboard to Visualize Events
1. Go to “Dashboards” under “Analytics” in the Elastic web portal.
2. Create a new dashboard and add visualizations.
3. Use metrics like “Count” (vertical field) and “Timestamp” (horizontal field).
4. Save your dashboard for future use.

---

## Task 7: Create an Alert
1. Navigate to “Alerts” under “Security.”
2. Create a custom rule with conditions for Nmap scan events.
3. Define actions like sending notifications or triggering webhooks.
4. Enable the rule to monitor logs and trigger alerts for specific events.

---

## Conclusion
This guide provides a hands-on approach to setting up a SIEM home lab using Elastic Stack and Kali Linux. It equips you with practical skills for configuring, monitoring, and analyzing security events.
