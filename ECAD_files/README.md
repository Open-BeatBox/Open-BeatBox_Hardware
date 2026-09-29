## Electronics – Overview and Fabrication

This repository contains the complete electronic design files for the Beatbox project, including schematics, PCB layouts, and manufacturing assets (Gerber files, drill files, and BOM where applicable).

---

### Files structure

All modules in this project use simple PCBs built around the RP2040 microcontroller, selected for its user-friendly USB programming (drag-and-drop code file), support for both C/C++ and Python, and a wealth of open-source libraries. Communication between modules is handled by the CAN bus protocol, using the MCP25625-E/SS controller for reliable, high-speed, and robust connectivity. Each PCB shares the same core circuit design, making it easy to customize or expand by adding only the components needed for each specific function.

This project contains several folders, containing one PCB design each:


###### BB_RPI_shield_V1 (x1)
This PCB serves as the main module, enabling communication with a computer via USB. It distributes power (5V and 12V) to other PCBs, includes a microSD card slot for storage, and features a real-time clock (RTC). It also manages CAN communication with all other modules in the system.

###### BB_feeder_main_V1 (x1)
This simple PCB controls the feeder module, managing pellet distribution for mice. It uses an A4988 driver to control a 14HM11-0404S stepper motor, ensuring precise pellet delivery.

###### BB_lighting_V1 (x1)
This PCB is dedicated to the ceiling lighting module, driving 5000K white LEDs, 615nm red LEDs, and 940nm infrared LEDs via a PCA9955B driver, allowing for customizable lighting in experimental setups.

###### BB_screen_main_V1 (x2)
Each box includes two of these PCBs, each powering a 2.8" TFT LCD with touchscreen (ILI9341, Adafruit) via an 8-bit parallel bus. The PCB also supports backlight control for optimal visibility.

###### BB_IR_light_curtain_V2_38k (x6)
This PCB is used in pairs for each screen and tunnel module, emitting 38-kHz pulsed infrared beams to reduce ambient light interference. It provides both individual beam interruption states (for tunnel use) and a global unified output (for screen use), enabling accurate detection of mouse interactions.

###### BB_tunnel_V1 (x1)
This PCB is part of the tunnel module, reading data from a pair of BB_IR_light_curtain_V2_38k PCBs to detect the direction and speed of mice movement. It includes a Qwiic connector for compatibility with Adafruit and Sparkfun I2C modules, and unused microcontroller I/O pins are accessible for future expansion.

###### BB_nosepoke_V1 (x1)
This PCB is integrated into the nosepoke module, using an infrared photointerrupter (GP1A57HRJ00F) to detect when mice perform nosepoke actions, enabling precise interaction tracking.

###### BB_feeder_IRBarrier_V1 (x1)
This PCB is part of the feeder module, using a GP1A57HRJ00F infrared photointerrupter to detect the presence of pellets inside the feeder, ensuring accurate pellet monitoring and dispensing.



#### File Structure Inside Each PCB Folder

Each PCB folder follows a consistent structure and contains several key design and production files:

##### Design Files
*.kicad_pro — Main KiCad project file. This file manages the overall project configuration and links between schematic and layout.

*.kicad_sch — Schematic file describing the electrical design of the circuit.

*.kicad_pcb — PCB layout file containing the physical design, including component placement and routing.

##### Production Folder

Each folder also includes a production/ directory used for manufacturing and assembly.

Contents typically include:

- Gerber files (usually provided as a .zip) — Used by PCB manufacturers to fabricate the board.
- BOM (Bill of Materials, bom.csv) — Lists all components required for assembly.
- Pick-and-place files (positions.csv, designators.csv) — Provide component designators and coordinates for automated assembly.

These files are essential for transitioning from design to fabrication and assembly.

---

### Ordering bare PCB

This option includes fabrication only (no assembly).

- Step 1 — Upload Gerber .zip file to JLCPCB and verify the board preview.
- Step 2 — Configure PCB Parameters (you can mostly keep the default parameters, it is possible to set a custom thickness and color) (we recommend selecting the LeadFree HASL finish)
- Step 4 — Final Checks: verify quantity and pricing, confirm manufacturing options

### Ordering assembled PCB

This option includes fabrication and assembly and is recommended for this project

- Step 1 — Upload files
Upload the Gerber .zip file and verify the board preview.

- Step 2 — Configure PCB parameters (same as for bare PCB)

- Step 3 — Enable PCB Assembly and select the assembly side(s).

- Step 4 — Upload bom.csv and positions.csv . Check that all components in the selection table are available

- Step 5 — Verification
Check component availability, mappings (LCSC), rotations, polarity, and connectors.

- Step 6 — Final checks
Verify no missing components, review price and lead time.


### Manual soldering

Some parts such as connectors may not be available and must be ordered separately. For cost saving, some users may even to order bare boards and components separately.
Those components must be soldered manually according to the standard procedure.

---
### Additional Components to order

In addition to the assembled PCBs, you will need several additionnal components such as connectors and cables.

- 12V power adapter GST60A12-P1J MEANWELL https://www.mouser.fr/en/ProductDetail/MEAN-WELL/GST60A12-P1J?qs=odmYgEirbwzBCeXKJrW1mg%3D%3D
- picoblade screen 15134-0300 MOLEX https://www.mouser.fr/en/ProductDetail/Molex/15134-0300?qs=lQAVKuKFhkLBenQanZjZ2Q%3D%3D
- picoblade tunnel 15134-0606 MOLEX https://www.mouser.fr/en/ProductDetail/Molex/15134-0606?qs=F%2F1Z9SgJL%252BXGHMSsv17LNQ%3D%3D
- DB9 cables EX-011-0.5MTR-BLK RS PRO https://fr.rs-online.com/web/p/cables-serie/2369118
- 2* screen 1770 ADAFRUIT https://www.mouser.fr/en/ProductDetail/Adafruit/1770?qs=GURawfaeGuAO3ABjFNxilQ%3D%3D
- motor 14HM11-0404S https://www.gotronic.fr/art-moteur-14hm11-0404s-23048.htm?srsltid=AU7gw4VPPmObfX02P8KX7kvqGmsoZfblRJtaHjb1iSWNCiLywOehEnlU
- mini camera (color camera mini-HD 700TVL 1/3” CMOS NTSC 3.6mm MTV Board Lens Mini CCTV Security Video FPV)
- usb-c cable for computer connection



---

### Important Notes

- Always double-check polarity and orientation before confirming assembly  
- If a component is unavailable, you may need to substitute it or assemble it manually  
- If non-generic components are unavailable, it is recommended to consult with an electronics engineer to identify suitable alternatives or adapt the design accordingly  
- The passive and active systems are independent and require different fabrication workflows  
- All necessary files are organized in the repository for direct use  
