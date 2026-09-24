# SUTMS Architecture

## 1. Overview

**SUTMS** (Smart Unified Threat Management System) is a modular network security framework designed to provide integrated network monitoring, intrusion detection, security event analysis, and network-level enforcement.

The architecture combines multiple open-source security technologies within a Linux-based environment. Each component performs a dedicated security function while contributing to a coordinated security monitoring and response workflow.

## 2. Architectural Components

### 2.1 Network Interface

The network interface provides the entry point for network traffic monitored by **SUTMS**. It acts as the communication point between the monitored network and the security components deployed within the **SUTMS** environment.

### 2.2 Suricata IDS/IPS

Suricata is used as the network intrusion detection and prevention component of **SUTMS**.

### 2.3 Wazuh Security Monitoring Layer

Wazuh provides centralized security monitoring and event analysis within **SUTMS**.

### 2.4 iptables Firewall Layer

iptables provides the network enforcement layer within the **SUTMS** architecture.

### 2.5 Glances System Monitoring

Glances provides system-resource monitoring for the **SUTMS** environment. System monitoring helps evaluate the operational requirements and resource overhead of the security stack.

## 3. High-Level Data Flow

The overall **SUTMS** workflow can be represented as:

<img width="759" height="80" alt="Screenshot" src="https://github.com/user-attachments/assets/0bdde540-86ef-41ba-b329-9d1f9abb7c6a" />

The architecture separates the major security functions into distinct logical layers. This separation improves modularity and allows individual components to be configured, monitored, tested, and maintained independently.

## 4. Summary

**SUTMS** combines network intrusion detection, centralized security monitoring, firewall enforcement, threat-intelligence support, and system-resource monitoring within a unified security architecture. The architecture is designed to provide multiple layers of network protection while maintaining modularity and operational visibility.

The public documentation intentionally presents the system at an architectural level. Research-specific mechanisms, internal detection logic, custom response procedures, optimization techniques, thresholds, and unpublished implementation details remain outside the public repository.
