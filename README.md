# ASR Rule Inspector

## Overview

The **ASR Rule Inspector** is a PowerShell script designed to inspect and report on Attack Surface Reduction (ASR) rules, Controlled Folder Access (CFA) configurations, and Intune policy assignments for devices managed by Microsoft Intune. It provides detailed insights into ASR rules, exclusions, CFA settings, and policy assignments, comparing Intune configurations with local device settings.

## Features

- **Administrative Privilege Check**: Ensures the script is run with elevated permissions.
- **Microsoft Graph API Integration**: Connects to Microsoft Graph API to retrieve Intune policies, configurations, and device data.
- **ASR Rule Inspection**:
    - Retrieves ASR rules configured in Intune.
    - Compares Intune ASR configurations with local device settings.
    - Identifies duplicates, conflicts, and mismatches in ASR rules and exclusions.
    - Retrieves and compares per-rule ASR exclusions.
- **CFA Configuration Analysis**:
    - Retrieves and compares CFA settings from Intune and local devices.
    - Reports on protected folders and allowed applications.
- **Intune Policy Assignment Evaluation**:
    - Evaluates Intune assignment filters against device properties.
    - Checks if specific Intune policies are assigned to a device.
- **HTML Report Generation**: Creates a detailed, interactive HTML report summarizing findings.

## Prerequisites

- **PowerShell 5.1 or later**.
- **Microsoft Graph PowerShell SDK**: The script installs required modules automatically.
- **Administrative Privileges**: The script must be run as an administrator.

## Installation

1. Clone the repository:
     ```bash
     git clone https://github.com/royklo/ASR-Rule-Inspector.git
     ```
2. Navigate to the script directory:
     ```bash
     cd ASR-Rule-Inspector
     ```

## Usage

1. Open PowerShell as an administrator.
2. Run the script:
     ```powershell
     .\ASR-Rule-Inspector v2.ps1
     ```
    <img src="assets/report.gif" alt="ASR Rule Inspector Report" width="80%">

## Parameters

The script does not require any parameters. It automatically retrieves data from Intune and the local device.

## Functions

### Core Functions

- **Test-AdminElevation**: Verifies if the script is running with administrative privileges.
- **Install-Requirements**: Installs and imports required PowerShell modules for Microsoft Graph API.
- **Test-MgGraphConnection**: Establishes a connection to Microsoft Graph API with the necessary scopes.
- **New-HTMLReport**: Generates an HTML report summarizing ASR rules, exclusions, CFA configurations, and policy assignments.

### ASR Rule Functions

- **Get-IntuneConfiguredASRRules**: Retrieves ASR rules configured in Intune policies.
- **Find-DuplicateASRRules**: Identifies duplicate or conflicting ASR rules in Intune configurations.
- **Get-ASRStatus**: Compares Intune ASR configurations with local device ASR settings.
- **Get-ASRStatusExclusions**: Retrieves and compares ASR exclusions from Intune and local device settings.
- **Get-ASRPerRuleStatusExclusions**: Retrieves and compares per-rule ASR exclusions from Intune and local device settings.

### CFA Functions

- **Get-CFAStatus**: Retrieves and compares Controlled Folder Access (CFA) configurations from Intune and local device settings.

### Device and Policy Functions

- **Get-IntuneDeviceData**: Retrieves detailed device properties from Intune.
- **Test-IntuneFilter**: Evaluates Intune assignment filters against device properties.
- **Test-DevicePolicyAssignment**: Checks if a specific Intune policy is assigned to a device.

## Output

The script generates an interactive HTML report with the following sections:

- **ASR Rules**: Displays ASR rules and their statuses.
- **Duplicate/Conflicting ASR Rules**: Highlights duplicate or conflicting ASR rules.
- **ASR Rule Exclusions**: Lists ASR exclusions and their statuses.
- **Per-Rule ASR Exclusions**: Summarizes per-rule ASR exclusions and their statuses.
- **Controlled Folder Access**: Summarizes CFA configurations and their statuses.
- **Policy Assignments**: Evaluates Intune policy assignments and filters for the device.

## Notes

- **Author**: Roy Klooster  
- **Version**: 3.0  
- **Date**: 2025  

For more information, visit the [GitHub repository](https://github.com/royklo/ASR-Rule-Inspector).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
