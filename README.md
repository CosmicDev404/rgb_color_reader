# rgb_color_reader
A low-cost color sensing system using an RGB LED and an LDR, exploring color detection through calibrated illumination and reflected light.
DIY RGB + LDR Color Sensor (Arduino). ![Cinematic](https://github.com/user-attachments/assets/7d9ebcee-1ecf-4d9f-93ef-921ba2582d2a)

🔹 BOM:
Following components are used to create this project.
- Arduino (Uno or Pro mini) _already owned_
- An LDR
- Resistors(10kΩ, 2x100Ω & 150Ω)
- An RGB LED with common cathode
- 0.96 inch I2C OLED display
- PCB(gerber included in hardware directory)
- MicroUSB female 5 pin
- 3x6*6*8 push buttons
- 2x12 2.54mm Female Headers + 1x2 2.54mm Female Headers

 🔹PCB

<img width="479" height="464" alt="Screenshot 2026-01-08 134518" src="https://github.com/user-attachments/assets/10226011-3d3e-4f2c-97da-be733eabfe1b" /><img width="1365" height="586" alt="Screenshot 2026-01-08 140915" src="https://github.com/user-attachments/assets/cdef54b9-564e-46ba-9990-fa988ce4928b" />

🔹Schematic:

<img width="736" height="521" alt="image" src="https://github.com/user-attachments/assets/614d9b38-b753-4c48-a9b9-ced5eaab9ab4" />


#  Background
🔹 What is this?

I’m building a low-cost color sensing system using an RGB LED and an LDR.
The idea is to sequentially illuminate a surface with red, green, and blue light and measure reflected intensity to identify colors.
It basically works like a human eye, detecting RGB reflections and determining the surface color.

![LDR](https://github.com/user-attachments/assets/7b20af16-8e54-44a7-9c9f-5a29e79c1d0a)

🔹 Why?

Commercial color sensors are expensive and opaque.
This project explores how much can be achieved with basic components, calibration, and software logic.
The fun part is that all the components used are super ubiquitous and affordable, so anyone can make it.
https://github.com/user-attachments/assets/6e2b36a0-62c5-49fb-8e82-23192e9eb4c3

![WhatsApp Image 2026-01-04 at 19 53 35_cdc5ee56](https://github.com/user-attachments/assets/c45b4d5e-eefc-4126-b578-34caf9d89753)

