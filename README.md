Riscflight is flight controller software (firmware) used to fly multi-rotor craft and fixed wing craft. It is a fork of Betaflight to the Risc-V processor family, initial development is using the K210 SOC on Seeed Maix boards.

The first milestone is to get it to the point that I can get a quad in the air, and hopefully some people crazy enough to test how it flys. I plan on keeping version numbering in parity with Betaflight.

## Alpha 1 - Roadmap (Initial Port)

- 4.2-K210-M1 - Getting it building in 32 bit mode
- 4.2-K210-M2 - IO and PID loop/Gyro on different cores
- 4.2-K210-M3 - ESC communication working
- 4.2-K210-M4 - Full IMU support
- 4.2-K210-M5 - Receiver Support
- 4.2-K210-M6 - VTX/DJI Support
- 4.2-K210-M7 - Publishing how to DIY your own setup
- 4.2-K210-A1 - Alpha 1 Release

## Alpha 2 - Roadmap (64 bit mode)

- 4.2-K210-64-M1 - 64 bit building
- 4.2-K210-64-M2 - IO and PID loop/Gyro - 64 bit
- 4.2-K210-64-M3 - ESC communication - 64 bit
- 4.2-K210-64-M4 - Full IMU support - 64 bit
- 4.2-K210-64-M5 - Receiver Support - 64 bit
- 4.2-K210-64-M6 - VTX/DJI Support - 64 bit
- 4.2-K210-64-A2 - Alpha 2 Release

## Alpha 3 - K210 - Neural Core Filtering

## Events

| Date  | Event |
| - | - |


## News

### Requirements for the submission of new and updated targets

The following new requirements for pull requests adding new targets or modifying existing targets are put in place from now on:

1. No new F3 based targets will be accepted;

2. For any new target that is to be added, only a Unified Target config into https://github.com/betaflight/unified-targets/tree/master/configs/default needs to be submitted. See the [instructions](https://github.com/betaflight/betaflight/blob/master/docs/TargetMaintenance/CreatingAUnifiedTarget.md) for how to create a Unified Target configuration. If there is no Unified Target for the MCU type of the new target (see instructions above), then a 'legacy' format target definition into `src/main/target/` has to be submitted as well;

3. For changes to existing targets, the change needs to be applied to the Unified Target config in https://github.com/betaflight/unified-targets/tree/master/configs/default. If no Unified Target configuration for the target exists, a new Unified Target configuration will have to be created and submitted. If there is no Unified Target for the MCU type of the new target (see instructions above), then an update to the 'legacy' format target definition in `src/main/target/` has to be submitted alongside the update to the Unified Target configuration.


## Features

Betaflight has the following features:

* Multi-color RGB LED strip support (each LED can be a different color using variable length WS2811 Addressable RGB strips - use for Orientation Indicators, Low Battery Warning, Flight Mode Status, Initialization Troubleshooting, etc)
* DShot (150, 300, 600 and 1200), Multishot, and Oneshot (125 and 42) motor protocol support
* Blackbox flight recorder logging (to onboard flash or external microSD card where equipped)
* Support for targets that use the STM32 F7, F4 and F3 processors
* PWM, PPM, and Serial (SBus, SumH, SumD, Spektrum 1024/2048, XBus, etc) RX connection with failsafe detection
* Multiple telemetry protocols (CSRF, FrSky, HoTT smart-port, MSP, etc)
* RSSI via ADC - Uses ADC to read PWM RSSI signals, tested with FrSky D4R-II, X8R, X4R-SB, & XSR
* OSD support & configuration without needing third-party OSD software/firmware/comm devices
* OLED Displays - Display information on: Battery voltage/current/mAh, profile, rate profile, mode, version, sensors, etc
* In-flight manual PID tuning and rate adjustment
* Rate profiles and in-flight selection of them
* Configurable serial ports for Serial RX, Telemetry, ESC telemetry, MSP, GPS, OSD, Sonar, etc - Use most devices on any port, softserial included
* VTX support for Unify Pro and IRC Tramp
* and MUCH, MUCH more.

## Installation & Documentation

See: https://github.com/betaflight/betaflight/wiki

## Support and Developers Channel

There's a dedicated Slack chat channel here:

https://slack.betaflight.com/

