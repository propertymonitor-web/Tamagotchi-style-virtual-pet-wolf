# Tamagotchi-style Virtual Pets for LoRa

A tiny pet that lives on your **LODESTAR ORION** radio. Pick one:

| Pet | Folder | Release |
|---|---|---|
| 🐺 **Wolf** | [`firmware/Wolf`](firmware/Wolf) | `wolf-v1.0.1-beta-UD21214` |
| 🦊 **Fox** | [`firmware/Fox`](firmware/Fox) | `fox-v1.0.1-beta-UD21214` |
| 🐱 **Cat** | [`firmware/Cat`](firmware/Cat) | `cat-v1.0.1-beta-UD21214` |
| 🐻 **Bear** | [`firmware/Bear`](firmware/Bear) | `bear-v1.0.1-beta-UD21214` |
| 🐷 **Pig** | [`firmware/Pig`](firmware/Pig) | `pig-v1.0.1-beta-UD21214` |
| 🐊 **Alligator** | [`firmware/Alligator`](firmware/Alligator) | `alligator-v1.0.1-beta-UD21214` |
| 🐊 **Crocodile** | [`firmware/Crocodile`](firmware/Crocodile) | `crocodile-v1.0.1-beta-UD21214` |
| 🦋 **Butterfly** | [`firmware/Butterfly`](firmware/Butterfly) | `butterfly-v1.0.1-beta-UD21214` |
| 🫏 **Donkey** | [`firmware/Donkey`](firmware/Donkey) | `donkey-v1.0.1-beta-UD21214` |
| 🦄 **Unicorn** | [`firmware/Unicorn`](firmware/Unicorn) | `unicorn-v1.0.1-beta-UD21214` |
| 🐉 **Dragon** (starts as an egg) | [`firmware/Dragon`](firmware/Dragon) | `dragon-v1.0.1-beta-UD21214` |
| 🦊 **Kitsune** | [`firmware/Kitsune`](firmware/Kitsune) | `kitsune-v1.0.1-beta-UD21214` |
| 🦅 **Griffin** (starts as an egg) | [`firmware/Griffin`](firmware/Griffin) | `griffin-v1.0.1-beta-UD21214` |
| 🔥 **Phoenix** (starts as an egg) | [`firmware/Phoenix`](firmware/Phoenix) | `phoenix-v1.0.1-beta-UD21214` |
| 🐴 **Horse** | [`firmware/Horse`](firmware/Horse) | `horse-v1.0.1-beta-UD21214` |
| 🥚 **Mystery Egg** | [`firmware/Mystery`](firmware/Mystery) | `mystery-v1.0.1-beta-UD21214` |

Every kind of pet can drop in on every other kind, so a fox might visit a wolf and a dragon might call on a pig. Families are another matter: pets only start a family with their own kind. Every one is different in its own way, and the
butterfly in particular has a long way to go before it's a butterfly.

**Eggs.** The dragon, griffin and phoenix start as an egg that hatches after 24 to 48 hours of the radio being switched on (it varies per pet). The **Mystery Egg** hatches
into a surprise: one of the pets above, picked from your radio's identity, so you get the same one every time you reflash it. Eggs only count time while the radio is powered on.
Only the Heltec V4 R2 has been tested; the new pets are untested on other boards.

A pet starts small. Look after it, keep your radio on, and see who it grows up to be.
No two wolves look alike, and it has a few surprises of its own. We're not going to list
them all here. Where's the fun in that?

