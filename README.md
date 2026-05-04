# blinky board

This toro inoue inspired 555 LED chaser board contains 2 IC's: CD4017 to control LED's flashing and get input from NE555P, 2 header pins to power the circuit, standard capacitors and resistors, and of course LEDs. Made with help from @Tanishq Goyal qnd @CAN's guides on stasis.

using the 555's astable mode, produces a continuous oscillating signal by toggling its output between high and low

# Photos

|Schematic|PCB|3D Render|
|---|---|---|
|![Schematic](https://github.com/emilyahmad/devboard/blob/main/images/devboard-schematic.png?raw=true)|![PCB](https://github.com/emilyahmad/devboard/blob/main/images/devboard-pcb.png?raw=true)|![3D](https://github.com/emilyahmad/devboard/blob/main/images/devboard-3dviewer.png?raw=true)|
<!--
# BOM
| Item | Purpose | Quantity | Cost | Source |
|---|---|---|---|---|
| C1, C2 | 10uF decoupling capacitor | 2 | $0.0800 | JLCPCB Basic (CL10A106KP8NNNC) |
| C3, C18 | 1uF decoupling capacitor | 2 | $0.0660 | JLCPCB Extended (GRM155R60J105KE19D) |
| C4, C5, C19, C20, C22, C23, C24, C26 | 0.1uF decoupling capacitor | 8 | $0.0845 | JLCPCB Basic (CL05B104KO5NNNC) |
| C15, C16 | 33pF crystal load capacitor | 2 | $0.0130 | JLCPCB Basic (0402CG330J500NT) |
| C17, C21, C25 | 0.1uF decoupling capacitor | 3 | $0.0845 | JLCPCB Basic (CL05B104KO5NNNC) |
| J1 | USB-C receptacle | 1 | $0.9155 | JLCPCB Extended (TYPE-C-31-M-12) |
| J2, J3 | 20-pin GPIO header | 2 | — | Solder yourself |
| J4 | 3-pin SWD debug header | 1 | — | Solder yourself |
| R1, R2 | 5.1K CC pull-down resistor | 2 | $0.0090 | JLCPCB Basic (0402WGF5101TCE) |
| R3, R4 | 27Ω USB termination resistor | 2 | $0.0176 | JLCPCB Extended (0402WGF270JTCE) |
| R5, R7, R8 | 1K resistor | 3 | $0.0150 | JLCPCB Extended (RCT021KFLF) |
| R6 | 10K pull-up resistor | 1 | $0.0065 | JLCPCB Basic (0402WGF1002TCE) |
| SW1, SW2 | Push button | 2 | $0.5550 | JLCPCB Basic (TS-1088-AR02016) |
| U1 | MCP1700 3.3V LDO regulator | 1 | $2.4285 | JLCPCB Extended (MCP1700T-3302E/TT) |
| U2 | RP2040 microcontroller | 1 | $4.8810 | JLCPCB Extended (RP2040) |
| U3 | W25Q16 16Mbit flash memory | 1 | $6.3910 | JLCPCB Extended (W25Q16JVZPIQ TR) |
| Y1 | 12MHz crystal oscillator | 1 | $0.8382 | JLCPCB Extended (XJHCELNANF-12MHZ) |

Total: $16.38
-->

```
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡜⠀⠑⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠇⠑⢄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡾⠀⠀⠀⠈⢂⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡌⠀⠀⠀⠑⢆⡀⠀⠀⠀⠀⠀⠀⠀⠀⠺⠄⣀⠀⠀⠀⠀⠑⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡘⠀⠀⠀⠀⣀⠜⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠑⠀⠤⣀⠈⢆⠀⠀⠀⠀⠀⠀⠀⢀⡸⠄⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⠃⠀⢀⠤⠊⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⠀⠑⠄⠀⠀⠀⠀⣀⡞⠁⠀⠀⢀⡀⠀⠀⠀⠀
⠀⠀⠀⠀⣤⠄⠀⠀⠀⠀⠀⢀⠋⡠⠔⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣤⠶⠒⠛⠉⠉⠈⢂⠀⠀⠀⠛⠀⣀⣤⠾⠛⠁⠀⠀⠀⠀
⠀⠀⠀⠀⠈⠳⣤⡀⠀⠀⠀⡎⠉⣀⣀⣀⣠⣄⣀⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣶⣿⣿⠶⠶⠶⠶⠶⠶⢤⣀⠱⠀⠀⠀⠀⠉⠈⠀⠀⠀⠀⠀⠀⠀
⠀⠺⢦⣄⡠⠀⠉⠁⠀⠀⠸⠐⠋⠁⠀⢀⣀⣤⣽⣿⠿⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠉⠛⠷⣦⣄⡀⠀⠀⠁⠀⠱⡀⠀⠀⠐⠓⠚⠛⠛⠀⠀⠀⠀
⠀⠀⠀⠀⠉⠛⠀⠀⠀⢀⠇⣠⠴⠶⠛⠉⣡⡾⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⠀⠈⠙⠷⢦⡀⠀⠀⢠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠠⡤⠤⠤⠼⠀⠀⠀⠀⢸⠀⠀⠀⢀⣤⡾⠋⠀⠀⠀⠀⠀⣀⣀⣤⣤⣶⡶⠶⠶⠿⢿⣷⠀⡐⠁⠀⠀⠀⠀⠀⠈⠒⠤⡀⠆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⢀⣴⠿⠩⠤⠄⣀⠀⠀⠀⣿⡟⠋⠉⠀⠀⠀⠀⠀⠀⠀⣿⠀⢇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢾⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠄⠀⡸⠁⠀⠀⠀⠀⠀⠙⢄⠀⢻⣇⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⠀⠈⠢⠄⣀⠀⠀⠀⠀⠀⢀⡠⠜⢣⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠂⠰⠁⠀⠀⠀⠀⠀⠀⠀⢸⠄⠘⣿⡄⠀⠀⠀⠀⠀⠀⠀⠀⣿⠀⠀⠀⠀⠀⠈⠁⠀⠈⠉⠁⠀⠀⠀⠆⠀⠀⠀⢀⠀⠀⠄⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⢇⠀⠀⠀⠀⠀⢀⡠⠔⠁⠀⠀⠹⣿⣄⠀⠀⠀⠀⠀⠀⢰⡿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡰⠀⡠⠐⠁⠀⠀⠀⡆
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠓⠂⠒⠊⠉⠀⠀⠀⠀⠀⠀⠀⠘⢿⣧⣄⠀⠀⠀⢀⣾⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠇⠊⠀⠀⠀⢀⠄⠊⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠛⠷⣦⣤⡾⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡴⠚⠁⠀⠀⠀⡠⠂⠁⠀⠀⠀
⠀⠀⠀⠂⠤⠀⣀⠀⠀⢳⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠈⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⠴⠊⠁⠀⠀⠀⡠⠔⠁⠀⠀⠀⠀⠀⠀
⡀⠀⠀⠀⠀⠀⠀⠈⠑⠂⠙⠢⠤⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠇⢀⡠⠔⠋⠀⠀⠀⠀⡠⠐⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠈⠀⠐⠂⠤⢀⡀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠀⠐⠒⠂⠀⠤⢤⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠞⠁⠀⠀⠀⣀⠄⠂⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠉⠀⠒⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⠠⠒⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢨⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠐⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
```
