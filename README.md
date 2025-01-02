# Locating Rogue SSIDs with Kismet
A basic signals intelligence project

## Scope
This project demonstrates how to use Kismet and a simple WiFi adapter card to locate rogue SSIDs within a given proximity.

## Disclaimer
Kismet is a powerful tool that is commonly used for [Wardriving](https://en.wikipedia.org/wiki/Wardriving). It is a passive, listen-only piece of softwware which makes no attempt to infiltrate, modify, or probe other networks or devices. Custom SSIDs which do not belong to me have been censored with black panels in the interest of preserving privacy. Ethical use of this tool should be your foremost priority at all times.

## Resources
### Hardware
* Laptop with Linux (Kali is most convenient due to preinstalled dependencies)
* Alfa AWUS036ACH WiFi Adapater

### Software
* Aircrack-NG
* Kismet

### Acknowledgements
* [Signals Intelligence with Kismet by SecurityFWD](https://www.youtube.com/watch?v=Qs9xPmUqzHI)
* [Configuring the Alpha AWUS036ACH Wi-Fi Adapter on Kali Linux](https://hackernoon.com/configuring-the-alpha-awus036ach-wi-fi-adapter-on-kali-linux)

## Installation

### Kismet

Kismet is preinstalled on Kali Linux. If using another distro, refer to the [official installation documentation on Kismet's website](https://www.kismetwireless.net/docs/readme/installing/linux/).
I highly recommend using Kali Linux as the only installations needed are the chipset drivers for your WiFi adapter, which greatly simplifies the process.

### Drivers

Driver installation for my particular WiFi adapter is a simple process and can be referenced in the _Acknowledgements_ section above. That tutorial also shows how to put your WiFi adapter into monitoring mode.

## Setup and Usage

After installing your drivers and enabling monitoring mode, it's time to launch Kismet. In your console, type `sudo kismet -c wlan1`. This launches Kismet and displays the live data gathered by the WiFi adapter.

You will observe new device detections within the console:

<br>![LaunchedTerminal](https://github.com/user-attachments/assets/c470fffd-3b04-444e-a4e5-439a972a4589)


<br>However, the information we're after is better viewed in a GUI. Tab to your browser and navigate to `http://localhost:2501` and create an account and password:

<br>![AdminPanel](https://github.com/user-attachments/assets/6a3464e7-f6b0-4678-a87d-67496ca9c327)

<br>Once you create your account, you're provided with a more legible view of the incoming data:

<br>![GeneralKismet](https://github.com/user-attachments/assets/72b2374f-5967-4b29-b93d-6baf1e7cf7dd)

