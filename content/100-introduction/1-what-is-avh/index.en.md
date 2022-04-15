---
title : "What is ARM Virtual Hardware?"
weight : 110
---

**Arm Virtual Hardware (AVH)** provides simulation models, software tooling, and infrastructure that can be integrated into CI/CD and MLOps development flows.

AVH supports the software development cycle of embedded, IoT, and ML applications and provides essential components for effective test and validation environments. Arm Virtual Hardware is flexible and can run any RTOS that is designed for Cortex-M or bare metal code that interacts with the processor.

Arm Virtual Hardware offers a comprehensive tool integration along with resources for software developers and can therefore run complex applications and software integration tests. A potential workload could be a sensor-fusion Machine Learning (ML) application that connects to the Internet via an IoT operating system.

## Arm Virtual Hardware consists of the following components:

- Arm Virutal Hardware Targets are precise simulation models of Cortex-M device sub-systems and are designed for complex software verification and testing. It allows simulation-based test automation of various software workloads, including unit tests, integration tests, and fault injection.
- Arm Virtual Hardware Services provide a cloud-native infra-structure for software test and validation. These Arm Virtual Hardware services can be integrated into various CI/CD and MLOps environments that range from GitHub to on-premise IT infrastructure. The Arm Virtual Hardware services will be available via the AWS Marketplace (and later also via other Cloud Service providers).
- Arm Virtual Hardware Developer Resources gives you access to interface drivers that map to virtual targets and physical hardware along with Python scripts for I/O simulation. The documentation explains how to integrate Arm Virtual Hardware Targets into typical CI/CD environments. Usage examples show typical usage cases and range from audio processing, ML algorithm testing, up to IoT applications that interface to Cloud Service providers.
- Software Development Environments with Arm Virtual Hardware Targets integration are also available. Arm Virtual Hardware is an integral part of the Keil MDK Professional Edition that is a comprehensive software tool suite for creating Cortex-M-based applications and related validation and test processes. In future, the next-generation Keil Studio will also integrate Arm Virtual Hardware.

![avh_overview](/static/vht_overview.png)
