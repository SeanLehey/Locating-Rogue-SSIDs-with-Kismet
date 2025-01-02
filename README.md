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

After installing all necessary software and drivers, it's time to launch Kismet. In your console, type `sudo kismet -c wlan1`. This launches Kismet and incorporates the live data gathered by the WiFi adapter in monitor mode.

You will observe new device detections within the console:

>picturehere<

However, the information we're after is more conveniently viewed in a GUI. Tab to your browser and navigate to `http://localhost:2501` and create an account and password:

