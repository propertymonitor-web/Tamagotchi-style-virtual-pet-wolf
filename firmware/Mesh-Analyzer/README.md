# LODESTAR ORION Mesh Analyzer

LODESTAR ORION with no pet and a live Mesh Analyzer on the dashboard. The same radio features as ORION, plus a way to see everything your radio hears.

**Heltec V4-R8:** the `heltec-v4-r8` folder holds the build for the V4-R8 board (ESP32-S3R8, 8 MB PSRAM). The R8 uses different pins for GPS, the LED and external power than the V4 R2, so use the R2 files on an R2 and the `heltec-v4-r8` files on an R8. Never power the radio without an antenna.

## What you get

A **Mesh Analyzer** panel on the dashboard. The radio reports every packet it hears or sends, and the page draws it live:

| Part of the panel | What it shows | How to use it |
| --- | --- | --- |
| **Heard** tile | Packets heard in the last minute, plus totals since the radio powered on and how many it sent | A quick feel for how busy your mesh is |
| **Signal** tile | Average and best signal strength (dBm) over the last minute | Closer to 0 is stronger. About -80 or better is strong, -100 is fair, below -115 is marginal |
| **Clarity** tile | Average SNR (dB), and the lowest SNR your radio setting can still decode | Higher is cleaner. A negative number is fine on LoRa, down to the limit shown |
| **Noise floor** tile | The quiet level of the channel, and how far above it your signals sit | A noise floor that jumps up means interference nearby. The bigger the gap above it, the safer the link |
| **Channel busy** tile | An estimate of how much of the last minute was spent receiving and sending (from the packet sizes and your radio settings) | Under 10% is comfortable. High numbers mean a crowded channel |
| **Nodes** tile | How many different senders or repeaters were heard in 10 minutes | Shows how much of the mesh you can reach |
| **Signal strength over time** | One dot per packet heard, coloured by type; a dashed red line marks the noise floor; short ticks along the bottom are packets you sent | Watch it scroll to see when signals come and go. Hover a dot for time, type, strength, SNR, hops, size and where it came from |
| **Signal quality** | Strength across, SNR up, for recent packets; the dashed red line is the lowest SNR your spreading factor can decode | Dots near or under the line are about to be lost. A move or antenna change should push the cloud up and to the right |
| **What is on the air** | Packet types in the time window (adverts, channel messages, direct messages, acks, paths and so on) | See what is taking up the airtime |
| **Hops the packets travelled** | Direct, 1 hop, 2 hops and so on | Mostly direct means you are close to the senders. Many hops means a long relay chain |
| **Who this radio hears** | The node each packet came from, how many packets, how recently, average and best strength, average SNR and a strength bar. Repeater names are filled in once the radio has heard their adverts | Find your best neighbours at a glance |

Buttons: **Show** picks the time window (1 minute, 5 minutes, 15 minutes, 1 hour). **Pause** freezes the graphs so you can look closely. **Save CSV** downloads every packet the page has kept. **Clear** empties the page's history.

## Getting started

1. Flash the radio at https://flasher.meshcore.io (Custom Firmware). Use the `fresh-install` file the first time. Use the `update` file on a radio that already runs LODESTAR ORION, so your settings are kept.
2. Pick your folder: `US-mph` (miles per hour) or `EU-UK-metric` (kilometres per hour), then your radio.
3. Plug the radio into your computer with a USB cable.
4. Open the dashboard at https://propertymonitor-web.github.io/lodestar_nova_alpha/ in **Chrome or Edge** (Safari and Firefox cannot talk to USB devices).
5. Press **Connect radio** and choose the radio's USB port. The Mesh Analyzer panel appears within a few seconds. If you only want to look around first, press **Try sample data** to see made-up traffic.

## Good to know

- The radio sends the packet stream only while the dashboard is open and connected. Nothing is stored on the radio and nothing is uploaded; the page keeps up to the latest 6,000 packets in your browser until you close or reload it. Use **Save CSV** to keep a session.
- The analyzer shows what the radio **decodes**. Packets lost in noise are not counted, so a quiet graph can mean a quiet mesh or a poor signal. Compare with the noise floor.
- "Heard from" is the last repeater on the packet's path, or the sender itself for a direct advert. It is the neighbour you actually receive, not necessarily the person who wrote the message.
- The channel-busy figure is an estimate from packet length and your spreading factor and bandwidth, not a measurement.
- This is a beta build. The radio's own screen, messages and GPS features work as in LODESTAR ORION; the analyzer only adds the data stream.
- Needs a Heltec V4 or another supported radio from this folder. The radio and the dashboard talk over USB, so Bluetooth to a phone still works as before while you are not connected to the dashboard.

## CSV columns

`time, direction (heard or sent), type, rssi_dbm, snr_db, hops, length_bytes, heard_from, origin_hash`

Made by Aries Thorne & Todd Steinhauer. LODESTAR ORION by FEAR REACTIVE. Built on MeshCore.
