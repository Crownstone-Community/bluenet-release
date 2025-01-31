# Bluenet

[![License: LGPL v3](https://img.shields.io/badge/License-LGPL%20v3-blue.svg)](http://www.gnu.org/licenses/lgpl-3.0)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Bluenet is the code running on the [Crownstone](http://crownstone.rocks) and Guidestone. Each Crownstone or Guidestone is a node in a network that uses signal strength for indoor localization of smartphones and wearables.

This Repository keeps track of the released version of bluenet. For the code have a look [here](https://github.com/crownstone/bluenet)

# Releases

## Firmware 5.7.0
- Added microapp support.
- Added double tap switchcraft.
- Energy is no longer reset when the Crownstone soft resets.
- Fixed bug where energy would not accumulated anymore.

## Bootloader 2.2.0
- Changed IPC ram layout.

## Firmware 5.6.4
- Fixed bug in extended behaviour.

## Firmware 5.6.3
- Fixed crash in factory reset mode.
- Fixed crash when a device connected and very quickly disconnected again.
- Fixed low chip voltage detection not being enabled.

## Firmware 5.6.2
- Restore behaviour enabled/disabled on boot.
- Added synchronizing of behaviour enabled/disabled on boot.
- Fixed crash on incoming connect.

## Firmware 5.6.1
- Fixed crash on outoing connect.

## Firmware 5.6.0
- Added more asset filtering features.
- Fixed bug in tracked devices.
- Fixed softfuse.

## Firmware 5.5.0
- Added asset filtering.
- Added mesh topology.
- Added outgoing connections.

## Firmware 5.4.2
- Handle mesh messages from 255 devices instead of 40.

## Firmware 5.4.1
- Fixed UART not listening when in setup mode.

## Firmware 5.4.0
- Breaking change of UART protocol.
- Implemented UART encryption.
- Added time synching.
- Added hub support.
- Added binary logger.

## Firmware 5.3.0
- New UART protocol.
- Built-in One can now measure up to 16A.
- Improved power measurement smoothing.
- Added debug switch buffer.
- Fixed background advertisement validation timestamp check.

## Firmware 5.2.1
- Fixed crash when setting switchcraft threshold.

## Firmware 5.2.0
- Improved switch detection for slower wall switches.
- Dimming allowed is disabled when dimmer softfuse is triggered.
- Added debug command to get RAM stats.
- Added debug command to clean flash.
- Fixed tracked device heartbeat.
- Fixed bug where turning switch on (255), with an active twilight, and dimming not allowed, would result in the switch being turned off again.
- Fixed debug softfuse buffer.
- Fixed ADC channel swap.

## Firmware 5.1.0
- Added soft on: slowly transition to new dim value in less than a second.
- Added debug commands (uptime, switch history, power samples, etc).
- Added tracked devices heartbeat command.
- Throttle set time and suntimes, to prevent times going back and forth.
- Limited dim value to minimum of 10% as workaround for hardware.
- Added more ADC buffers, leading to barely any restarts.
- Fixed bug in median filter of power samples.
- Added workaround for switchcraft to handle voltage measurement peaks.
- Fixed crash when receiving an advertisement with a field of len 0.

## Firmware 5.0.1
- Persist ibeacon config id activation.
- Added control command result to UART.
- Fixed dumb home mode.
- Fixed mesh command results.
- Fixed tracked devices never timing out.

## Firmware 5.0.0
- Added watchdog.
- Added state/config set via mesh.
- Added persistence mode to state get/set.
- Added iBeacon interleaving.
- Added IPC, enabling to get the bootloader version while not in DFU mode.
- Improved zero power calibration.
- Fixed stones ignoring messages of other stones in the mesh.
- Fixed some behaviour bugs.
- Fixed dimmer intensity inversion.

## Bootloader 2.1.0
- Added bootloader info that can be read by application.
- Changed the GPREGRET is used.

## Crownstone 4.0.1
- Fixed bug that would get the firmware in a bootloop, due to flash corruption.

## Crownstone 4.0.0
- First release with behaviours.
- Characteristics and protocol changes.

## Crownstone 3.0.6
- Also scan only 75% of the time with the plug 1B2C and builtin 1B1D.

## Crownstone 3.0.5
- Fixed plugs getting low voltage, by scanning only 75% of the time.
- Fixed bug where setup would wait forever on Guidestones and USB sticks.
- Turn on switch when upgrading from firmware version 2.

## Crownstone 3.0.4
- Fixed false detection of dimmer on failure, by decreasing ADC timeout.

## Crownstone 3.0.3
- Fixed crash in FDS init when upgrading from firmware version 2.

## Crownstone 3.0.2
- Fixed dimming, by always using the crystal HF clock.

## Crownstone 3.0.1
- Fixed bug where state of other Crownstones would be advertised for too long.

## Crownstone 3.0.0
- First release with SDK 15
- First release with official Bluetooth Mesh.

## Crownstone 2.1.2
- Changed mesh channel to 37.

## Crownstone 2.1.0
- Setup is now a single command.
- RSSI between mesh nodes is now advertised.
- First version of Switchcraft.
- Advertisements now always use the same service UUID, device type is in the payload.
- Writing switch state to flash now (most of the times) takes a few ms instead of >100ms.
- Improved ADC: stable sampling frequency, and detects when a stall happened.
- Fixed bug where UART TX would stop working.

## Crownstone 2.0.2
- If no board version is in UICR, the default hardware board is written.

## Crownstone 2.0.1
- Dimmer state is no longer restored on boot, relay is used instead (to prevent unnecessary relay toggles when crownstone is behind wall switch).
- Switch lock is disabled when enabling dimming. There is no use case for having both enabled.
- Mesh is no longer flooded by state messages: max 1 state message per 3s is sent.
- Fixed bug where relay was toggled when changing dim value while dimming is not available.
- Fixed bug where relay was being turned on/off while already turned on/off when changing dim value.

## Crownstone 2.0.0
- Crownstone IDs are now 1B, this changed a lot of protocol.
- Changed advertisement protocol to include more data.
- Crownstones now send their state over the mesh.
- Crownstones can now be controlled over the mesh.
- Added switch lock.
- Added config to allow dimming.
- Added energy calculation (cleared on reboot though).
- Added binary UART protocol.
- Added dimming to only start X seconds after boot.
- Added IGBT failure detection.

## Crownstone 1.7.1
- Changed soft fuse to turn relay on when IGBTs are overloaded (temperature or current).

## Crownstone 1.7.0
- Dimming now done by trailing edge dimming (currently only works for 50Hz).
- Dimmer state is stored in persistent storage, and restored on boot (currently with a delay of about 2s).
- Overcurrent detection is relaxed to avoid getting triggered by interference. This lead to slower overcurrent detection though (~400ms).
- Fixed bug where a mesh message on an invalid handle would lead to a crash.

## Crownstone 1.6.0
- Added support for boards ACR01B2G and ACR01B6C.

## Bootloader 1.3.0
- Added support for boards ACR01B2G and ACR01B6C.

## Crownstone 1.5.1
- Enabled sharing time via mesh.

## Crownstone 1.5.0
- Added: schedule functionality: the crownstone can be scheduled to turn on/off at certain times.
- Added: configurable soft fuses.
- Added: also reset relay on a factory reset.
- Added: turn on relay after an hour in setup mode, for built-in crownstones.
- Fixed: unset error bit in advertisement when state errors are reset.

## Crownstone 1.4.0
- Use crystal for low frequency clock.

## Crownstone 1.3.3
- Fixed crashes on disconnect.

## Crownstone 1.3.1
- Added safety measures.
- Keep advertising while connected.
- Connections time out when nothing is written (helps against zombie connections from certain phones).
- Added command to increase TX power during setup.

## Guidestone 1.1.0

## Crownstone Plug 1.1.0

## Crownstone Plug 1.0.0

# Instructions

The above releases are automatically rolled out through our infrastructure towards all bluenet running devices (under which the Crownstone switches and plugs). Release 2.1.4 is the latest release with an unsecure bootloader, after this release a secure bootloader is used. Tools like `nrfutil pkg display "crownstone_*.zip"` only work on the new .zip files.

# Copyrights

The copyrights (2014-2017) belongs to the team of Crownstone B.V. and are provided under an noncontagious open-source license:

* Authors: Dominik Egger, Bart van Vliet, Anne van Rossum, Marc Hulscher, Peet van Tooren, Alex de Mulder, Christian Haas
* Date: 27 Jan. 2014
* Triple-licensed: LGPL v3+, Apache, MIT
* Crownstone B.V., http://crownstone.rocks
* Rotterdam, The Netherlands

This code is built on the shoulders of giants. Our special thanks go to Christopher Mason for the initial C++ code base at [http://hg.cmason.com/nrf](http://hg.cmason.com/nrf) and Trond Einar Snekvik, department of Engineering Cybernetics at Norwegian University of Science and Technology (and Nordic Semiconductors) for the meshing functionality ([OpenMesh](https://github.com/NordicSemiconductor/nRF51-ble-bcast-mesh)).

# License

## Open-source license

This software is provided under a noncontagious open-source license towards the open-source community. It's available under three open-source licenses:
 
* License: LGPL v3+, Apache, MIT

<p align="center">
  <a href="http://www.gnu.org/licenses/lgpl-3.0">
    <img src="https://img.shields.io/badge/License-LGPL%20v3-blue.svg" alt="License: LGPL v3" />
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
  </a>
  <a href="https://opensource.org/licenses/Apache-2.0">
    <img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg" alt="License: Apache 2.0" />
  </a>
</p>

## Commercial license

This software can also be provided under a commercial license. If you are not an open-source developer or are not planning to release adaptations to the code under one or multiple of the mentioned licenses, contact us to obtain a commercial license.

* License: Crownstone commercial license

# Contact

For any question contact us at <https://crownstone.rocks/contact/> or on our discord server through <https://crownstone.rocks/forum/>.
