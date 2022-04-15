---
title : "Keil Studio"
weight : 204
---

- Open [Keil Studio](https://studio.keil.arm.com) and go to **File - Import Project**:
  ![Import project dialog](/static/import_project.png)
- Enter the URL [URL_to_the_repo](https://www.github.com)
- The project is imported and set as the active project:
  ![AWS MQTT Demo project opened and set active](/static/aws_mqtt_demo.png)
- The README.md file shows project settings and explains what you require to make the project run on Virtual Hardware in Keil Studio.
- Make the required changes.
- **Build** the project by clicking the build button: ![Build Button](/static/build_button.png)
- The build should complete without errors or warnings.
- Finally, run the project on the AVH model clicking the run button: ![Run Button](/static/run_button.png)
- You will see the debug messages in the **Output** window:
  ![Output Window](/static/output_window.png)
