<meta http-equiv="Content-Type" content="text/html;charset=utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- Bootstrap -->
<link href="../bootstrap/css/bootstrap.min.css" rel="stylesheet" media="screen">

<link href="../bluej.css" rel="stylesheet"/>
<link href='http://fonts.googleapis.com/css?family=Arbutus+Slab' rel='stylesheet' type='text/css'>

</head>
<body>
<div class="bluej_main container">

<div class="text-center row">

# <img src="http://bluej.org/bluej-icon-256.png" height="75" align="top"> BlueJ on the Raspberry Pi! <img src="http://bluej.org/raspberrypi/raspberrypi-B-plus.jpg" height="75">

[BlueJ](http://bluej.org/) BlueJ is an Integrated Development Environment (IDE) written in Java, designed for the teaching of java for beginners.

From version 3.14, BlueJ fully supports the [Raspberry Pi](http://www.raspberrypi.org) models A, A+, B and B+. From version 3.15, BlueJ added support for the Raspberry Pi 2. The Raspberry Pi is a credit card sized single board computer aimed at promoting the teaching of basic computer programming in schools. BlueJ is a Java development environment that allows development as well as program execution on the Pi.

BlueJ provides full access to hardware attached to the Raspberry Pi via the open source [Pi4J](http://www.pi4j.com) library, from the the familiar Java SE language, including the new Java 8. 

## Tutorials

* [LED tutorial](led.md)
* [Button tutorial](button.md)
* [Adjustable LED tutorial](PWMLed.md)
* [Controlling a servo motor](ServoMotor.md)

As basis for your own projects, all of the above I/O helper classes, plus helper classes to use analog inputs: using the MCP3008, and another one using a just a capacitor (described [here](http://www.raspberrypi-spy.co.uk/2012/08/reading-analogue-sensors-with-one-gpio-pin/)) are avaliable in [a single BlueJ project for download](https://github.com/downloads/bluejteam/RaspberryPiTutorials/projects/AllComponents.zip).

###Note:

All of the normal BlueJ functionality also works on the Raspberry Pi, however, although BlueJ runs as a regular user, your code runs as root (to support access to the hardware). In normal use, you will not notice the difference, but if you write code which e.g. delete system files, then you can cause system problems on the Pi.

<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="http://code.jquery.com/jquery.js"></script>
<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="bootstrap/js/bootstrap.min.js"></script>
<script type="text/javascript">
$(window).load(function(){
$('.carousel').carousel({interval: 8000});
});
</script>
<script src="http://www.google-analytics.com/urchin.js" type="text/javascript">
</script>
<script type="text/javascript">
_uacct = "UA-301920-1";
urchinTracker();
</script>