Etiquette: Don't ask to ask and please wait around long enough for a reply - sometimes people are out flying, asleep or at work and can't answer immediately.

## Configuration Tool

To configure Betaflight you should use the Betaflight-configurator GUI tool (Windows/OSX/Linux) which can be found here:

https://github.com/betaflight/betaflight-configurator/releases/latest

## Contributing

Contributions are welcome and encouraged. You can contribute in many ways:

* implement a new feature in the firmware or in configurator (see [below](#Developers));
* documentation updates and corrections;
* How-To guides - received help? Help others!
* bug reporting & fixes;
* new feature ideas & suggestions;
* provide a new translation for configurator, or help us maintain the existing ones (see [below](#Translators)).

The best place to start is the Betaflight Slack (registration [here](https://slack.betaflight.com/)). Next place is the github issue tracker:

https://github.com/betaflight/betaflight/issues
https://github.com/betaflight/betaflight-configurator/issues

Before creating new issues please check to see if there is an existing one, search first otherwise you waste people's time when they could be coding instead!

If you want to contribute to our efforts financially, please consider making a donation to us through [PayPal](https://paypal.me/betaflight).

If you want to contribute financially on an ongoing basis, you should consider becoming a patron for us on [Patreon](https://www.patreon.com/betaflight).

## Developers

Contribution of bugfixes and new features is encouraged. Please be aware that we have a thorough review process for pull requests, and be prepared to explain what you want to achieve with your pull request.
Before starting to write code, please read our [development guidelines](docs/development/Development.md ) and [coding style definition](docs/development/CodingStyle.md).

TravisCI is used to run automatic builds

https://travis-ci.com/betaflight/betaflight

[![Build Status](https://travis-ci.com/betaflight/betaflight.svg?branch=master)](https://travis-ci.com/betaflight/betaflight)

## Translators

We want to make Betaflight accessible for pilots who are not fluent in English, and for this reason we are currently maintaining translations into 18 languages for Betaflight Configurator: Català, Deutsch, Español, Euskera, Français, Galego, Hrvatski, Bahasa Indonesia, Italiano, 日本語, 한국어, Latviešu, Português, Português Brasileiro, polski, Русский язык, Svenska, 简体中文.
We have got a team of volunteer translators who do this work, but additional translators are always welcome to share the workload, and we are keen to add additional languages. If you would like to help us with translations, you have got the following options:
- if you help by suggesting some updates or improvements to translations in a language you are familiar with, head to [crowdin](https://crowdin.com/project/betaflight-configurator) and add your suggested translations there;
- if you would like to start working on the translation for a new language, or take on responsibility for proof-reading the translation for a language you are very familiar with, please head to the Betaflight Slack (registration [here](https://slack.betaflight.com/)), and join the '#team\_translation' channel - the people in there can help you to get a new language added, or set you up as a proof reader.

## Betaflight Releases

https://github.com/betaflight/betaflight/releases

## Open Source / Contributors

Betaflight is software that is **open source** and is available free of charge without warranty to all users.

Betaflight is forked from Cleanflight, so thanks goes to all those whom have contributed to Cleanflight and its origins.

Origins for this fork (Thanks!):
* **Alexinparis** (for MultiWii),
* **timecop** (for Baseflight),
* **Dominic Clifton** (for Cleanflight),
* **borisbstyle** (for Betaflight), and
* **Sambas** (for the original STM32F4 port).

The Betaflight Configurator is forked from Cleanflight Configurator and its origins.

Origins for Betaflight Configurator:
* **Dominic Clifton** (for Cleanflight configurator), and
* **ctn** (for the original Configurator).

Big thanks to current and past contributors:
* Budden, Martin (martinbudden)
* Bardwell, Joshua (joshuabardwell)
* Blackman, Jason (blckmn)
* ctzsnooze
* Höglund, Anders (andershoglund)
* Ledvina, Petr (ledvinap) - **IO code awesomeness!**
* kc10kevin
* Keeble, Gary (MadmanK)
* Keller, Michael (mikeller) - **Configurator brilliance**
* Kravcov, Albert (skaman82) - **Configurator brilliance**
* MJ666
* Nathan (nathantsoi)
* ravnav
* sambas - **bringing us the F4**
* savaga
* Stålheim, Anton (KiteAnton)

And many many others who haven't been mentioned....
