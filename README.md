STARBIE
 a tiny motion control digital pet that lives on a star-shaped PCB 
 ##Hardware 
- **Seeed XIAO ESP32-C3**: the microcontroller that runs everything
- **0.96" SSD1306 OLED (128x64)**: the screen Starbie lives on
- **MPU6050**: accelerometer/gyro for tilt and shake controls
- **DHT11**: temperature and humidity sensor
- **2 Cherry MX switches**: buttons for the menu and stats screen
- **10k resistor**: pull-up for the DHT11

The OLED and MPU6050 share the same I2C lines. The DHT11 is on D1, and the buttons are on D2 and D3.

## How it works
| Control | What it does |
|---|---|
| Button 1 | Opens the radial menu / picks the highlighted option |
| Tilt (menu open) | Moves the selector |
| Button 2 | Shows or hides the stats screen |
| Shake | Starbie does a shake reaction |
Menu options: **NAP**, **PLAY**, **FEED**, and **PET**, each with its own animation.

## What I did
- Designed the schematic and PCB in **KiCad 10**, including the star-shaped board outline
- Routed the board using both copper layers with a ground pour, and passed DRC
- Exported Gerbers for manufacturing
- Set up the firmware in **Arduino IDE** with the ESP32 board package and the required libraries
- Added a custom **sparkle trail** effect that blinks behind Starbie as it walks

## Files
- `MyStarbie/`: KiCad project, schematic, PCB, and Gerbers (`production/Starbie Gerbers.zip`)
- `Starbie.ino`: firmware with my sparkle edit
