# Locating Rogue SSIDs with Kismet
A basic signals intelligence project

## Scope
This project demonstrates how to use Kismet and a simple WiFi adapter card to locate rogue SSIDs within a given proximity.

## Resources
### Hardware
* Laptop with Linux (Kali is most convenient due to preinstalled dependencies)
* Alfa AWUS036ACH WiFi Adapater

### Software
* Aircrack-NG
* Kismet

## Installation

### Installing Kismet

Kismet is preinstalled on Kali Linux. If using another distro, refer to the official installation documentation on Kismet's website (https://www.kismetwireless.net/docs/readme/installing/linux/)

## Setup and Usage

After installing all necessary software and drivers, it's time to launch Kismet. In your console, type `sudo kismet -c wlan1`. This launches Kismet and displays the live data gathered by the WiFi adapter in monitor mode.

You will observe new device detections within the console:


![LaunchedTerminal](https://github.com/user-attachments/assets/c470fffd-3b04-444e-a4e5-439a972a4589)



However, the information we're after is better viewed in a GUI. Tab to your browser and navigate to `http://localhost:2501` and create an account and password:


![AdminPanel](https://github.com/user-attachments/assets/6a3464e7-f6b0-4678-a87d-67496ca9c327)

Once you create your account, you're provided with a more legible view of the incoming data:

![GeneralKismet](https://github.com/user-attachments/assets/143b3929-faf4-4535-b002-3ebb381f6833)
