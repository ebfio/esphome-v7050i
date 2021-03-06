# esphome-v7050i
ESPHome project to control [v7050i](https://www.benq.com/en-us/projector/laser-tv-projector/v7050i.html) via RS232.

## Requirements
- I personally use a ESP32 for mine, but it should work fine with a ESP8266.
- A RS232 module. I personally use [this one](https://www.amazon.com/gp/product/B00LPK0Z9A/ref=ppx_yo_dt_b_asin_title_o05_s01?ie=UTF8&psc=1).
- A RS232 cable - with the V7050i, a straight cable worked for me. You might need to flip the TX and RX pins on your ESP.
- A v7050i projector. This might work with other models, but I have no way to test it. Proceed at your own risk! ⚠️ 

## Installation

- Hookup the RS232 module to the cable and the ESP. Then use ESPHome to create a new project. 
- Add the `uart_read_line_sensor.h` to your ESPHome configuration directory (since I use docker, I just scp'd; for HASS, you mileage may vary).
- Copy and paste the contents of the projector.yaml file. I use some secrets on that file that you might just hardcode based on what ESPHome created for you.
- Test! It should work.

## Motivation
The v7050i is a great projector, I'm utterly impressed with it. My problem is that it has a major UX flaw: I use it with my Apple TV and its remote; whenever I turn off my Apple TV, it sends one power off command to the projector, as it does with every other TV in existence. The projector however, requires 2 power off signals to turn it off, causing the projector to stay on after my Apple TV is already off. I started by flashing a ESP8266 with an IR blaster and it solved the issue... until I found about that beautiful RS232 port. And here we are :) 

Also, Home Assistant now monitors my Apple TV. Anytime that it's switched off, it turns off the projector. Life is good again. My wife, however, continues to be unimpressed by me adding Wi-Fi powered devices in our bedroom. But I digress...

## Screenshots

Coming soon!

## Credits

Based on the ESPHome custom text component example. 
