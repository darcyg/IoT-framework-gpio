# GPIO Snap for Ubuntu Snappy
GPIO snap for DeviceHive framework and examples. 

### How to Build
```bash
snappy build src
```


### Usage Examples

#### GPIO Blink

This program does blinking of the LED lamps connected to corresponding gpio pins.

```bash
devicehive-gpio.gpio-blink [PIN#] ...
```
Where PIN# is one of pins on the device connected to LEDs. To list all available pins run app without parameters:
```bash
devicehive-gpio.gpio-blink
```

Example:
```bash
devicehive-gpio.gpio-blink PIN9 PIN10 PIN11 PIN12 PIN13 PIN14 PIN15 PIN16
```


#### GPIO Switch

This program turns LED on/off when on a button click.

```bash
devicehive-gpio.gpio-switch BUTTON_PIN LED_PIN
```
Where PIN# is one of pins on the device connected to LEDs. To list all available pins run app without parameters:
```bash
devicehive-gpio.gpio-blink
```

Example:
```bash
devicehive-gpio.gpio-blink PIN9 PIN10
```


#### GPIO Click

This program uses 2 buttons to control a set of LEDs. One of the LEDs is turned off and buttons shift turned off led left or right.

```bash
devicehive-gpio.gpio-click
```

> It is important to connect LEDs and buttons to specific pins for this example. For BBB use 
> Buttons: GPIO_66, GPIO_67
> LEDS: GPIO_69, GPIO_68, GPIO_45, GPIO_44, GPIO_23, GPIO_26, GPIO_47, GPIO_46

## Device Profiles

As GPIO pinout is different on every device/board and there is no way to enumerate available pins programatically. So gpio daemon uses pin mapping for each device. Mappings are located in `/src/etc/gpio.yaml` file.  Each profile is mapped to the name returned by `/sys/firmware/devicetree/base/model` on the current system.

