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