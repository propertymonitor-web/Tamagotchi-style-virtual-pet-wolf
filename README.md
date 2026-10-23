# Tamagotchi-style Virtual Pets for LoRa

A tiny pet that lives on your **LODESTAR ORION** radio. Pick one:

| Pet | Folder | Release |
|---|---|---|
| 🐺 **Wolf** | [`firmware/Wolf`](firmware/Wolf) | `wolf-v0.3.0-alpha` |
| 🦊 **Fox** | [`firmware/Fox`](firmware/Fox) | `fox-v0.3.0-alpha` |
| 🐱 **Cat** | [`firmware/Cat`](firmware/Cat) | `cat-v0.3.0-alpha` |
| 🐻 **Bear** | [`firmware/Bear`](firmware/Bear) | `bear-v0.3.0-alpha` |
| 🐷 **Pig** | [`firmware/Pig`](firmware/Pig) | `pig-v0.3.0-alpha` |
| 🐊 **Alligator** | [`firmware/Alligator`](firmware/Alligator) | `alligator-v0.3.0-alpha` |
| 🐊 **Crocodile** | [`firmware/Crocodile`](firmware/Crocodile) | `crocodile-v0.3.0-alpha` |
| 🦋 **Butterfly** | [`firmware/Butterfly`](firmware/Butterfly) | `butterfly-v0.3.0-alpha` |

Each pet only talks to its own kind, so a fox never confuses a wolf, and a crocodile never mistakes an alligator for family. Every one is different in its own way, and the
butterfly in particular has a long way to go before it's a butterfly.

A pet starts small. Look after it, keep your radio on, and see who it grows up to be.
No two wolves look alike, and it has a few surprises of its own. We're not going to list
them all here. Where's the fun in that?

> A LoRa mesh radio, a pocket pet, and a bit of mystery.
> Built on [MeshCore](https://github.com/meshcore-dev/MeshCore) · **LODESTAR ORION** by FEAR REACTIVE
> Created by **Aries Thorne & Todd Steinhauer**

---

## What you need

* A **Heltec V4** radio (the one with the OLED screen). The pet lives on that screen, so other boards won't show it.
* A way to flash it: <https://flasher.meshcore.io> (choose **Custom Firmware**).
* Optional, but half the fun: a friend with a second radio running the same firmware.

## Which file?

Open your pet's folder, then pick the one that matches how you like your speeds. The pet is the same in both.

| Folder | Speeds shown as | For |
|---|---|---|
| `US-mph` | miles per hour | US |
| `EU-UK-metric` | kilometres per hour | EU, UK and everywhere else |

Each folder has two files:

* **`…fresh-install.bin`**: use this the first time you put the wolf on a radio.
* **`…update.bin`**: use this later to update a radio that already has the wolf.

(Radio frequency settings are not part of the firmware. Set your region's frequency in the
MeshCore app as usual.)

## Flashing

1. Download the `fresh-install` file for your region.
2. Open <https://flasher.meshcore.io> in Chrome or Edge, plug in your Heltec V4 over USB.
3. Choose **Custom Firmware**, pick the file, and flash.
4. When the radio restarts you will see the **ORION splash screen**, and then your wolf.

Want to check your download? [`firmware/SHA256SUMS.txt`](firmware/SHA256SUMS.txt) has the checksums.

## Using it

Your wolf is the first screen after the splash.

| Button | On the wolf screen |
|---|---|
| click | next page |
| double click | screen off (any click wakes it) |
| long press | look at the next pet in your pack, if you have more than one |
| **fast triple click** | from any other screen: straight back to your pet (on the pet screen it toggles the buzzer, as usual) |

Everything else on the radio works exactly like normal MeshCore. Messages, channels, the lot.
The wolf is just one extra page at the front.

## Dashboard: watch your pet on a big screen

**This is the dashboard for the LODESTAR ORION + Pet firmware** (every file in this repo). It is the normal
LODESTAR ORION dashboard page; when it is connected to a radio running one of these pet builds, a **Your pet** panel
appears at the top and shows exactly what is on the radio's screen, enlarged. Good for a laptop, a TV or a projector.

1. Plug the radio into your computer with a USB **data** cable.
2. Open **<https://propertymonitor-web.github.io/lodestar_nova_alpha/>** in **Chrome or Edge**.
3. Click **Connect radio** and pick the radio's port.
4. The pet appears. **Full screen** fills the display, **Save picture** takes a snapshot, **Pixel grid** gives it the OLED look.

The radio only sends the picture while the page is open and connected. Nothing leaves your computer. Without a pet
firmware the panel simply never appears. Your phone can stay connected over Bluetooth the whole time.

## A few hints (and only a few)

* It grows up while the radio is **powered on**, so give it time.
* It notices what your radio is doing.
* Its looks come from your radio, so yours is one of a kind.
* Leave it running and watch for a while. It doesn't do the same thing twice in a row.
* Wolves are friendly. Other wolves on nearby radios might drop in.

That's all you get.

## Good to know

* Your wolf is saved to the radio's flash, so it survives reboots. A sudden power cut can lose a little growth.
* Visits between wolves only happen between radios that can hear each other directly, both running this firmware.
* This is an early release. Found a bug, or a wolf behaving strangely? Please open an issue and tell us what your wolf was doing.

## What's new in 0.3.0

* **Watch your pet on the dashboard**: see the [dashboard section](#dashboard-watch-your-pet-on-a-big-screen).

## What's new in 0.2.0

* Three new pets: **pig, alligator, crocodile**. They look different from each other, and each one has its own tricks.
* **Fast triple click** takes you back to the pet from any other screen.
* The alligator and crocodile show a short dedication card after the ORION splash.

## Credits

* **LODESTAR ORION**: FEAR REACTIVE
* **Pets and splash**: created by Aries Thorne & Todd Steinhauer
* Based on [MeshCore](https://github.com/meshcore-dev/MeshCore) (MIT licence)
