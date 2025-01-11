<p align="center">
<img src="https://www.theforage.com/blog/wp-content/uploads/2022/12/what-is-cybersecurity-1024x631.jpg"/>
</p>

<h1>Creating a Security Operations Center in Microsoft Azure <a href="https://medium.com/@ubuu751/creating-a-security-operations-center-in-microsoft-azure-99eaf414adf0">Link To Article on Medium.com</a></h1>

# # Lab Setup Diagram
<img src="Azure Cloud SOC.png"/>

# Setting Up and Securing a Cloud-Based Security Operations Center with Azure

## Abstract

This lab explores the implementation of a Security Operations Center (SOC) using Microsoft Azure. By configuring Azure Sentinel, Log Analytics Workspace, and Azure resources (such as Virtual Machines, SQL Databases, Blob Storage, and Key Vault), the lab demonstrates monitoring, detecting, and responding to security incidents. Simulated attacks are used to observe and evaluate system vulnerabilities and defensive responses.

---

## Introduction

The objective of this lab is to simulate the setup of a SOC using Microsoft Azure to monitor and secure cloud-based resources. The key goals include:

- Centralizing logs from multiple resources.
- Using Azure Sentinel as the SIEM (Security Information and Event Management) tool.
- Implementing security controls to reduce vulnerabilities and ensure compliance with NIST frameworks.

---

## Materials and Methods

### Materials
- Microsoft Azure subscription
- Azure Sentinel
- Windows and Linux virtual machines
- SQL Database, Blob Storage, and Key Vault

### Methods

#### Environment Setup
- Created Windows and Linux Virtual Machines with open internet access to simulate honeypots.
- Configured SQL Database, Blob Storage, and Key Vault to mimic real-world organizational resources.

#### Log Collection
- Centralized logs from all resources using Azure Log Analytics Workspace.

#### Security Monitoring
- Connected Log Analytics Workspace to Azure Sentinel for advanced monitoring and incident management.
- Configured Activity Logs to track administrative actions.

#### Threat Simulation
- Opened virtual machines to simulate attacks (e.g., brute force logins) from external actors.
- Monitored all activities and logged events in Log Analytics Workspace.

#### Querying Logs
- Used KQL (Kusto Query Language) to analyze failed login attempts and identify malicious activities (e.g., filtering for EventID 4625 for failed logins).

#### Lockdown Measures
- Applied NIST 800-53 controls (e.g., SC-7 for boundary protection).
- Restricted Blob Storage access using virtual network rules.
- Configured additional Network Security Groups (NSGs) to isolate and protect resources.

#### Performance Comparison
- Compared security events before and after implementing lockdown measures to evaluate the effectiveness of the SOC.

---

## Results

### Initial State
- Open VMs and resources attracted numerous unauthorized access attempts.
- Over 11,000 security events were recorded within 24 hours.

### Post-Lockdown
- Applied controls reduced unauthorized attempts by approximately 20%, as observed through decreased security events.

### KQL Queries
- Identified patterns in failed login attempts and highlighted IP addresses responsible for malicious activities.

### Incident Mapping
- Azure Sentinel generated geographical maps showing attack origins, aiding in situational awareness.

---

## Discussion

This lab demonstrates the effectiveness of an Azure-based SOC in detecting, analyzing, and mitigating security threats. Key observations include:

- The critical role of centralized logging and analysis in threat detection.
- The value of proactive measures (e.g., NSGs, access restrictions) in reducing attack surfaces.
- The flexibility and scalability of Azure Sentinel for managing security incidents.

### Limitations
- Only a limited number of resources were monitored. Expanding the SOC to include additional data sources and advanced automation would further enhance its capabilities.

---

## Conclusion

The Azure-based SOC effectively centralized monitoring, reduced vulnerabilities, and provided actionable insights into security events. The lab underscores the importance of integrating security tools and frameworks to build a resilient cloud environment.

---

## References

- Hazard, Dennis. "Creating a Security Operations Center in Microsoft Azure." Medium, August 10, 2024.
- [Microsoft Azure Documentation](https://azure.microsoft.com/documentation/)
- [NIST 800-53 Framework](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
