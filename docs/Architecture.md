# SUTMS Architecture

## 1. Overview

**SUTMS** (Smart Unified Threat Management System) is a modular network security framework designed to provide integrated network monitoring, intrusion detection, security event analysis, and network-level enforcement.

The architecture combines multiple open-source security technologies within a Linux-based environment. Each component performs a dedicated security function while contributing to a coordinated security monitoring and response workflow.

## 2. High-Level Architecture

```
          INTERNET
             │
             ▼
    ┌───────────────────┐
    │  Network Traffic  │
    │      Interface    │
    └─────────┬─────────┘
              │
              ▼
    ┌───────────────────┐
    │      SURICATA     │
    │ Traffic Inspection│
    └─────────┬─────────┘
              │
      Security Events
              │
              ▼
    ┌───────────────────┐
    │       WAZUH       │
    │    Event Analysis │
    └─────────┬─────────┘
              │
      Security Response
              │
              ▼
    ┌───────────────────┐
    │      IPTABLES     │
    │   Traffic Control │
    └─────────┬─────────┘
              │
              ▼
      PROTECTED NETWORK
    ┌───────────────────┐
    │       GLANCES     │
    │ System Monitoring │
    └───────────────────┘
````

## 3. Architectural Components

### 3.1 Network Interface

The network interface provides the entry point for network traffic monitored by **SUTMS**. It acts as the communication point between the monitored network and the security components deployed within the **SUTMS** environment.

The network layer may provide information such as:

- Source and destination addresses
- Network protocols
- Connection information
- Packet information
- Traffic metadata
- Network activity

The exact interface configuration depends on the deployment environment.

### 3.2 Suricata IDS/IPS

Suricata is used as the network intrusion detection and prevention component of **SUTMS**. Its primary responsibilities include:

- Network packet inspection
- Protocol analysis
- Signature-based detection
- Suspicious traffic identification
- Intrusion detection
- Intrusion prevention
- Security-event generation
- Network security monitoring

Suricata generates security events that can be consumed by the centralized monitoring layer.

### 3.3 Wazuh Security Monitoring Layer

Wazuh provides centralized security monitoring and event analysis within **SUTMS**. It can collect information from multiple security and system sources, including:

- Suricata security events
- Authentication logs
- System logs
- Security events
- Network-related events

The Wazuh layer provides centralized visibility into security activity and supports event analysis and response workflows.

### 3.4 iptables Firewall Layer

iptables provides the network enforcement layer within the **SUTMS** architecture. Its responsibilities include:

- Packet filtering
- Network access control
- Traffic restriction
- Source-based blocking
- Firewall rule management
- Enforcement of security responses

iptables operates at the Linux networking layer and provides the mechanism through which network traffic can be allowed, restricted, or blocked.

### 3.5 Glances System Monitoring

Glances provides system-resource monitoring for the **SUTMS** environment. It can provide visibility into:

- **CPU** utilization
- Memory utilization
- Disk usage
- Network activity
- Running processes
- System load
- Overall system health

System monitoring helps evaluate the operational requirements and resource overhead of the security stack.

## 4. High-Level Data Flow

The overall **SUTMS** workflow can be represented as:

<img width="759" height="80" alt="image" src="https://github.com/user-attachments/assets/80246b9c-f85a-4be2-b7ce-254abf6242a2" />


The architecture separates the major security functions into distinct logical layers. This separation improves modularity and allows individual components to be configured, monitored, tested, and maintained independently.

## 5. Security Processing Flow

At a conceptual level, **SUTMS** operates through the following stages:

### Stage 1 — Network Traffic

Network traffic enters or passes through the monitored **SUTMS** environment.

### Stage 2 — Traffic Inspection

The network traffic is inspected by the network security layer.

### Stage 3 — Detection

Suspicious or security-relevant activity can result in the generation of security events.

### Stage 4 — Centralized Monitoring

Relevant events are collected by the centralized security monitoring layer.

### Stage 5 — Event Analysis

Collected events are analyzed to identify security-relevant activity.

### Stage 6 — Response

When appropriate, the architecture can initiate a security response.

### Stage 7 — Enforcement

The firewall layer can enforce the resulting network-security action.

### Stage 8 — Monitoring

Security events and system-resource information remain available for monitoring and analysis.

## 6. Component Responsibilities

| Component                   | Primary Responsibility                             |
| --------------------------- | -------------------------------------------------- |
| Network Interface           | Provides monitored network traffic                 |
| Suricata                    | Network intrusion detection and prevention         |
| Wazuh                       | Centralized security monitoring and event analysis |
| iptables                    | Network traffic filtering and enforcement          |
| Glances                     | System-resource monitoring                         |
| Ubuntu Linux                | Base operating system and networking environment   |
| Threat Intelligence Sources | External security intelligence where configured    |

## 7. Logging and Visibility

**SUTMS** relies on the logging capabilities of its individual components to provide security visibility.

### Suricata

Suricata can generate information related to:

- Security alerts
- Network events
- Protocol activity
- Detection events
- Engine activity

### Wazuh

Wazuh can provide information related to:

- Security alerts
- Collected logs
- Event metadata
- Correlated events
- Response activity
- Monitoring information

### Linux

The Linux environment can provide:

- Authentication events
- System events
- Service activity
- Network-related information

## 8. Threat Intelligence Layer

**SUTMS** can incorporate external threat-intelligence information as part of its security architecture.

Relevant technologies and standards include:

- **STIX**
- **TAXII**
- Threat-intelligence feeds

Threat intelligence can provide information about known security indicators and malicious infrastructure.

## 9. Deployment Environment

**SUTMS** was developed and evaluated in a controlled Linux-based virtual environment.

The virtualized environment provides:

- Network isolation
- Controlled testing
- Repeatable experiments
- Resource allocation
- Security-event simulation
- Configuration testing
- System-resource monitoring

The architecture can be adapted to other Linux-based environments or dedicated hardware depending on deployment requirements.

## 10. Design Principles

### 10.1 Modularity

Each security component performs a defined function and can be managed independently.

### 10.2 Layered Security

Multiple security mechanisms operate at different stages of the security workflow.

### 10.3 Centralized Visibility

Security information from multiple sources can be brought together for centralized monitoring.

### 10.4 Automated Response

The architecture supports automated security responses when appropriate conditions are identified.

### 10.5 Lightweight Deployment

**SUTMS** uses open-source technologies and is designed with resource-conscious deployment in mind.

### 10.6 Extensibility

The modular architecture allows additional security tools, monitoring capabilities, intelligence sources, and enforcement mechanisms to be incorporated in future versions.


## 11. Summary

**SUTMS** combines network intrusion detection, centralized security monitoring, firewall enforcement, threat-intelligence support, and system-resource monitoring within a unified security architecture. The architecture is designed to provide multiple layers of network protection while maintaining modularity and operational visibility.

The public documentation intentionally presents the system at an architectural level. Research-specific mechanisms, internal detection logic, custom response procedures, optimization techniques, thresholds, and unpublished implementation details remain outside the public repository.
