# Home Assistant Add-on: AMR2MQTT

[![GitHub Release][releases-shield]][releases]
![Project Stage][project-stage-shield]
[![License][license-shield]](LICENSE)

![Project Maintenance][maintenance-shield]
[![Community Forum][forum-shield]][forum]

_Runs rtl_tcp, rtlamr, and optional HomeLink RF detection to read meter data and send to MQTT._

## About

This add-on provides a modernized, multi‑service AMR/ERT meter reader for Home Assistant.  
It uses an RTL-SDR dongle to listen for signals from ERT‑compatible smart meters using  
[rtlamr][rtlamr], publishes decoded frames to MQTT, and optionally detects HomeLink  
garage remote button presses via RF energy spikes.

This version includes a fully updated architecture:

- `rtl_tcp` SDR backend  
- `rtlamr` AMR/ERT decoder  
- MQTT publisher  
- Optional HomeLink RF detector (315 MHz)  
- Unified logging pipeline  
- Full healthcheck for Supervisor  
- Modern rootfs layout using s6-overlay  

Originally based on ragingcomputer’s [amridm2mqtt][amridm2mqtt] and the HA add-on by  
[mdegat01][mdegat01], this version has been significantly expanded and modernized.

## Support

Got questions?

You have several ways to get them answered:

- The Home Assistant [Community Forum][forum].
- The Home Assistant [Discord Chat Server][discord-ha] in the **#add-ons** channel.

You can also open an issue on GitHub.

## Authors & contributors

The original setup of this repository is by [Mike Degatano][mdegat01].

The amridm2mqtt service this was built off of was created by  
[ragingcomputer][ragingcomputer].

For a full list of all authors and contributors,  
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2023–2026

Permission is hereby granted, free of charge, to any person obtaining a copy  
of this software and associated documentation files (the "Software"), to deal  
in the Software without restriction, including without limitation the rights  
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
copies of the Software, and to permit persons to whom the Software is  
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all  
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE  
SOFTWARE.

[project-stage-shield]: https://img.shields.io/badge/project%20stage-production%20ready-brightgreen.svg
[amridm2mqtt]: https://github.com/ragingcomputer/amridm2mqtt
[contributors]: https://github.com/mdegat01/addon-amr2mqtt/graphs/contributors
[discord-ha]: https://discord.gg/c5DvZ4e
[forum]: https://community.home-assistant.io/t/home-assistant-add-on-amr2mqtt/378196
[mdegat01]: https://github.com/mdegat01
[ragingcomputer]: https://github.com/ragingcomputer
[license-shield]: https://img.shields.io/github/license/mdegat01/addon-amr2mqtt.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2026.svg
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg
[releases-shield]: https://img.shields.io/github/release/alvinchen1/hassio-addons.svg
[releases]: https://github.com/alvinchen1/hassio-addons/releases
[rtlamr]: https://github.com/bemasher/rtlamr