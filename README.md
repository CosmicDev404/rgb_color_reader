# rgb_color_reader

<img width=20% alt="Screenshot 2026-01-09 142144" src="https://github.com/user-attachments/assets/3734985a-242d-4958-b2e5-c7b4c7bd2e9c" align=right>

A low-cost color sensing system using an RGB LED and an LDR, exploring color detection through calibrated illumination and reflected light.
DIY RGB + LDR Color Sensor (Arduino). 

 🔹PCB

<img width=60% alt="Screenshot 2026-01-08 134518" src="https://github.com/user-attachments/assets/10226011-3d3e-4f2c-97da-be733eabfe1b" /><img width="1365" height="586" alt="Screenshot 2026-01-08 140915" src="https://github.com/user-attachments/assets/cdef54b9-564e-46ba-9990-fa988ce4928b" />

🔹Schematic:

<img width=60% alt="image" src="https://github.com/user-attachments/assets/614d9b38-b753-4c48-a9b9-ced5eaab9ab4"/>


#  Description

<img src="https://github.com/user-attachments/assets/7b20af16-8e54-44a7-9c9f-5a29e79c1d0a" width=20% align=right>

A low-cost color sensing system using an RGB LED and an LDR.
The idea is to sequentially illuminate a surface with red, green, and blue light and measure reflected intensity to identify colors.
It basically works like a human eye, detecting RGB reflections and determining the surface color.


![Cinematic](https://github.com/user-attachments/assets/7d9ebcee-1ecf-4d9f-93ef-921ba2582d2a)

🔹 Need

Commercial color sensors are expensive and opaque.
This project explores how much can be achieved with basic components, calibration, and software logic.
The fun part is that all the components used are super ubiquitous and affordable, so anyone can make it.

## Components/BOM:

- Arduino (Pro mini)
- An LDR
- Resistors(10kΩ, 2x100Ω & 150Ω)
- An RGB LED with common cathode
- 0.96 inch I2C OLED display
- PCB(gerber included in hardware directory)
- MicroUSB female 5 pin
- 3x6*6*8 push buttons
- 2x12 2.54mm Female Headers + 1x2 2.54mm Female Headers

## Instructions 

- Use the gerber files to create the PCB required for this project from assets
- Upload _"firmware.ino"_ into Arduino pro mini
- Insert Arduino pro mini into the PCB header slots with correct orientation and solder other components
- Make sure that RGB led doesn't directly interfere with LDR readings, ie a separater may be used or correct angles must be ensured
- LDR and RGB must be close to/in contact with the surface for accurate readings 
