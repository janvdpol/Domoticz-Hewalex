# Domoticz-Hewalex
Domoticz plugin to integrate Hewalex heat and solar pumps

Tested with Python version 3.8, Domoticz versions 2020.2 and 2021.1

## Prerequisites

### Heat pumps (PCWU)

RS485 to Wi-Fi device setup and either eavesdropping on the communication between the G-426 controller and the PCWU or communicating directly to the PCWU over a dedicated RS485 port. Eavesdropping is easier to setup and allows reading temperatures but does not allow control over the pump. See https://github.com/mvdklip/hewalex-geco-protocol/tree/main/docs/PCWU for more information.

### Solar pumps (ZPS)

RS485 to Wi-Fi device setup and connected to the RS485 port on the backside of the G-422 controller. https://github.com/mvdklip/hewalex-geco-protocol/tree/main/docs/ZPS for more information.

## Installation

Assuming that domoticz directory is installed in your home directory.

```bash
cd ~/domoticz/plugins
git clone https://github.com/mvdklip/Domoticz-Hewalex
# restart domoticz:
sudo /etc/init.d/domoticz.sh restart
```
In the web UI, navigate to the Hardware page and add an entry of type "Hewalex".

Make sure to (temporarily) enable 'Accept new Hardware Devices' in System Settings so that the plugin can add devices.

Afterwards navigate to the Devices page and enable the newly created devices.

## Known issues

## Updating

Like other plugins, in the Domoticz-Hewalex directory:
```bash
git pull
sudo /etc/init.d/domoticz.sh restart
```

## Parameters

| Parameter | Value |
| :--- | :--- |
| **IP address** | IP of the RS485 to Wi-Fi device eg. 192.168.1.231 |
| **Port** | Port of the RS485 to Wi-Fi device eg. 8899 |
| **Device & Mode** | Device type and mode of communication |
| **Query interval** | how often is data retrieved |
| **Debug** | show debug logging |

## Acknowledgements

Based on

https://www.elektroda.pl/rtvforum/topic3499254.html \
https://github.com/aelias-eu/hewalex-geco-protocol
