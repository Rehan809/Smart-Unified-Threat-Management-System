# Configuration, Deployment & Testing

## Overview

This document describes the main implementation stages of SUTMS: configuring the security components, deploying them in the Ubuntu environment, and validating the complete system through controlled testing.

The implementation focused on integrating **Suricata IDS/IPS, Wazuh SIEM, iptables, Glances, and STIX/TAXII threat intelligence** into a unified home-network security system.

# 1. Configuration

Each SUTMS component was configured according to its role in the security architecture.

- **Suricata** was configured for network traffic inspection, threat detection, and alert generation.
- **Wazuh** was configured for centralized security-event monitoring, log collection, analysis, and alert visibility.
- **iptables** was configured for firewall filtering and automated malicious-IP blocking.
- **Glances** was configured to monitor CPU, memory, disk, network, and process usage.
- **STIX/TAXII** was incorporated to support threat-intelligence and indicator-based security analysis.

The components were configured separately and then connected according to their roles in the overall SUTMS architecture.

Configuration files were kept separate from application code so that security rules, service settings, and environment-specific parameters could be managed independently.

# 2. Deployment

SUTMS was deployed in an **Ubuntu 24.04 virtualized environment** for controlled home-network security monitoring. The system supported monitoring of both **inbound and outbound network traffic**.

# 3. Testing

The complete SUTMS environment was tested in a controlled virtual environment using simulated security scenarios.

Testing focused on:

- Network traffic inspection
- Automated IP blocking
- Suricata–Wazuh–iptables integration
- CPU and memory utilization

The system was initially tested under normal network traffic conditions. It was then subjected to a series of attack scenarios to evaluate its performance.

## Key Results

The evaluation demonstrated:

- **~99% real-time attack detection accuracy** across simulated threat scenarios.
- Automated malicious-IP blocking after **5 failed SSH attempts within 60 seconds**.
- Approximately **55% reduction in memory utilization** after optimizing the Suricata detection stack.
- **Below 30% CPU usage** during continuous monitoring and live attack simulations.

# Overall Implementation Flow

The project followed a simple development cycle:

**Configure → Integrate → Deploy → Simulate → Monitor → Validate → Optimize**

The final system combined network detection, centralized monitoring, firewall enforcement, automated response, threat intelligence, and resource monitoring into a unified home-network security environment.
