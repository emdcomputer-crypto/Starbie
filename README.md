# Starbie PCB Project

Starbie is a small virtual pet PCB made with a XIAO ESP32-C3. It uses a 0.96-inch OLED screen to show an animated pet menus and different stats. The project also has two buttons an MPU6050 motion sensor, and a DHT11 temperature and humidity sensor.

This is my Week 1 PCB project for Hack Club Half Life. I designed the schematic and PCB in KiCad, routed the traces, added a ground pour, checked the board with the Design Rules Checker, and prepared the fabrication files.

## What I learned and what I fixed

I started by following the guided Starbie project from [SharKingStudios](https://github.com/SharKingStudios/Starbie ), because I was already planning to make something similar and this was a good starting point as it was also guided.

After setting up the schematic with the XIAO ESP32-C3, OLED display, MPU6050, DHT11 sensor, and buttons, I started routing everything in KiCad. Routing by hand became messy quickly, so I looked up some tips to make the traces cleaner.

Instead of manually routing every ground connection, I added a full-board GND copper pour. When I ran the DRC, I found some isolated ground pads because traces were blocking the copper pour from reaching them. I fixed this by adding short bridge traces from those pads to the ground zone. After that, the board had zero unconnected pads.

I also used KiCad's 3D viewer to check if the components would fit correctly. Later, I had a problem where JLCPCB kept showing the board as a small default rectangle. I eventually realized that I had forgotten to press the Plot button after changing the KiCad settings. After plotting the files again and re-zipping them, the board showed correctly.

## Bill of Materials

These are the prices I found for the parts in Italy:

I took the time to carefully research and compare components. Originally, I considered sourcing through Amazon Italy to avoid potential customs delays. However I realized that ordering directly through AliExpress offers significantly lower individual component prices even when accounting for EU VAT and standard shipping to Italy.

By spending extra time finding good AliExpress parts like the XIAO microcontroller, OLED display, and sensors, I was able to slash the total project cost down by a little:

| Part | What it is used for | Quantity | Price | Vendor |
|---|---|---:|---:|---|
| [XIAO ESP32-C3](https://it.aliexpress.com/item/1005008791937363.html) | Main microcontroller and Wi-Fi | 1 | $10.92 | AliExpress |
| [0.96-inch OLED Display](https://it.aliexpress.com/item/1005008791937363.html) | Displays pet status and sensor readings | 1 | $2.28 | AliExpress |
| [MPU6050 Module](https://it.aliexpress.com/item/1005008791937363.html) | 6DOF Motion and gyroscope sensor | 1 | $3.24 | AliExpress |
| [DHT11 Sensor](https://it.aliexpress.com/item/1005008791937363.html) | Temperature and humidity monitoring | 1 | $2.09 | AliExpress |
| [3-Pin MX Switches](https://it.aliexpress.com/item/1005008791937363.html) | Mechanical user input switches | 1 | $4.70 | AliExpress |
| [Relegendable Keycaps](https://it.aliexpress.com/item/1005008791937363.html) | Clear dual-layer customizable keycap shell | 1 | $4.66 | AliExpress |
| [PCB Fabrication](https://jlcpcb.com/) | Custom circuit board manufacturing | 1 | $10.30 | JLCPCB |

- **Parts Subtotal:** $38.19 
- **Tax & Shipping:** $37.44 (Including PCB manufacturing shipping/taxes)
- **Total Project Cost:** **$75.63**



## Project files

- [`Hardware/Project.kicad_sch`](Hardware/Project.kicad_sch) — KiCad schematic
- [`Hardware/Project.kicad_pcb`](Hardware/Project.kicad_pcb) — KiCad PCB layout
- [`Hardware/Project.kicad_pro`](Hardware/Project.kicad_pro) — KiCad project file
- [`FabricationFiles`](FabricationFiles) — Gerber and drill files
- [`Firware/Starbie.ino`](Firware/Starbie.ino) — ESP32-C3 firmware
- [`BOM.md`](BOM.md) — full bill of materials
- [`BOM.csv`](BOM.csv) — CSV version of the bill of materials
- [`JOURNAL.md`](JOURNAL.md) — project development journal


## Credits

This project was based on the guided Starbie project by [SharKingStudios](https://github.com/SharKingStudios/Starbie ). I used it as a starting point and made my own PCB layout, fabrication files, documentation, and project changes for Hack Club Half Life Week 1.


<img width="1920" height="1080" alt="8" src="https://github.com/user-attachments/assets/c37e10d5-585f-4cc0-acd0-51f298823da0" />
<img width="1920" height="1080" alt="7" src="https://github.com/user-attachments/assets/87957fc7-e223-4ff7-b5dd-a4a5c4921c19" />
<img width="1920" height="1080" alt="6" src="https://github.com/user-attachments/assets/625f0c08-736c-48d9-abf9-7ff58fc5dfe3" />
<img width="1920" height="1080" alt="5" src="https://github.com/user-attachments/assets/972f1bec-a14e-47f3-9d3a-ed867ab34475" />
<img width="1920" height="1080" alt="4" src="https://github.com/user-attachments/assets/3e0d92da-f70a-4f13-beae-8f6c6e0f95c5" />
<img width="1920" height="1080" alt="3" src="https://github.com/user-attachments/assets/864ecc64-ffe6-4982-923c-56a3f4dc68a8" />
<img width="1920" height="1080" alt="2" src="https://github.com/user-attachments/assets/4ba7f78e-6d13-4d3d-9e9e-a9404b95ea41" />
<img width="1920" height="1080" alt="1" src="https://github.com/user-attachments/assets/597cae54-7f68-4bd6-b929-0c935f74671d" />
<img width="1920" height="1080" alt="1 4" src="https://github.com/user-attachments/assets/3ae49fa7-ef4e-497e-81d8-3ddacc3fb5fa" />
<img width="1920" height="1080" alt="1 3" src="https://github.com/user-attachments/assets/57f14418-2df4-423d-9654-304cf5f2df3c" />
<img width="1920" height="1080" alt="1 2" src="https://github.com/user-attachments/assets/b28252e1-e858-4774-a134-100a6e32339e" />
<img width="1918" height="1022" alt="1" src="https://github.com/user-attachments/assets/825287b1-bd7a-44bd-b2d2-55fc8d6c6fd0" />
<img width="899" height="835" alt="2" src="https://github.com/user-attachments/assets/0a0aad9e-b819-4356-bc02-08e05b6d7212" />
<img width="1914" height="1029" alt="3" src="https://github.com/user-attachments/assets/4de5ff7e-9d3d-4ad7-b697-74dd0116fb33" />
<img width="1100" height="950" alt="4" src="https://github.com/user-attachments/assets/77a392d3-4c74-4eb0-80cc-7061bd4b518a" />

