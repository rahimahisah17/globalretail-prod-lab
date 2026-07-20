# Global Retail Production Infrastructure Lab

## Project Overview

This project demonstrates the deployment of a production-style Azure infrastructure using Azure CLI. The environment consists of Linux and Windows virtual machines deployed within the same virtual network, configured as web servers, secured with Network Security Groups (NSGs), and validated through end-to-end connectivity testing.

Unlike a guided lab with perfect conditions, this project involved troubleshooting real Azure platform limitations including regional VM capacity constraints, subscription quotas, SSH authentication issues, and networking configuration challenges.

---

## Objectives

- Provision Azure resources using Azure CLI
- Deploy Linux and Windows virtual machines
- Configure a shared Virtual Network
- Deploy a highly available Windows VM
- Install and configure Nginx on Ubuntu
- Install IIS on Windows Server
- Configure NSG rules for HTTP access
- Validate public connectivity
- Document troubleshooting and resolutions

---

## Architecture

- Resource Group
- Virtual Network
- Network Security Groups
- Ubuntu Linux VM
- Windows Server VM
- Windows 11 VM (Availability Zone)
- Nginx
- IIS

---

## Azure Infrastructure

| Resource | Name |
|----------|------|
| Resource Group | rg-globalretail-prod-001 |
| Region | West Europe |
| Linux VM | vm-linux-web-01 |
| Windows Server VM | vm-win-admin01 |
| Windows 11 VM | vm-win11-ha |
| Virtual Network | vm-linux-web-01VNET |
| Subnet | vm-linux-web-01Subnet |

---

## Technologies Used

- Microsoft Azure
- Azure CLI
- Ubuntu Server 22.04 LTS
- Windows Server 2022
- Windows 11 Pro
- Azure Virtual Network (VNet)
- Network Security Groups (NSGs)
- Availability Zones
- Nginx
- IIS
- SSH
- Remote Desktop Protocol (RDP)

---

## Deployment Summary

The environment was provisioned entirely using Azure CLI. The deployment included:

- Creating a Resource Group
- Deploying an Ubuntu Linux VM
- Deploying a Windows Server VM
- Deploying a highly available Windows 11 VM in an Availability Zone
- Connecting all virtual machines to the same Virtual Network
- Installing Nginx on Linux
- Installing IIS on Windows Server
- Configuring NSG rules for HTTP traffic
- Verifying public access to both web servers

---

# Challenges Encountered and Resolutions

This project presented several real-world Azure deployment challenges. Each issue was investigated and resolved before the deployment was completed successfully.

| Challenge | Resolution |
|-----------|------------|
| VM SKU unavailable in East US | Switched deployment to West Europe after verifying available capacity. |
| Standard_B1s and Standard_B2s unavailable | Queried Azure for supported VM sizes and selected Standard_D2s_v3. |
| DSv5 quota restrictions | Avoided restricted VM families by choosing a supported SKU. |
| Azure CLI returned "The content for this response was already consumed" | Identified this as an Azure CLI error while using the underlying deployment error to continue troubleshooting. |
| Windows VM name exceeded 15 characters | Renamed the VM to comply with Windows computer name limits. |
| SSH authentication failed | Generated a new RSA key pair locally and added the public key to the Linux VM. |
| Windows 11 deployment failed due to subnet conflict | Attached the VM to the existing subnet instead of allowing Azure to create another default subnet. |
| IIS installation initially failed | Connected through Remote Desktop and installed IIS from PowerShell running inside the Windows Server VM. |
| Public HTTP access unavailable | Created inbound NSG rules allowing TCP port 80 and verified connectivity from a browser. |

---

## Key Skills Demonstrated

- Azure Infrastructure Provisioning
- Azure CLI Automation
- Virtual Machine Deployment
- Virtual Networking
- Network Security Groups (NSGs)
- Availability Zones
- Linux Administration
- Windows Server Administration
- IIS Configuration
- Nginx Configuration
- SSH Authentication
- Azure Troubleshooting
- Cloud Networking
- Infrastructure Documentation

---

# Deployment Walkthrough

## 1. Created the Resource Group

The deployment began by creating a dedicated Azure Resource Group to contain all resources for the project.

**Screenshot**

![Resource Group](screenshots/07-resource-group.png)