> A LoRa mesh radio, a pocket pet, and a bit of mystery.
> Built on [MeshCore](https://github.com/meshcore-dev/MeshCore) · **LODESTAR ORION** by FEAR REACTIVE
> Created by **Aries Thorne & Todd Steinhauer**

---

## What you need

* A **Heltec V4** radio (the one with the OLED screen). **The Heltec V4 R2 is the only board that has been tested on real hardware.**
* Files for other radios are in the same pet folders (see *Other radios* below). They compile, but they are **UNTESTED**.
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

## Other radios (UNTESTED)

Only the **Heltec V4 R2** has been run on a real board. The boards below were built successfully but nobody has tried them yet, so please report what you see. Each board has its own folder inside each pet folder, for example `firmware/Fox/rak4631/US-mph/`.

| Board | Folder | Screen | Files |
|---|---|---|---|
| Heltec V3 | `heltec-v3` | OLED | `fresh-install.bin`, `update.bin` |
| LilyGo T3-S3 | `lilygo-t3s3` | OLED | `fresh-install.bin`, `update.bin` |
| Heltec Wireless Tracker | `heltec-tracker` | colour | `fresh-install.bin`, `update.bin` |
| Heltec Wireless Tracker V2 | `heltec-tracker-v2` | colour | `fresh-install.bin`, `update.bin` |
| LilyGo T-Deck | `lilygo-tdeck` | colour (scaling not confirmed) | `fresh-install.bin`, `update.bin` |
| RAK4631 | `rak4631` | OLED | `install-or-update.zip`, `full-image.hex` |
| Heltec T114 | `heltec-t114` | colour | `install-or-update.zip`, `full-image.hex` |
| Heltec T096 | `heltec-t096` | colour | `install-or-update.zip`, `full-image.hex` |
| Ikoka Nano G2 Ultra | `nano-g2-ultra` | OLED | `install-or-update.zip`, `full-image.hex` |

Colour screens draw the pet on a 128x64 canvas that is scaled up. The nRF52 boards (RAK, T114, T096, Nano G2 Ultra) use the `.zip` with the normal nRF52 update tools. Boards that do not fit: Heltec V2, LilyGo T-Beam SX1262 and T-LoRa V2.1 (out of memory) and Station G2 (too big for its flash).

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
* Pets are friendly. Other pets on nearby radios might drop in, whatever kind they are.

That's all you get.

## Good to know

* Your pet is saved to the radio's flash, so its age and sex survive reboots and power cuts (at worst you lose a few minutes of growth). **Use the `update` file for later versions**: the `fresh-install` file is for a radio that has never had the pet, and may wipe the radio's storage, which starts a new pet.
* Visits between wolves only happen between radios that can hear each other directly, both running this firmware.
* This is an early release. Found a bug, or a wolf behaving strangely? Please open an issue and tell us what your wolf was doing.

## Mesh Analyzer builds

Two versions of LODESTAR ORION that add a live **Mesh Analyzer** to the dashboard: every packet the radio hears is drawn as it arrives (signal strength, clarity, noise floor, packet types, hops, who it came from), and you can save it all as a CSV.

| Build | Folder | Release |
| --- | --- | --- |
| ORION + Mesh Analyzer (no pet) | [`firmware/Mesh-Analyzer`](firmware/Mesh-Analyzer) | `mesh-analyzer-v1.0.1-beta-UD21214` |
| ORION + Mystery Egg + Mesh Analyzer | [`firmware/Mystery-Mesh-Analyzer`](firmware/Mystery-Mesh-Analyzer) | `mystery-mesh-analyzer-v1.0.1-beta-UD21214` |

Open the dashboard at https://propertymonitor-web.github.io/lodestar_nova_alpha/ (Chrome or Edge, USB cable). The Mesh Analyzer panel appears by itself when the radio has this firmware. Each folder has a README that explains every graph and how to use it: [Mesh-Analyzer](firmware/Mesh-Analyzer/README.md), [Mystery-Mesh-Analyzer](firmware/Mystery-Mesh-Analyzer/README.md).

## What's new in 1.0.1 beta

* **Redrawn pets.** The **Dragon** is now a medieval western dragon (long neck, swept horns, bat wings, spiked back, taloned feet, barbed tail). The **Griffin** has a feathered wing and a hooked eagle beak. The **Cat** has whiskers and a rounder head. The **Crocodile** and **Alligator** are bigger, with teeth. Every pet still gets its own markings, coat, ears and tail from your radio's ID, so no two are alike.
* Fresh-install and update files for every pet and every supported radio. Use `update` to keep your pet.

## What's new in 1.0.0 beta

* **Everything is beta now.** Every release in this repository ends in `-UD21214` so you can tell the current builds from the old alpha ones.
* **Dashboard security fix.** The dashboard page no longer accepts anything from the radio's data that could be turned into page code. It is fixed on the live page (https://propertymonitor-web.github.io/lodestar_nova_alpha/). Thanks to a tester for finding it.
* **Heltec V4-R8.** The two Mesh Analyzer builds now include a `heltec-v4-r8` folder with files for the V4-R8 board.
* Pet names and kinds on the top line, the redrawn Griffin, and every pet visiting every other pet are all included. Updating with the `update` file keeps your pet.

## What's new in 0.7.0

* The Mystery Egg radio has a few more surprises in store.
* Small fixes under the hood. Nothing to do on your side; just flash the update file.

## What's new in 0.6.0

* **Name your pet.** Open the dashboard, find **Your pet**, type a name (up to 7 characters) and press **Set name**. The name shows at the top of the radio's screen and on the dashboard. You need the USB cable and the dashboard to set it. It names the pet on the screen right now, so each pet in a family can have its own name.
* The top line of the screen now reads like `F14mo Rex Wolf`: sex and age, the name, then the kind of pet. If it does not all fit, the kind is shortened or dropped.
* Your pet's save has a new format. Pets from older versions load fine, but once a radio has run 0.6.0 an older firmware cannot read its pet, so keep using the update files.

## What's new in 0.5.1

* **Pets visit every other kind of pet.** A fox can now call on a wolf, a pig on a dragon, and so on. Pets still only start a family with their own kind.
* A new pet: the **horse**.

## What's new in 0.4.0

* New pets: **donkey, unicorn, dragon, kitsune, griffin, phoenix**, each with its own tricks.
* The **dragon, griffin and phoenix start as an egg**, and the **Mystery Egg** hatches into a surprise. Eggs hatch after 24 to 48 hours of the radio being on.

## What's new in 0.3.1

* Safer saving: your pet is saved in two places, every 10 minutes and whenever something happens, so a power cut in the middle of a save can't lose it. A pet's sex is now fixed by its radio.

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
