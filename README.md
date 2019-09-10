# IDD-Fa19-Lab1: Blink!

**A lab report by Bar Kadosh**

## Part A. Set Up a Breadboard

To initially set up my breadboard, I connected the +5V pin of the Arduino to the red rail (on the same side of the breadboard that the pin is on) and the GND pin of the Arduino to the blue rail (on the same side of the breadboard that the pin is on). While not necessary, I also connected the opposite red rail to the initial red rail and the opposite blue rail to the initial blue rail.

<img src="https://github.com/barkadosh1/IDD-Fa18-Lab1/blob/master/IMG_9386.jpeg" width="800" height="700">

## Part B. Manually Blink a LED

**a. What color stripes are on a 220 Ohm resistor and a 100 ohm resistor?**

On our 220 Ohm resistor, the colors, in order, are: red, red, black, black, brown. Using a resistor color coding chart, this translates to the following: the first digit is 2 (red), the second digit is 2 (red), the third digit is 0 (black), the multiplier is 10<sup>0</sup> Ohms (black), and the tolerance is +/- 1% (brown).

Using the same color code/color convention, we can predict what the color stripes on a 100 ohm resistor would be: brown, black, black, black. Brown represents the first digit (1), the first black represents the second digit (0), the second black represents the third digit (0), and the last black represents a multiplier of 1 Ohm. Since the 5th color represents the tolerance, I will not attempt to predict what it may be, as such a value is arbitrary.
 
**b. What do you have to do to light your LED?**

After constructing the circuit described in the schematic, the LED still does not light up initially. In order to allow it to light up, I must press the button -- when pressed, the LED lights up. When the button is not pressed, there is essentially a break in the circuit and the LED can not light up.

## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**

To begin, we are given the Blink code example. Within this code, nothing has to be changed in order to make the LED blink. In the void setup() section, the line "pinMode(LED_BUILTIN, OUTPUT)" already establishes that pin 13 (LED_BUILTIN) is an output. In the void loop() section (which runs a continuous loop), the example code already contains the line "digitalWrite(LED_BUILTIN, HIGH)" to turn the LED on, the line "delay(1000)" to keep the LED on for 1 second, the line "digitalWrite(LED_BUILTIN, LOW)" to turn the LED off, and another "delay(1000)" line to keep the LED off for another second before repeating the loop. Therefore, all of the code needed to make the LED blink is already provided in the example code. 

**b. What line(s) of code do you need to change to change the rate of blinking?**

In order to change the rate of blinking, the line "delay(1000)" after the LED is turned off must be changed. This will change how long the loop will be delayed before repeating -- in order words, this will delay how long the loop will wait before turning the LED on. If the value 1000 is increased, the rate of blinking will be slower; if the value is decreased, the rate of blinking will be faster. 

The other "delay(1000)" line between turning the LED on and off controls how long the actual light stays on, not how much time occurs in between blinking. 

**c. What circuit element would you want to add to protect the board and external LED?**

We would like to add a resistor to protect our board and external LED. Given Ohm's law, V = IR, we can see that for a given voltage, having a low resistance will lead to a very high current. Therefore, we should add a resistor to lower the current flowing to the LED, otherwise the LED might break. Additionally, we can add a fuse to take the initial hit and prevent the LED from being impacted in the event that something goes wrong.
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**

Starting at a delay of 15 ms, I began lowering the delay by 1 ms and observing. At 10 ms, the LED appeared to be a continuous light (no blinking). However, I was still able to notice slight vibrations. At a delay of 9 ms, the light was truly constant (no vibrations and no blinking). In order to prove that it was in fact still blinking, I recorded 2 videos at an even lower delay of 5 ms: one at normal speed and one in slow motion and pasted them below. As the slow motion video shows, the blinking is in fact still occuring -- our eyes just aren't capable of seeing it. 