---

## 2. Provisioned the Ubuntu Linux Virtual Machine

A Linux virtual machine running Ubuntu Server 22.04 LTS was deployed using Azure CLI.

**Screenshot**

![Linux VM](screenshots/08-linux-vm-created.png)

---

## 3. Provisioned the Windows Server Virtual Machine

A Windows Server virtual machine was created to host IIS.

**Screenshot**

![Windows Server VM](screenshots/09-windows-server-vm.png)

---

## 4. Provisioned a Highly Available Windows 11 VM

A Windows 11 Pro virtual machine was deployed into an Availability Zone while sharing the existing Virtual Network.

**Screenshot**

![Windows 11 VM](screenshots/10-windows11-ha.png)

---

## 5. Installed Nginx on Ubuntu

After connecting to the Linux VM using SSH, Nginx was installed and verified.

**Screenshot**

![Nginx Installed](screenshots/11-nginx-installed.png)

---

## 6. Installed IIS on Windows Server

Using Remote Desktop and PowerShell, IIS was installed successfully.

**Screenshot**

![IIS Installed](screenshots/12-iis-installed.png)

---

## 7. Configured Network Security Groups

Inbound HTTP (TCP/80) rules were added to allow public access to the web servers.

**Screenshot**

![NSG Rules](screenshots/13-nsg-http-rule.png)

---

## 8. Verified Public Connectivity

Both Nginx and IIS were successfully accessed through their public IP addresses using a web browser.

**Screenshot**

![Browser Verification](screenshots/14-browser-test.png)

---

# Validation

After deployment, the infrastructure was validated to confirm that all components were functioning correctly.

## Validation Performed

- Successfully connected to the Ubuntu VM using SSH.
- Installed and verified the Nginx service.
- Successfully connected to the Windows Server VM using Remote Desktop.
- Installed IIS using PowerShell.
- Configured Network Security Groups to allow inbound HTTP traffic (TCP/80).
- Verified that both the Linux and Windows web servers were publicly accessible through their respective public IP addresses.

---

# Lessons Learned

This project provided practical experience beyond simply provisioning Azure resources. It reinforced the importance of understanding Azure regional capacity, subscription quotas, virtual networking, authentication methods, and systematic troubleshooting.

Key takeaways include:

- Azure regions may not always have capacity for every VM SKU.
- VM family quotas can prevent deployments even when a subscription is active.
- Azure CLI error messages may hide the underlying issue, requiring careful investigation.
- SSH key management is essential when administering Linux virtual machines.
- Windows virtual machines have naming constraints that must be considered during deployment.
- Proper Network Security Group configuration is required before workloads become publicly accessible.
- Cleaning up Azure resources promptly helps prevent unnecessary costs.

---

# Cleanup

After validating the environment, all Azure resources were deleted to avoid ongoing charges.

Resources removed included:

- Resource Group
- Virtual Machines
- Virtual Network
- Network Security Groups
- Public IP Addresses
- Network Interfaces
- Managed Disks

This reflects cloud cost management best practices.

---

# Conclusion

This project demonstrates the end-to-end deployment of a production-style Azure environment using Azure CLI. In addition to provisioning Linux and Windows virtual machines, the implementation included web server configuration, network security, high availability concepts, connectivity validation, and troubleshooting of real Azure platform limitations. The experience strengthened practical Azure administration skills while reinforcing operational excellence and cost-conscious resource management.

---

# Repository Structure

```
globalretail-prod-lab/
├── README.md
├── docs/
└── screenshots/
```

---

# Skills Demonstrated

- Microsoft Azure
- Azure CLI
- Infrastructure as Code (CLI-based)
- Virtual Machines
- Linux Administration
- Windows Server Administration
- Windows 11 Administration
- Azure Networking
- Virtual Networks (VNets)
- Subnets
- Network Security Groups
- Availability Zones
- SSH
- Remote Desktop Protocol (RDP)
- Nginx
- IIS
- Infrastructure Troubleshooting
- Cloud Cost Management

---

# Author

**Rahimah Sulayman**

Cloud Engineer | Azure | Kubernetes | DevOps

GitHub: https://github.com/rahimahisah17
LinkedIn: https://www.linkedin.com/in/rahimah-sulayman