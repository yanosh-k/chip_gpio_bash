# Info
Bash functions to use GPIO with [C.H.I.P.](https://getchip.com/pages/chip) computer. Based on the work of [jefflarkin](https://gist.github.com/jefflarkin) and [gonzalo](https://gist.github.com/gonzalo).

The original gists can be found here:

[https://gist.github.com/jefflarkin/b2fcec3817ea5d85288f](https://gist.github.com/jefflarkin/b2fcec3817ea5d85288f)

[https://gist.github.com/gonzalo/f7c00f1d40473865f0a3c5954812481c](https://gist.github.com/gonzalo/f7c00f1d40473865f0a3c5954812481c)

# Installation

Clone or download the gpio.sh file:

`git clone https://github.com/yanosh-k/chip_gpio_bash.git`

`wget https://raw.githubusercontent.com/yanosh-k/chip_gpio_bash/master/gpio.sh`

[Source](https://ss64.com/bash/source.html) or execute the file so the function become availabe for the current shell:

`source gpio.sh`

# Usage

### Enabling a pin
Usually all IO pins are disbaled, so first we need to enable them in order to start working with them:

`gpio_enable PIN_NUMBER`

Where PIN_NUMBER is a number between 0 and 7. This number corresponds to the IO pins XIO-P0 to XIO-P7.

![Chip Pinout](https://docs.getchip.com/images/chip_pinouts.jpg)

### Seting pin behaviour
You can set each of the pins to act as IN our OUT. To do so use the followin command:

`gpio_mode PIN_NUMBER in`

or

`gpio_mode PIN_NUMBER out`

### Reading pin value
For pins that are set as *in* you can read the value. The value would be either 0 or 1. **Make sure to connect a [pull-down or a pull-up resistor](http://www.resistorguide.com/pull-up-resistor_pull-down-resistor/) in order to read a correct value from the input.**

`gpio_read PIN_NUMBER`

### Setting pin value
For pins that are set as *out* you set a value. If you want to bring the singal up, set its value to 1, if you want to birng the signal down, set its value to 0.

`gpio_write PIN_NUMBER 1`

or

`gpio_write PIN_NUMBER 0`

### Disabling a pin
After you finish working with the pin you can disable it by calling the function:

`gpio_disable PIN_NUMBER`