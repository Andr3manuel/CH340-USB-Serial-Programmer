# CH340-USB-Serial-Programmer

CH340C USB-to-UART bridge with auto-flash circuit for ESP32/ESP32-CAM. Features pre-crossed TX/RX lines and safe 3.3V/5V logic interfacing for Arduino targets.


A versatile and safe USB-to-Serial bridge designed to take the hassle out of flashing microcontrollers. While most generic CH340 adapters require manual button presses to flash Espressif chips, this board features a built-in \*\*auto-reset circuit\*\*, making it a true "plug \& play" solution for the \*\*ESP32\*\* and \*\*ESP32-CAM (WROOM)\*\*.



\## 🎯 Primary Targets



\* \*\*ESP32 \& ESP32-CAM (WROOM):\*\* Features an integrated dual-NPN transistor bridge (SS8050S) driven by DTR and RTS signals. This automatically handles the `EN` (Reset) and `IO0` (Boot) sequence required for seamless uploading in the Arduino IDE or PlatformIO.

\* \*\*Arduino Ecosystem:\*\* Fully compatible with ATMega boards (like the Pro Mini). The DTR pin provides the standard auto-reset functionality needed for standard Arduino flashing.



\## 🛡️ Safe Logic Interfacing (3.3V \& 5V)



One of the biggest issues with generic programmers is feeding 5V logic into a 3.3V ESP32. This board is designed for absolute safety:

\* \*\*Current-Limiting Protection:\*\* While the CH340C and UART lines operate at ~4.7V (5V USB via an SS34A protection diode), the `TX` and `RX` lines feature \*\*1kΩ series resistors\*\*. This safely limits the injection current to ~1mA, allowing the 3.3V target's internal clamping diodes to handle the signal without damage.

\* \*\*Clean 3.3V Auto-Reset:\*\* The NPN transistors driving the ESP32's `EN` and `BOOT` pins are pulled up directly to the onboard \*\*AMS1117-3.3V regulator\*\*, guaranteeing safe 3.3V logic levels for those critical pins.



\## 🔌 "Plug \& Play" Usability

\* \*\*Pre-Crossed UART:\*\* The `TX` and `RX` lines are already crossed on the PCB. Simply connect \*\*Programmer TX to Target TX\*\* and \*\*Programmer RX to Target RX\*\*. No more guessing wire orientations!

\* \*\*Selectable Power:\*\* Onboard jumper to supply either \*\*3.3V\*\* or \*\*5V (4.7V)\*\* to power your target board directly from the USB-C port.

