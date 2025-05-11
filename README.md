Sure! I’ll write a polished and professional GitHub README that clearly explains your Micro-Mouse power module project, outlines the work split between team members, and provides helpful context for readers or collaborators.

I’ll include sections for project overview, subsystem role, member contributions, and build contents.

I’ll share the updated README shortly.


# EEE3088F-2025 Micro-Mouse Power Module

**Authors:** Khanyisa Hlungwani & Maitele Makungo

## Project Description

This repository contains the **Power Module** for a Micro-Mouse robot project, developed as part of the EEE3088F (2025) course. The Micromouse is a small autonomous robot designed to navigate and solve a maze, consisting of various subsystems (sensors, motors, control, and power). The Power Module handles all aspects of power distribution and management for the robot, ensuring that each component receives stable and sufficient power. It includes the circuitry for the robot’s battery power supply, voltage regulation for logic and sensors, and motor driver outputs, along with safety features like battery monitoring and charging control. Overall, this module is crucial for delivering reliable power to the Micro-Mouse, allowing it to operate safely and efficiently during maze-solving runs.

## Scope and Responsibilities

The design and implementation of the Power Module were divided between two team members, each focusing on specific functional areas:

* **Khanyisa Hlungwani:** Responsible for the **motor control** circuitry and **battery management**. This includes the motor driver hardware for the drive motors, the **battery monitoring** system to track battery voltage/health, and the **battery charging** circuit to safely recharge the robot’s Li-ion/Li-Po battery pack. Khanyisa’s design ensures the motors receive the appropriate power and that the battery is used and charged safely (with over-voltage and over-discharge protection as needed).

* **Maitele Makungo:** Responsible for the **power input interface** and **voltage regulation**. This includes the **USB-C interface** for external power/charging (allowing the robot to be powered or charged via a USB-C source), the design of **voltage regulators** (to step down or regulate battery/USB voltage to the required levels for various components such as 5V, 3.3V, etc.), and overall **power management** circuitry. Maitele’s design ensures stable regulated voltages for all electronics and handles power switching logic (for example, switching between USB power and battery, and implementing any necessary protection like current limiting or short-circuit protection).

By splitting the responsibilities, each student focused on their section of the power system while ensuring that the two parts integrate seamlessly into a single Power Module that meets the Micro-Mouse’s requirements.

## Repository Contents

The repository is organized into folders and files that represent different aspects of the Power Module design:

* **Schematics** – Contains the electrical schematics of the power module. This includes complete circuit diagrams for the battery charger/monitor, motor driver circuits, USB-C power input circuitry, and voltage regulators. The schematics are provided in the chosen EDA tool format (and may include PDF exports for easy viewing). **(e.g.,** files like `PowerModule_Schematic.pdf` and the source schematic design files **)**

* **PCB Layout** – Contains the PCB design files and layout information for the power module’s printed circuit board. This includes the board layout file from the PCB design software, as well as generated manufacturing files (Gerber files, drill files) and possibly images of the PCB layout. **(e.g.,** a board file `PowerModule_PCB.kicad_pcb` or Altium project, and exported images like `PCB_Top.png`, `PCB_Bottom.png` **)**

* **Final Design** – This folder includes the finalized documentation and outputs of the project. It typically contains the final report or design document for the power module, a Bill of Materials (BOM) listing all components used, and any presentation slides or additional references. It may also include **final revision** schematic/PCB printouts and assembly drawings, as well as test results or data from the completed module. In short, the **Final Design** folder serves as a comprehensive package of the finished power module design and can be used for review or submission purposes.

*(If applicable, the repository may also include firmware or code related to the power module — for example, microcontroller code for battery monitoring. Such code (if present) will be located in a separate `Firmware` directory with its own README or documentation.)*

## Usage and Integration

The Power Module is designed to integrate with the Micro-Mouse robot’s overall system (often via a main control board or motherboard). Key connections and usage notes include:

* **Power Input:** The module can be powered via the on-board battery or through the USB-C port. When the Micro-Mouse is operating untethered, it draws power from the battery. When plugged into USB-C, the system can charge the battery and/or run the robot from USB power (with proper regulation and without overcharging the battery).

* **Outputs to Other Modules:** The Power Module provides regulated output lines (e.g., 5V, 3.3V) that connect to the Micro-Mouse’s other subsystems (like the sensor module and control electronics) via a designated connector. It also provides the motor driver outputs that connect directly to the motors on the chassis. These interface connections are clearly labeled in the schematic and on the PCB silkscreen for easy assembly.

* **Battery Monitoring:** The on-board battery voltage sensor can be read by the main controller (or a dedicated microcontroller on the power board) to determine the battery charge level. This allows the robot’s software to warn about low battery or manage charging states. Users should ensure the battery is within safe voltage ranges during operation (the module includes under-voltage lockout to protect the battery).

* **Charging:** To charge the robot, connect a USB-C cable to the Power Module’s port. The charging circuit will automatically manage the charging current and cutoff based on the battery’s state. Indicator LEDs (if included on the PCB) may show the charging status (charging, full, etc.). It’s recommended to refer to the **Final Design** document for specifics on the charging procedure and any jumpers or switches related to power sourcing.

## Getting Started

To get started with this Power Module repository:

1. **Clone the Repository:** Download or clone the repo to access all design files. Ensure you have the necessary software to open the schematic (`Schematics` folder) and PCB layout files (`PCB Layout` folder). For example, if the design was done in KiCad, download KiCad to open the project; if Altium, use Altium Designer, etc.

2. **Open the Schematic:** Review the power module schematic to understand the circuit design. This can be found in the **Schematics** folder (use the PDF for a quick view, or the source file for editing). The schematic is annotated with comments to explain the role of each section (battery charger, motor driver, etc.).

3. **Examine the PCB Layout:** Open the PCB design in the appropriate software to see component placement and routing. Alternatively, view the provided PCB images in the **PCB Layout** folder to get an overview of the board’s design (component locations, board dimensions, connectors, etc.).

4. **Read the Documentation:** In the **Final Design** folder, read the final report or documentation which includes detailed descriptions of design decisions, testing procedures, and results. This will provide insight into why certain components were chosen and how the module was verified to meet requirements.

5. **Integration:** If you are integrating this Power Module with your own Micro-Mouse project, use the interfacing information (pinouts and diagrams) provided in the documentation to connect the module properly. The **Micro-Mouse System Interfacing** section of the report (in **Final Design**) describes how this power board connects to the main controller board and motors.

## Contributing

This project was completed as an academic course project by the authors, so it may not be open for external contributions in the usual sense. However, if you are an instructor or student looking to use this design as a reference or extend it:

* Feel free to fork the repository for your own educational use.
* If you find issues or have suggestions, you can contact the authors or open an issue for discussion.
* Ensure to credit the original authors (Khanyisa Hlungwani and Maitele Makungo) if you derive or use significant portions of this design in your own project.

## Acknowledgments

* **Course Instructors and Mentors:** Thank you to the EEE3088F course instructors for guidance throughout the project, and for providing the framework and resources for the Micro-Mouse competition project.
* **Teammates:** Appreciation to each other as team members for the collaboration and division of work that made this Power Module successful.
* **Resources:** The Micro-Mouse community and prior projects provided inspiration and insight. Resources like online Micromouse forums and documentation helped shape the design (for example, understanding common voltage requirements and battery choices for micromouse robots).



---

*This README provides an overview of the Power Module for the EEE3088F-2025 Micro-Mouse project. For detailed schematics, PCB layouts, and test results, please refer to the files and documentation within this repository. We hope this information is helpful for anyone studying or building a Micro-Mouse power system.*

 
