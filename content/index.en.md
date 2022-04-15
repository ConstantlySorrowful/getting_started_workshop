---
title: "Getting Started With ARM Virtual Hardware (AVH) in Keil Studio Cloud (KSC)"
weight: 0
---

This workshop demonstrates how to setup a development workflow with cloud-based Continuous Integration (CI) for testing an IoT application that connects to AWS cloud services.

The application can be tested using Arm Virtual Hardware. Code development and debug can be done locally, for example with CMSIS-Toolbox and Keil MDK tools. In this workshop we will demonstrate how to use Keil Studio Cloud that will provide a cloud-native development environment.

Automated test execution is managed with GitHub Actions and gets triggered on every code change in the repository. The program gets built and run on Arm Virtual Hardware cloud infrastructure in AWS and the test results can be then observed in repository's GitHub Actions.
