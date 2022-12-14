---
title : "Benefits"
weight : 2
---

### Test without Hardware

AVH allows to verify your code without the need for physical hardware which provides a robust test environment that enables:

- Early software development for faster time-to-market
- Select optimal target device once the software workload is analysed
- Re-target applications to production hardware with driver abstractions

 ### Verify Correctness

Arm Virtual Hardware Targets are based on Arm simulation models that are validated with the same process as the IP. Specially it allows you to:

- Perform algorithm testing with identical logical behaviour of the target device
- Precisely repeat complex input patterns in CI/CD test environments
- Analyse software behaviour with event annotations

### Evaluate Performance

Software algorithms for Digital Signal Processing (DSP) or Machine Learning (ML) frequently require significant CPU resources and need to be optimized for the target hardware. Comparing performance of such "load heavy" algorithms requires that they can be automatically executed with different configurations parameters but using identical input.

Arm Virtual Hardware Services allows users to test their programs at scale with reproducible input patterns and so validate and optimize application performance which allows you to:

- Compare speed of different implementations of an algorithm
- Identify timing issues during system integration
- Optimize resources (i.e. data buffers) towards application requirements

### Continuous Testing

Applying continuous integration work flows for embedded applications can be complicated by the specifics of development environments and the need of executing the program on target hardware. So the development teams are often reluctant to spend initial effort setting up the continuous integration (CI) workflow even though the long-term benefits are undisputed as shown on the Figure below

![avh_overview](/static/effort_comparison.png)

**Arm Virtual Hardware** simplifies the setup and use of CI workflows in embedded projects.

For unit and integration tests virtual targets offer additional advantages over hardware, including:

- **Speed** - no overhead for flashing the application on physical hardware. This saves time on small and fast unit tests.
- **Scale** - virtual platforms can scale to run many tests in parallel. This makes virtual platforms more cost-effective than a farm of physical hardware.
- **Maintenance** ??? unlike physical hardware, virtual platforms do not overheat, wear out from overuse, break from misuse, or use physical space and resources.
- **Upgrades** ??? virtual platforms can be adapted and re-configured to match corresponding changes to the underlying hardware platform that is under development. These types of changes can be costly or impossible with physical hardware.
