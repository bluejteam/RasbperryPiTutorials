<h1 align="center"> BlueJ - LED Tutorial</h1>
<h2 align="center"><img src="http://bluej.org/bluej-icon-256.png" height="70"/> LED Tutorial <img src="http://bluej.org/raspberrypi/raspberrypi-B-plus.jpg" height="70"></h>
<p>This tutorial describes how to use BlueJ on the Raspberry Pi to to interact with simple electronics using the Pi's GPIO pins (General-Purpose Input/Output pins). It is not intended to be a complete description of how to use the pins: for that, see the sections called <a href="button.md#UnderTheHood">Under the Hood</a>.</p>
<p>The tutorial is divided into two parts. In the first we'll look at output and lighting an LED, in the second we'll look at input from a button.</p>
<p>If you have not got BlueJ installed in your Raspberry Pi, please install it by following the instructions <a href="http://bluej.org/raspberrypi/index.html#installation">here</a>.</p>

<h2>Section 1: Interacting with a LED</h2>
<p>In this section, we will connect a LED to a Raspberry Pi and turn it on and off by direct object manipulation using BlueJ.  This tutorial will make use of the project <a href="https://github.com/bluejteam/RasbperryPiTutorials/raw/master/projects/LEDButton.zip">LEDButton</a>, which you should  download and open in  BlueJ running on the Raspberry Pi.</p>

<h3>Material</h3>
<p>For this experiment, you will need:</p>
<ul>
<li>1 LED <img src="red_led.jpg" height="120"></li>
<p></p>
<li>1 Resistor (any value between 270Ω to 330Ω) <img src="resistor.JPG" width="120"></li>
<p></p>
<li>2 wires <img src="wires.jpg" width="120"></li>
<p></p>
<li>a breadboard <img src="breadboard.jpg" width="120"> *optional</li>
</ul>

<h3>Assembly</h3>
<h4>Without a breadboard</h4>

<p>An LED is a component that emits light whenever there is a current flowing through it. It will have one long leg and one  shorter one. The short leg (ground terminal) should be connected directly to the black wire and the longer leg should be connected to your resistor. The resistor is used  to limit the current flowing and prevent the LED from burning out.</p>
<p>The other leg of the resistor should be connected to the other wire (the red one), as  in the following picture:</p>
<p align="center">
<a href="led_and_resistor.JPG"><img src="led_and_resistor.JPG" height="200"></a>

<p align="center"><figcaption>Figure 1: connecting the LED to the resistor (click for larger picture).</figcaption></p>
</p>

<p>The Black wire should then be connected to the pin marked 20 (Ground) on your Pi and the red wire should be connected to the pin marked 22 (GPIO6): </p>
<a name="RaspberryPiPins"></a>
<p align="center">
<img src="GPIOs.png" height="400"></p>
<p align="center"> <figcaption>Figure 2: The Raspberry Pi Pins.</figcaption></p>
<p></p>
<p><b>Note:</b> If you have a Raspberry Pi model B+, you will have more than 26 pins. However, the assignment for those pins present on both models (B and B+) will still be the same as described here and the project should work without change.</p></a>
<p>Here is what your  circuit should look like:</p>
<p align="center">
<a href="led_connected_to_raspberrypi.jpg"><img src="led_connected_to_raspberrypi.jpg" height="200"></a></p>
<p align="center"><figcaption>Figure 3: Connection to the Raspberry Pi.</figcaption></p>

<h4>With a breadboard</h4>

If you have a breadboard of any size available, we recommend using it to build the circuit. Don't forget to get the legs of the LED the right way round! 
The circuit is shown in Figure 4, below:
<p align="center">
<a href="LEDBreadBoard.png"><img src="LEDBreadBoard.png" height="200"></a></p>
<p align="center"><figcaption>Figure 4: Using a breadboard (click for larger picture).</figcaption></p>

<h3>Code</h3>
<p>In BlueJ, open the project LEDButton. Your screen should look like this:</p>
<p align="center">
<img src="LEDandButtonOpen.png" height="400"></p>
<p align="center"><figcaption>Figure 5: The LED and Button project open in BlueJ.</figcaption></p>

<p></p>
<p>Each  of the yellow boxes in the BlueJ screen above is a Java class. The LED class represents the real LED connected to the Raspberry Pi.</p>
<p>The LED, Button and ButtonListener classes are already made and you can use them in the following exercises, but do not change them. The Controller class is where you will write your own code. The Button and ButtonListener classes will be described in Part 2 of this tutorial.</p>
<p></p>

