# Changelog

All notable changes to this project are documented in this file.

## v1.0.0 - Initial Release

### Added
- Azure Resource Group deployment
- Ubuntu Linux Virtual Machine
- Windows Server Virtual Machine
- Windows 11 Virtual Machine
- Virtual Network and Subnet
- Network Security Groups
- Nginx installation on Ubuntu
- IIS installation on Windows Server
- Public connectivity validation
- Comprehensive project documentation

### Fixed
- Resolved Azure VM SKU availability issues by selecting supported VM sizes.
- Worked around regional capacity restrictions by deploying to a supported Azure region.
- Resolved SSH authentication issues by generating and configuring RSA keys.
- Corrected Windows VM naming constraints.
- Configured NSG inbound rules to allow HTTP traffic.
- Removed Azure resources after validation to minimize cloud costs.