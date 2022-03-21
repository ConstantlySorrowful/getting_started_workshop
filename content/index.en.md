---
title: "Getting Started With ARM Virtual Hardware"
weight: 0
---

# Getting Started With ARM Virtual Hardware

This project demonstrates how to setup a development workflow with cloud-based Continuous Integration (CI) for testing an IoT application that connects to AWS cloud services.

The application can be tested using Arm Virtual Hardware. Code development and debug can be done locally, for example with CMSIS-Build and Keil MDK tools. We are also working on a development flow for Keil Studio that will provide a cloud-native development environment.

Automated test execution is managed with GitHub Actions and gets triggered on every code change in the repository. The program gets built and run on Arm Virtual Hardware cloud infrastructure in AWS and the test results can be then observed in repository's GitHub Actions.