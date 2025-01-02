# Locating Rogue SSIDs with Kismet
A basic signals intelligence project

## Scope
This project demonstrates how to use Kismet and a simple WiFi adapter card to locate rogue SSIDs within a given proximity.

## Disclaimer
Kismet is a powerful tool that is commonly used for [Wardriving](https://en.wikipedia.org/wiki/Wardriving). It is a passive, listen-only piece of software which makes no attempt to infiltrate, modify, or probe other networks or devices. Stationary residential SSIDs which do not belong to me have been censored with black panels in the interest of preserving privacy. Ethical use of this tool should be your foremost priority at all times.

## Resources
### Hardware
* 1x Linux device (Kali is most convenient due to preinstalled packages)
* 1x Alfa AWUS036ACH WiFi Adapater

### Software
* Aircrack-NG
* Kismet
* Chipset drivers for your chosen WiFi adapter

### Acknowledgements
* [Signals Intelligence with Kismet by SecurityFWD](https://www.youtube.com/watch?v=Qs9xPmUqzHI)
* [Configuring the Alpha AWUS036ACH Wi-Fi Adapter on Kali Linux](https://hackernoon.com/configuring-the-alpha-awus036ach-wi-fi-adapter-on-kali-linux)

## Installation

### Kismet

Kismet is preinstalled on Kali Linux. If using another distro, refer to the [official installation documentation on Kismet's website](https://www.kismetwireless.net/docs/readme/installing/linux/).
I highly recommend using Kali Linux as the only installation needed is the chipset driver for your WiFi adapter, which greatly simplifies the process.

### Drivers

Driver installation for my particular WiFi adapter is a simple process and can be referenced in the _Acknowledgements_ section above. That tutorial also shows how to put your WiFi adapter into monitoring mode.

## Initial Setup

After installing your drivers and enabling monitoring mode, it's time to launch Kismet. In your console, type `sudo kismet -c wlan1`. This launches Kismet and displays the live data gathered by the WiFi adapter.

You will observe new device detections within the console:

<br>![LaunchedTerminal](https://github.com/user-attachments/assets/c470fffd-3b04-444e-a4e5-439a972a4589)


<br>However, the information we're after is better viewed in a GUI. Tab to your browser and navigate to `http://localhost:2501` and create an account and password:

<br>![AdminPanel](https://github.com/user-attachments/assets/6a3464e7-f6b0-4678-a87d-67496ca9c327)

<br>Once you create your account, you're provided with a more legible view of the incoming data:

<br>![GeneralKismet](https://github.com/user-attachments/assets/72b2374f-5967-4b29-b93d-6baf1e7cf7dd)

## Data Columns

Kismet displays information about devices in an organized manner.  Depending on which view is selected, different information is displayed. The two views we are using are called _Devices_ and _SSIDs_.

<br>![4Panels](https://github.com/user-attachments/assets/e1dec70a-6484-448c-8845-d01dce809427)

<br>Depending on the selected view, different information is displayed to the user. The most pertinent datapoints are as follows:


### SSID

SSID stands for Service Set ID, and it represents the human-readable name of the device. This can be configured by the device owner. The default value often shares the brand name and model of the device.

### BSSID

BSSID stands for Base Service Set ID, and it uniquely identifies a specific WiFi network. This value cannot be changed. While this is not a MAC address, plugging this value into a MAC database will still likely yield the manufacturer name at the very least.

### Sgn

Sgn represents the signal strength emitted by the device in relation to your WiFi adapter. This is the most important value to consider when attempting to locate rogue SSIDs in your environment. As a rule of thumb, the closer this is to zero, the closer your WiFi adapter is to the device. Using a simple _hot and cold_ technique will likely result in the user locating the device.

## Other Uses

Aside from wardriving and locating rogue devices, Kismet is just a fun tool in general. While making this project, an airplane flew overhead and broadcasted its in-flight WiFi for a few minutes. It should be noted that, just like the cliched _FBI Spy Van_ SSID, always take SSIDs with a grain of salt. This is a user-configurable value and is not foolproof; this very well could have belonged to a passerby with a sense of humor.

<br>![UnitedAirlinesVerbose](https://github.com/user-attachments/assets/4e0ba654-3668-48c0-a4d5-e44a293391cf)

<br>Kismet data can be uploaded to Wigle.net, which is a wireless network mapping tool made possible by user-submitted data. It provides heatmaps of access points, along with their names. This is why it's prudent to redact any unique, user-configured SSIDs when doing projects like this, as that is not your information to share. Once again, ethics should be your foremost priority when using a tool like Kismet.

<br>![Wigle](https://github.com/user-attachments/assets/efbbee63-c4c2-4f6c-bd74-76622e90c1e1)

<br>Overall, Kismet is a fun tool to have in one's arsenal. From a hobbyist perspective, you get to see what's up, down, and around in the invisible world of networking. For more practical purposes, it's a solid bulwark against rogue SSIDs and shadow IT. Thanks for reading!