[Normal Speed - Bar Kadosh](https://youtu.be/1IWH4m2lmdI)

[Slow Motion - Bar Kadosh](https://youtu.be/ApmYkxbyZ-I)

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**

For modifying my code, I did a fun example where I made the lights blink with the song "Eye of the Tiger." The code and a video are below.

[Eye of the Tiger Blinking Code - Bar Kadosh](https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/sketch_eye_of_tiger.ino)

[Eye of the Tiger Blinking Video - Bar Kadosh](https://youtu.be/WHScfbW2Z6Q)


### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

[Blinking Pin 9 - Bar Kadosh](https://youtu.be/Xn55NqshU2c)

## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**

As is seen in the video, I am ALMOST able to get the LED to glow the whole turning range of the potentiometer. While the LED gets very bright on one end of the potentiometer, the LED does not fully turn off on the other end of the potentiometer. I imagine that this end of the potentiometer does not provide a resistance high enough that is capable of blocking enough current from reaching the LED, which is why the LED does not fully dim.

[Potentiometer - Bar Kadosh](https://youtu.be/ckfLt4m3FOc)

## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**

Only two things need to be modified. The output pin on the board must be changed so that the wire connects to pin 11. In the code, the value of "led" must be updated to a value of 11 so that the output pin is set to 11. A video of the fade is below.

In order to actually change the way it fades, there is a variable "fadeAmount" in the code. Increasing the value of this variable will cause the LED to fade and unfade faster.

[Fade - Bar Kadosh](https://youtu.be/1BE0TMpyLh8)

**b. What is analogWrite()? How is that different than digitalWrite()?**

AnalogWrite() is a method that can be used with a PWM output pin. Since we assign values between 0-255, we can control the percentage of the time that the output is HIGH or LOW (255 meaning always on, 0 meaning always off, and values in between adjusting proportionally). This is different from digitalWrite(), which only allows for two states: HIGH (5 V in our case) or LOW (off in our case). 

## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 

My device is a charger for a portable playstation. The original charger, the schematic, and the inside of the charger are shown below.

<img src="https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/IMG_9392.jpeg" width="400" height="300"> <img src="https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/IMG_9417.jpeg" width="400" height="300">

<img src="https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/IMG_9418.jpeg" width="800" height="800">

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**

For my device, it does not appear as if there is any computation. I looked up documentation for all of the integrated circuits and none of them suggest computation. The other remaining parts can visually be determined to not be "computers."

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

For the most part, no sensors are visually present in the PCB. However, when looking up documentation for one of the integrated circuits, I noticed that it is an optocoupler. Upon further reading, I discovered that one of the parts within the optocoupler is a photosensitive device which detects light from the other part in the optocoupler, an LED. It does this by converting the light energy (visible, infrared, etc.) into an electrical signal. Since these devices are contained within the integrated circuit, it is not clear if this electrical signal is conveyed to other portions of the device.

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

The system is powered through a 110 Volt AC outlet. Within the PCB, there is transformation and regulation. On my PCB, transformers help take the 110 AC Voltage and lower it to a more reasonable voltage. My board then also appears to have a switching regulator, which transforms the power supply into a pulsed voltage. Capacitors and inductors are then used to smooth the voltage out (and potentially a filter, though I definitively see capacitors and inductors). For this system, 110 V is present until going through the transistors, capacitors, switching regulator, etc., and past that point, 5 V is present in the system. Both values were confirmed with a voltmeter.  

**d. Is information stored in your device? Where? How?**

It does not appear as if any information is being stored in the device. Since this device is a charger, I would guess that this makes sense, as there doesn't seem to be a need for a charger to store information. 

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

After understanding my board and drawing out the schematic, I confirmed with a voltmeter 2 points on the PCB where a 5V difference existed. This occurs after the 110 AC Voltage goes through a series of transformers, rectifiers, filters, switching regulators, capacitors, etc. By this point, a 5V difference exists between 2 given points in the circuit. I soldered a wire coming out of one of those points and connected it to my breadboard. I then connected that wire to the LED and connected the LED to a resistor (in the breadboard). Finally I connected a wire from the resistor and soldered the other end back onto the second point of the PCB, closing the loop. By doing this, I hacked the electric source of my device and inserted the LED/resistor combo within the circuit to reroute the current and light up the LED.

<img src="https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/IMG_9399-1.jpeg" width="800" height="700">

### 3. Build your light!

**Make a video showing off your Frankenlight.**

As is seen in the video, once I insert the plug of my device into an electrical out, the LED lights up.

[Frankenlight - Bar Kadosh](https://youtu.be/AJwrvC-jkeQ)
