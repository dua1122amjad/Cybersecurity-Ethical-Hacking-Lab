# Cybersecurity-Ethical-Hacking-Lab
Practical cybersecurity lab environment using VirtualBox, Kali Linux, Windows VMs, NAT networking, IP configuration, connectivity testing, and VM snapshots.
#  Cybersecurity & Ethical Hacking Lab Environment
##  Overview

This repository documents my hands-on setup of a practical Cybersecurity, Ethical Hacking, and Penetration Testing Lab Environment using virtual machines and VirtualBox.

The lab was created as an isolated environment for practicing cybersecurity concepts, network configuration, ethical hacking techniques, penetration testing, and future CTF-based exercises.

The setup follows a two-phase approach covering the installation and configuration of VirtualBox, Kali Linux, Windows virtual machines, network configuration, IP addressing, connectivity testing, and VM snapshots.

##  Lab Objectives

- Build an isolated cybersecurity practice environment.
- Configure VirtualBox networking using a custom NAT Network.
- Install and configure Kali Linux.
- Configure Windows virtual machines for security testing.
- Assign and verify IP configurations.
- Test connectivity between virtual machines.
- Create VM snapshots for safe experimentation and rollback.
- Prepare the environment for future CTF and penetration-testing labs.

---

##  Lab Environment & Specifications

### Virtualization
- **Hypervisor:** Oracle VirtualBox
- **Archive Utility:** 7-Zip
- **Virtual Machines:** Multiple Virtual Machines

### Operating Systems
- **Attacker OS:** Kali Linux (`kali-linux-2026.2-virtualbox-amd64`)
- **Target OS:** Windows 10/11/7, Android VM (optional)

### Network
- **Network Type:** NAT Network (`NatNetwork`)
- **Network Subnet:** `10.0.0.0/24`
- **Configured IP Range:** `10.0.0.2` – `10.0.0.99`

---
##  Network Topology

The general lab architecture is structured as follows:

```text
                 Host Machine
                     |
               VirtualBox
                     |
              NAT Network
             10.0.0.0/24
                     |
       +-------------+-------------+
       |             |             |
     Kali         Windows       Android
   Linux VM         VM            VM
       |             |             |
       +-------------+-------------+
              Connectivity Tests

 ##  Example IP Configuration

The lab uses the 10.0.0.0/24 network. Example addresses from the lab setup include:

| Machine | Example IP |
| :--- | :--- |
| **Kali Linux** | `10.0.0.2` |
| **VM 2** | `10.0.0.10` |
| **VM 3** | `10.0.0.7` |
| **VM 4** | `10.0.0.16` |
| **VM 5** | `10.0.0.9` |
| **VM 6** | `10.0.0.11` |
## ⚙️ Phase 1 – Kali Linux Setup & Proof of Work

### Step 1: Install 7-Zip & Setup VirtualBox
7-Zip was installed to extract and manage downloaded virtual machine files. Oracle VirtualBox was installed as the virtualization platform. The Kali Linux VM (`kali-linux-2026.2-virtualbox-amd64`) was imported with 2048 MB RAM and 2 Processors allocated.
<p align="center">
  <img src="Screenshot (90).png" alt="VirtualBox Setup" width="600" height="337" />
</p>

---

### Step 2: Configure Custom NAT Network
A custom NAT Network named `NatNetwork` was created in VirtualBox using the `10.0.0.0/24` IPv4 CIDR prefix with DHCP enabled.

![NAT Network Configuration] <img width="600" height="337" alt="Screenshot (94)" src="https://github.com/user-attachments/assets/75f5c99f-f4ff-4f8c-9842-d44dccdfef51" />


---

### Step 3: Configure Kali Linux Network Connection
Kali Linux was configured manually to communicate through the custom NAT Network with static parameters:
- **IPv4 Address:** `10.0.0.2`
- **Netmask:** `24` (`255.255.255.0`)
- **Gateway:** `10.0.0.1`
- **DNS Server:** `8.8.8.8`

![Wired Connection Settings] <img width="600" height="337" alt="Screenshot (95)" src="https://github.com/user-attachments/assets/f33a6de7-6051-4bf7-b385-a0464832896b" />


---

### Step 4: Verify IP Interface Configuration
Assigned IPv4 configurations were verified inside the Kali Linux terminal using `ip a`. The `eth0` network adapter successfully bound to `10.0.0.2/24`.

![IP Configuration Verification]<img width="600" height="337" alt="Screenshot (96)" src="https://github.com/user-attachments/assets/74110e1a-7f6b-4464-b553-f46b4968f93e" />


---

### Step 5: Test Connectivity & Network Routing
Tested internet reachability and NAT gateway routing inside Kali Linux by accessing external web destinations via the browser.

![Connectivity Test] <img width="600" height="337" alt="Screenshot (97)" src="https://github.com/user-attachments/assets/614c996e-79e4-46c7-bf22-4b7200f28a02" />


---

### Step 6: Create VM Snapshot
A snapshot of the configured Kali Linux VM was created to provide a restore point before performing security experiments. The snapshot was named **`Kali setup`** with the description *"Setting up IP address"*.

![VirtualBox Snapshot] <img width="600" height="337" alt="Screenshot (98)" src="https://github.com/user-attachments/assets/b85871b1-12ac-41bd-9dae-60b53654d37f" />



