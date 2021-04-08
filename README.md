# Check Items

Check your group has two containers: PL-2 Raspberry Pi Container & Rapberry Pi Startar Kit.

* PL-2 Raspberry Pi Container contains:
  * Raspberry Pi
  * USB power cable
  * SD card x 2
    * The one inserted in the Rasberry pi is ready to use.
    * The one inserted in the black SD card adapter is not; you can install OS, configure, and use it, if you like. 
  * SD card adapter x 2 (white & black)
  
* Raspberry Pi Starter Kit contains a packing list.

# Preparation

1. Login

Login using ssh.

  * IP address: `192.168.11.10x`  (`x` is group number 1 - 5)
  * User: `pi`
  * Password: `raspberry`
```
$ ssh pi@192.168.11.10x
```

2. Change password

Change password immediately! 
```
$ passwd
```

3. Clone your repository

Clone your git repository using any one of group member's account.

```
$ git clone https://user@github.com/kut-info-ase-2019/raspi-led-g0X.git
```

You would like to write a program on your laptop computer. In this case, you can `git push` your program on your computer and `git pull` on the Raspberry Pi.

**IMPORTANT: You must push your programs, or artifacts, to the repository. Otherwise, staffs cannot evaluate your artifacts.**

# Preliminaries

## GPIO

Raspberry pi has bunch of pins to control peripherals. Some of them are power pins and others are GPIO pins.
For GPIO pins, GPIO numbers (GPIO#2 - #27) are printed on the case.
We can output 3.3V or 0V to a GPIO pin, and sense the level of a GPIO pin by using `Pi.GPIO` Python module.

Pins with 5V, 3.3V and a triangle mark are power pins. A triangle mark means GND. **Do not connect different levels of pins each other.**

## breadboard

We can construct a circuit without soldering on a breadboard. Holes on a breadboard are connected as shown in the following picture:
<img src="BREADBOARD.png">

# Hands-on

In the following, we develop two applications appear in the tutorial of the [Raspberry Pi Startar Kit](http://osoyoo.com/2017/07/13/raspberry-pi-3-starter-learning-kit-introduction). In this cource, we develop an electric circuit by combining electoric devices. **Please be careful not to destroy devices**. 

## Light LED

Read [Raspberry Pi Starter Kit Lesson 4](http://osoyoo.com/2017/06/23/python-light-led/).

### brief instruction

1. Connect the Raspberry Pi to the breadboard.  Use a "T"-shape connector and a flat cable.
2. Construct a circuit on the breadboard (see [connection graph](http://osoyoo.com/wp-content/uploads/2017/06/Untitled-Sketch_bb.jpg))
  * LED only lights for a cirtain polality; When a longer pin (anode) is at a higher level than the other (cathode), it lites. If you connect the anode to a GPIO pin and the cathode to GND though a register, you can light it only when you output 3.3V to the GPIO pin.
  * **Do not forget inserting a register. The registance of LED is virtually zero.**
3. Execute the LED lighting program found at http://osoyoo.com/driver/pi3_start_learning_kit_lesson_4/pythontest.py.

## Temparture and humidity sensor module

Read [Raspberry Pi Starter Kit Lesson 11](http://osoyoo.com/2017/07/06/dht11/).

We use DHT11 sensor module. On DHT11, necessary registers are implemented.  All you have to do is to connect to appropriate pins of  Raspberry pi.

### brief instruction

1. Construct a circuit on the breadboard. (see [connection graph](graph:http://osoyoo.com/wp-content/uploads/2017/07/Untitled-Sketch_bb.png))
2. Execute the Python program found at http://osoyoo.com/driver/pi3_start_learning_kit_lesson_17/dht11.py.

## Your Application

Let's develop a heat index indicator.
Heat index is explained in　https://en.wikipedia.org/wiki/Heat_index) or [wikipedia](https://ja.wikipedia.org/wiki/不快指数) in Japanese

The indicator senses temperature and humidity each second, and light the LED corresponding to the current heat index. For example:

* green: heat index < 75
* yellow: heat index < 80
* red: heat index >= 80

You can use more LEDs to show heat index with a higher resolusion.

### what to do

* Push your heat index indicator program to this repository.
* Prepare for demonstration.
