---
title : "Physical Hardware"
weight : 150
---

**Modular programming** recommends to separate the functionality of a program into independent, interchangeable modules that use defined interfaces that abstract the hardware functionality. This design concept simplifies code re-use and allows to implement **Virtual Drivers** and **Hardware Drivers** that expose the same API and implement the same logical behavior. If built correctly, it overcomes many issues that are typically found in monolithic software and enables a staged **software validation** with multiple test levels such as unit, integration, and system testing.

To simplify re-targeting from **Arm Virtual Hardware Targets** to final production hardware, the examples implement the concept of software layers. As the next generation tooling will provide native support for program layers, it makes it easy to work on a combination of simulated and physical hardware. The picture below examplifies this concept.

![Import project dialog](/static/Simulation2Hardware.png)