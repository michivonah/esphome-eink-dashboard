# E-Ink Frame/Dashboard for ESPHome

A simple dashboard with weather data, current playing music & data from Home Assistant for ESPHome.

![Dashboard Example 1](https://github.com/user-attachments/assets/002c1605-2a43-46b6-b78e-b336aa5685a1)
![Dashboard Example 2](https://github.com/user-attachments/assets/d483e0ec-5a82-468d-98d3-7df261c97e6e)

## Required hardware

- [Waveshare 7.5" E-Ink Screen 480x800px](https://amzn.to/4k6oe8k)
- [Waveshare e-Paper ESP32 Driver Board](https://amzn.to/4lW8GWx)
- [IKEA RÖDALM, Black, 13x18cm](https://www.ikea.com/ch/de/p/roedalm-rahmen-schwarz-10548867/)

## Software
- ESPHome
- Home Assistant

## Installation

1. No soldering is required since the e-Paper driver board was integrated into the ESP32 board. All you need to do is to connect the e-Paper screen to the driver board, and then connect the driver board to power via USB.
1. Copy `/fonts` and `e-ink-frame.yaml` to your /.config/esphome folder and adjust it your needs.
1. Flash the configuration to your ESP32 driver board via [ESPHome Web](https://web.esphome.io/)
1. Enjoy!

## Features

## Weather, music & sensor information
The dashboard shows the current outdoor temperature based on a weather service of choice you added to your Home Assistant. The icon next to it shows you the weather state.

In the center of the screen the current playing media of one or more speakers can be displayed.

At the bottom you find some stats of your Home Assistant instance that you can adjust.

## Intelligent Screen Refreshing
To reduce the frequency of screen refreshes and to prolong the life of the e-ink screen, the screen will now only refresh when presence is detected and the lux in the current room is over 5 to avoid refreshing when the display's content can't be read in terms of brightness (like during night).

## Last Refreshed Timestamp
The last update timestamp can be displayed on the screen itself. No more wondering when the screen was last refreshed!

## Remote Control and Monitoring
The screen can now be controlled and monitored remotely. The screen can be either refreshed manually, restarted, or safely shut down through buttons in your HA. The number of screen refreshes in its lifetime as well as its last update timestamp and wifi signal strength can also be monitored.

![List of available sensors and buttons](https://github.com/user-attachments/assets/598bbd02-08ef-4e02-9cb2-ea2aa8206435)
![Refresh Screen Count example](https://github.com/user-attachments/assets/c87b3732-f07f-4b13-8dcf-361881b49c93)

## Easy adjustable
The placing can easly be adjusted via the variables inside of the display block.
```c+++
// General settings
uint multi_info_base_x = 80;
uint text_offset_x = 48;
uint tab_offset_x = 170;
uint multi_info_base_y = music_base_y + 220;
uint text_offset_y = 4;
uint linebreak_offset_y = 60;
```

## References

Here are some other repos that I referenced from:
- [Madelena/esphome-weatherman-dashboard - GitHub](https://github.com/Madelena/esphome-weatherman-dashboard)
- [DeastinY/esphome-waveshare-e-paper-dashboard - GitHub](https://github.com/DeastinY/esphome-waveshare-e-paper-dashboard)
- [savikko/smarthome - GitHub](https://github.com/savikko/smarthome)
