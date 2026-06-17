# Portable-Arduino-UNO-Shield
![KiCad](https://img.shields.io/badge/Design-KiCad-314CB0?logo=kicad)
## What is it?

A shield that you can use to upgrade older Arduino UNO boards such that your projects don't need extra batteries nor cables. Just the one your phone uses!

## How does it look?

<img width="1321" height="737" alt="image" src="https://github.com/user-attachments/assets/4830735e-faa8-4910-9517-6c89cc7b9ba3" />

## Physical details:
- **Input:** USB-C (5V, up to 2A for charging)
- **Battery:** 14500 Li-ion Rechargeable (3.7V, 500mAh)
- **Output:** 5V through boost converter ( -0.6V diode voltage drop when running on usb-c !!! )
- **Board Size:** Aprox. 91.5 × 53.4 mm

## Main components
- **Charging IC:** Handles the Li-ion charging (MCP73831-2-OT)
- **Boost Converter:** Steps up 3.7V from the battery to 5V for the Arduino (TPS61200DRC)
- **MOSFET:** Disconects the battery from output when current is fed from USB (PMOS)
- **Reverse Blocking Diode:** Makes sure current doesn't flow backward
- **ESD Diode:** Protects against static discharge on the USB data lines (USBLC6-2SC6)
- **USB to UART converter:** Translates the data lines to actual information (CH340E)

## Installation & usage
1. Pop the 14500 battery into the holder( <img width="52" height="93" alt="image" src="https://github.com/user-attachments/assets/2ab30bc8-fdae-4df0-ab16-1fcf39c804ec" /> Watch the polarity!)
2. Stack the shield onto your Arduino UNO
3. Plug in USB-C to charge (the LED being on means the battery charging)
4. When done charging, unplug and turn on the switch!

## Schematic
<img width="1066" height="743" alt="image" src="https://github.com/user-attachments/assets/fe58093a-e3a7-48c6-98e2-e1861abe47ca" />

## How would this prove useful?

Ever had a project that needed the arduino to be mounted somewhere such that a USB connection couldn't have been possible? I did.

## How did I make it?

I build it by integrating both a standard Li-ion charging circuit (MCP73831 reference design) with a boost converter topology and a USB-serial interface. Added my own custom changes to these, such as the LED and battery switch. It has been a wonderful experiment.

**Key Learnings:** decoupling capacitors, pull-down resistors, step-up boost converters usage, usb-to-uart translation as a requirement.
