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

I know that some of these parts can be found much cheaper through websites such as Seeed or LCSC. However, I live in Italy, and shipping can make a big difference. Even if the components are cheap, international shipping, VAT, and other import costs can make the final price almost the same as buying from Amazon.

Amazon is also more convenient for this project because the shipping is faster and returns are easier. There was a time when websites such as AliExpress were much cheaper for these types of components, but taxes and import costs for products from China have increased in the EU. Because of this, the Amazon prices were the most practical option for me, even though the individual parts cost more. 


| Part | What it is used for | Quantity | Price | Vendor |
|---|---|---:|---:|---|
| [XIAO ESP32-C3]([https://www.amazon.it/dp/B0GQS8K54W ]([https://it.aliexpress.com/item/1005008791937363.html?spm=a2g0o.cart.0.0.6ab418fcxEWY8e&mp=1&pdp_npi=6%40dis%21EUR%21EUR+9.99%21EUR+9.99%21%21EUR+9.99%21%21%21%400b88abba17926478517746365e0c42%2112000052930246748%21ct%21IT%218194849047%21%211%210%21&gatewayAdapt=glo2ita](https://www.amazon.it/ESP32-C3-XIAO-Bluetooth-Dual-Mode-Interfaccia/dp/B0GQS8K54W/ref=sr_1_2_sspa?__mk_it_IT=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3QKX5NNHQE2ZC&dib=eyJ2IjoiMSJ9._SAf8VV9Xs50mPb3GynPf5q)_)) | Main microcontroller and Wi-Fi | 1 | $20.19 | Amazon Italy |
| [0.96-inch OLED](https://www.amazon.it/dp/B0GKDNWT82 ) | Displays the pet and sensor readings | 1 | $13.46 | Amazon Italy |
| [MPU6050](https://www.amazon.it/dp/B07BVXN2GP ) | Motion and gyroscope sensor | 1 | $7.85 | Amazon Italy |
| [DHT11](https://www.amazon.it/dp/B0CK195FRJ ) | Temperature and humidity sensor | 1 | $10.09 | Amazon Italy |
| [MX switch](https://www.amazon.it/dp/B0H2HPJPKW ) | User input button | 1 | $8.97 | Amazon Italy |
| [Keycaps](https://www.amazon.it/dp/B0F1YQTQMD ) | Covers for the switches | 1 | $16.36 | Amazon Italy |
| [PCB fabrication](https://jlcpcb.com/ ) | Manufacturing the custom PCB | 1 | $9.16 | JLCPCB |

- Parts subtotal: **$86.08**
- Tax and shipping: **$11.75**
- Total: **$97.83**



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

<img width="3840" height="2160" alt="665674551-57f0e280-d2bf-4604-b259-fa0ea4802df7" src="https://github.com/user-attachments/assets/27de648b-78fc-4e90-82ae-fd1baa80a4bc" />
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

