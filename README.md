# <img src="http://bluej.org/bluej-icon-256.png" height="70" > BlueJ on the Raspberry Pi! <img src="http://bluej.org/raspberrypi/raspberrypi-B-plus.jpg" height="70">

[BlueJ](http://bluej.org/) BlueJ is an Integrated Development Environment (IDE) written in Java, designed for the teaching of java for beginners.

From version 3.14, BlueJ fully supports the [Raspberry Pi](http://www.raspberrypi.org) models A, A+, B and B+. From version 3.15, BlueJ added support for the Raspberry Pi 2. The Raspberry Pi is a credit card sized single board computer aimed at promoting the teaching of basic computer programming in schools. BlueJ is a Java development environment that allows development as well as program execution on the Pi.

BlueJ provides full access to hardware attached to the Raspberry Pi via the open source [Pi4J](http://www.pi4j.com) library, from the the familiar Java SE language, including the new Java 8. 

## Tutorials

* [LED tutorial](http://bluej.org/raspberrypi/led.html)
* [Button tutorial](http://bluej.org/raspberrypi/button.html)
* [Adjustable LED tutorial](http://bluej.org/raspberrypi/PWMLed.html)
* [Controlling a servo motor](http://bluej.org/raspberrypi/ServoMotor.html)

As basis for your own projects, all of the above I/O helper classes, plus helper classes to use analog inputs: using the MCP3008, and another one using a just a capacitor (described [here](http://www.raspberrypi-spy.co.uk/2012/08/reading-analogue-sensors-with-one-gpio-pin/)) are avaliable in [a single BlueJ project for download](http://bluej.org/raspberrypi/projects/AllComponents.zip).

###Note:

All of the normal BlueJ functionality also works on the Raspberry Pi, however, although BlueJ runs as a regular user, your code runs as root (to support access to the hardware). In normal use, you will not notice the difference, but if you write code which e.g. delete system files, then you can cause system problems on the Pi.
