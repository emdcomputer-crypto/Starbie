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

Starbie PCB Project 
I was already planning to make something similar to a starbie so that's why i chose this because it's guided and is a good starting project, i followed all the instructions here : https://github.com/SharKingStudios/Starbie/tree/main
How It Went & Problems I Fixed: 
After getting the schematic setup with the XIAO-ESP32-C3, OLED display, MPU6050, DHT11 sensor, and the two buttons, I hopped into KiCad's PCB Editor to start routing everything together.
Routing by hand got messy super fast, so I looked up some quick routing tips online to keep things clean and smooth. Instead of manually dragging every single ground line around the board,
I added a full-board GND copper pour across the top layer to handle all those ground connections automatically.
When running the Design Rules Check (DRC), a few specific errors popped up:   Trapped / Isolated Ground Pads: A few ground pads (like Pad 1 on the OLED, Pad 4 on the DHT11, and Pad 2 on J2) i searched online and a trace was blocking the ground pour from reaching them.
I fixed these by manually routing short bridge tracks from those pads out into the ground zone.
Once those were out of the way DRC cleared with 0 unconnected pads
