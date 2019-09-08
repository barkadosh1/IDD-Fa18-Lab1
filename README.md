# IDD-Fa19-Lab1: Blink!

**A lab report by Bar Kadosh*

## Part A. Set Up a Breadboard

To initially set up my breadboard, I connected the +5V pin of the Arduino to the red rail (on the same side of the breadboard that the pin is on) and the GND pin of the Arduino to the blue rail (on the same side of the breadboard that the pin is on). While not necessary, I also connected the opposite red rail to the initial red rail and the opposite blue rail to the initial blue rail.

<img src="https://github.com/barkadosh1/IDD-Fa18-Lab1/blob/master/IMG_9386.jpeg" width="600" height="500">

## Part B. Manually Blink a LED

**a. What color stripes are on a 220 Ohm resistor?**
On our 220 Ohm resistor, the colors, in order, are: red, red, black, black, brown. Using a resistor color coding chart, this translates to the follow: the first digit is 2 (red), the second digit is 2 (red), the third digit is 0 (black), the multiplier 10<sup>0</sup> Ohms (black), and the tolerance is +/- 1% (brown).
 
**b. What do you have to do to light your LED?**
After constructing the circuit described in the schematic, our LED initially still does not light up. In order to allow it to light up, I must press the button -- when pressed, the LED lights up. When the button is not pressed, there is essentially a break in the circuit, and therefore, the LED can not light up.

## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**
To begin, we are given the Blink code example. Within this code, nothing has to be changed in order to make the LED blink. In the void setup() section, the line "pinMode(LED_BUILTIN, OUTPUT)" already establishes that pin 13 (LED_BUILTIN) is an output. In the void loop() section (which runs a continuous loop), the example code already contains the line "digitalWrite(LED_BUILTIN, HIGH)" to turn the LED on, the line "delay(1000)" to keep the LED on for 1 second, the line "digitalWrite(LED_BUILTIN, LOW)" to turn the LED off, and another "delay(1000)" line to keep the LED off for another second before repeating the loop. Therefore, all of the code needed to make the LED blink is already provided in the example code. 

**b. What line(s) of code do you need to change to change the rate of blinking?**
In order to change the rate of blinking, the line "delay(1000)" after the LED is turned off must be changed. This will change how long the loop will be delayed before repeating -- in order words, this will delay how long the loop will wait before turning the LED on. If the value 1000 is increased, the rate of blinking will be slower; if the value is decreased, the rate of blinking will be faster. 

The other line "delay(1000" in between turning the LED on and off controls how long the actual light stays on, not how much time occurs in between blinking. 

**c. What circuit element would you want to add to protect the board and external LED?**
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**
For modifying my code, I did a fun example where I made the lights blink with the song "Eye of the Tiger." The code and a video are below.

[Eye of the Tiger Blinking Code - Bar Kadosh](https://github.com/barkadosh1/IDD-Fa19-Lab1/blob/master/sketch_eye_of_tiger.ino)

[Eye of the Tiger Blinking Video - Bar Kadosh](https://youtu.be/WHScfbW2Z6Q)


### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**
[Blinking Pin 9 - Bar Kadosh](https://youtu.be/Xn55NqshU2c)

## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**
As is seen in the video, I am ALMOST able to get the LED to glow the whole turning range of the potentiometer. While the LED gets very bright on one end of the potentiometer, the LED does not fully turn off on the other end of the potentiometer. I imagine that this end of the potentiometer does not provide such a high resistance that is capable of completely blocking the flow of current, and therefore does not dim the LED fully.
[Potentiometer - Bar Kadosh](https://youtu.be/ckfLt4m3FOc)

## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**
Only two things need to be modified. The output pin on the board must be changed so that the wire connects to pin 11. In the code, the value of "led" must be updated to a value of 11 so that the output pin is set to 11. A video of the fade is below.

In order to actually change the way it fades, there is a variable "fadeAmount" in the code. Increasing the value of this variable will cause the LED to fade and unfade faster.

[Fade - Bar Kadosh](https://youtu.be/1BE0TMpyLh8)

**b. What is analogWrite()? How is that different than digitalWrite()?**


## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

**d. Is information stored in your device? Where? How?**

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

**Describe what you did here.**

### 3. Build your light!

**Make a video showing off your Frankenlight.**

**Include any schematics or photos in your lab write-up.**