<h4>Creating a new LED object</h4>
<p>Before we start to write code, we'll see how the LED class affects the real LED by using BlueJ to control it directly.</p>
<p>To start, right-click on the LED class and from the pop-up menu, choose:</p>
<pre>new LED()</pre>
<p align="center">
<img src="newLED-noParameters.png" width="700"></p>
<p align="center"><figcaption>Figure 6: Creating an instance of LED.</figcaption></p>

<p></p>
<p>BlueJ will ask for the "name of the instance": the suggested name is good for now. You will see a red rectangle on the bottom left of the BlueJ window named "lED1":</p>
<p align="center">
<img src="lED1-created.png" width="700"></p>

<p align="center"><figcaption>Figure 7: An instance of LED on the object bench.</figcaption></p>


<p>This rectangular red icon represents the "lED1" object. This object is the Java representation of the real LED connected to the Raspberry Pi.</p>
<p></p>
<h4>Turning the LED on</h4>
To turn the LED on, right-click on the "lED1" instance and select:
<pre>void on()</pre>
<p align="center">
<img src="lED1-selecting-Method-on.png" width="700"></p>
<p align="center"><figcaption>Figure 8: The pop-up with the list of operations on "lED1".</figcaption></p>
<p></p>

<p>This should turn on the LED. (It might take a moment the first time, as all the behind-the-scenes connections are made).</p>
<p>If you look at Figure 6, you can see that we can also create a LED specifying a gpio number. We didn't need to do that because the default gpio number is the gpio number 6, where we connected our LED.</p>
<p></p>

<p><b>Tip:</b> The LED  Class contains its own documentation showing all the available methods and a brief description of each of them. To see them just double click in the LED class (yellow box) and its documentation (javadoc) will show up: </p>
<p align="center">
<img src="LED-javadoc.png" width="700"></p>
<p align="center"><figcaption>Figure 9: The Javadoc for the LED class.</figcaption></p>

<p></p>
  
<h3>Exercises: </h3>
<ul>
<li><i>Exercise 1.1</i>: You have turned the LED on. Can you turn it off now?
<p></p></li>
<li><i>Exercise 1.2</i>: You can write code in the Controller class to do what you have just done interactively. In the Controller class, change the body of the method "void turnLEDOn()" to call the method which will turn the LED on, and likewise change the method "void turnLEDOff()" in the same class to turn the LED off.
<p>Tips: 
<ul>
<li>To edit the Controller class, double click on the "Controller" yellow box and you will see the source code for the Controller class.</p>
<p></p>
<li> In the Controller class, the LED object is called 'led': it is already there for you!</p></li>
<p></p>
<li> <b>Important:</b> before testing the changes you make to the Controller class, do not forget to compile your project by clicking on "Compile" on the top left of your editor or on the left panel of the BlueJ main screen:</p>
<p align="center">
<img src="Controller-Editing.png" width="600"></p>
<p align="center"><figcaption>Figure 10: Controller class: Click on the <i>Compile</i> button before testing.</figcaption></p>

<p></p></li>
</li>
<p></p>
<li>To test the changes in your Controller class, make an instance of the Controller by right-clicking on the class, just like we did with the LED class, and then  right-clicking on the red Controller instance to call the methods you have just changed. </li>
</ul>
</li><p></p>
<li><i>Exercise 1.3</i>: Change the body of the method "void flash(int time)" in the Controller class to keep the LED on for a given amount of time (measured in milliseconds), then turn the LED off.
<p>Tips:
<ul>
<p></p>
<li>The Controller class has a method called
<pre>sleepMillisec(int time)</pre>
This method can be used in order to make your program wait a given number of milliseconds.</p>
1 millisecond is a very short time.</li>
</li></ul>
<p></p>
<li><i>Exercise 1.4</i>: Change the body of the method "void flashSOS()" in order to make the LED flash the morse code for SOS.
<p>Tip:
<ul>
<li><p>The morse code for SOS is: ". . . - - - . . .", where a dot (.) is a brief flash and a dash (-) is a longer flash</p></li>
<li>
<p>Make use of the flash method implemented in the previous exercise.</li>
</ul>
<li><i>Exercise 1.5</i>: Find out all the patterns Morse Code uses, and write a new method for the Controller class which flashes out any string you give it in Morse Code.</li>
</ul>
<p></p>
<p><a href="button.md">Next tutorial</a></p>
<p><a href="README.md"> Back to the index</a></p>




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

