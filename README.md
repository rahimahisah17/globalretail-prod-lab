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