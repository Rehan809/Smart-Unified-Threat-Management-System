# SUTMS — Smart Unified Threat Management System

## Overview

SUTMS (Smart Unified Threat Management System) is a lightweight home-network security framework designed for real-time network monitoring, threat detection, security-event analysis, and automated response.

The system integrates **Suricata IDS/IPS, Wazuh SIEM, iptables firewall, Glances system monitoring, and STIX/TAXII threat intelligence** on Ubuntu 24.04.


## Repository Structure

```text
SUTMS/
├── README.md
│
└──  docs/
  ├── Architecture.md
  ├── CD&T.md
  └── Tools.md

````

## Project Objectives

* Design a lightweight SUTMS for resource-constrained environments.
* Integrate network flow detection, IDS, and firewall capabilities.
* Optimize IDS signatures to reduce memory and CPU utilization by over 55%.

## Project Status

SUTMS is an implemented and tested security-monitoring project developed for home and small-network environments.

## Architecture

The system supports monitoring of both **inbound and outbound network traffic**.

**Core flow:**

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/991a9d2a-ef10-49d9-99a7-53823639ec06" />


## Project Details

Detailed information about the SUTMS components, key features, implementation process, testing, challenges, and performance results is documented separately.

For the complete project workflow and evaluation details, refer to: **[Configuration, Deployment & Testing](docs/CD&T.md)**

## Project Team

SUTMS was developed collaboratively by:

- **Rehan Shaik [[LinkedIn](https://www.linkedin.com/in/rehan809)]**
- **Munazza Farees [[LinkedIn](https://www.linkedin.com/in/munazza-farees-a983142b7)]**

## Acknowledgement

We want to express our sincere gratitude to **RAMESH D [[LinkedIn](https://www.linkedin.com/in/rameshd24/)]** for his constant guidance and valuable suggestions during the project work on SUTMS.

His technical insights, patience, and support helped us understand the challenges, improve our implementation, and complete this project. We are truly thankful for his mentorship and contribution to our learning and project journey.
