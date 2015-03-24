# GPIO Snap for Ubuntu Snappy
GPIO snap for DeviceHive framework and examples. 

### How to Build
```bash
snappy build .
```


### How to use

#### GPIO Blink

This program does blinking of the LED lamps connected to corresponding gpio pins.

```bash
gpio-blink [PIN#] ...
```
Where PIN# is one of pins on the device connected to LEDs. To list all available pins run app without parameters:
```bash
gpio-blink
```

Example:
```bash
gpio-blink.devicehive-gpio PIN9 PIN10 PIN11 PIN12 PIN13 PIN14 PIN15 PIN16
```


#### GPIO Switch

This program turns LED on/off when on a button click.

```bash
gpio-switch BUTTON_PIN LED_PIN
```
Where PIN# is one of pins on the device connected to LEDs. 

Example:
```bash
gpio-blink.devicehive-gpio PIN9 PIN10
```


#### GPIO Click

This program uses 2 buttons to control a set of LEDs. One of the LEDs is turned off and buttons shift turned off led left or right.

```bash
gpio-click
```

> It is important to connect LEDs and buttons to specific pins for this example.

