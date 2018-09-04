# IDD-Fa18-Lab1: Blink!

**A lab report by Manuel Viejo**

## Part A. Set Up a Breadboard

![Image of breadboard](https://github.com/mviejo33/IDD-Fa18-Lab1/blob/master/IMG_20180903_195714.jpg)


## Part B. Manually Blink a LED

**a. What color stripes are on a 220 Ohm resistor?**

From left to right (tolerance on the right end): Red -> Red -> Black -> Black -> Brown

**b. What do you have to do to light your LED?**

Once the circuit is settled up I only needed to press the button to complete the circle.

## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**

The change the port number in the pinMode function to the appropiate one, in this case it is 13 for the built in LED

**b. What line(s) of code do you need to change to change the rate of blinking?**

By modyfing the delays after setting the voltage to LOW and HIGH we can make the LED blink. For example, I could increment the delay to 4000 ms while the voltage is HIGH and it will decrease the rate of blinking.

**c. What circuit element would you want to add to protect the board and external LED?**

A resistor
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**

About 13 ms, I could record it and slow down the video.

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**

[Link to blink_myway](//github.com/mviejo33/IDD-Fa18-Lab1/blob/master/blink_myway.ino)

### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

**Link to LED blinking:** https://www.youtube.com/watch?v=R7EJZwu4U84



## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**

No, because even if the potentiometer is not exerting any resistance, there´s a 100 Ohm floor caused by the resistor.

## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**

Change the pin number the led is attached to, from 9 to 11.

**b. What is analogWrite()? How is that different than digitalWrite()?**

analogWrite uses pulse width modulation, which is an off on pattern that simulates voltages in between 0 and 5V (for this arduino in particular). digitalWrite sets a constant voltage to a pin.

## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**

Yes, in the integrated circuit (IC) dedicated to keep track of time and the alarm. Once the IC detects a time associated with the alarm, it triggers the beeping sound through an output pin. In addition to that, the IC must handle the arithmeric operations associated with changing the time on a clock, as well as keeping track of the current device mode (Radio, Buzzer or Sound).
 
**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

Yes, there are a bunch of buttons. In particular, there is one for modifying the mode of the device, Once the device mode changes, the IC must be notified through an input pin(s). The IC uses two output pins for lightning one of the three LEDs dedicated to show which mode is currently on.

It also has a Volume Control Wheel Potentiometer, which modifies the resistance in the circuit, permitting the variation in volume.
 
**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

The device is powered by plugging it in the wall, the AC is then transformed to 6VDC with a power supply.


**d. Is information stored in your device? Where? How?**

Yes, the alarm time, current time and mode. This is done by storing variables in the IC, these variables persist after shutdown. These variables are set through button signals and are then transmitted to the corresponding IC´s input pin.

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

I used an alarm clock for this lab, I lighted up a led that denoted the mode that the alarm clock is running on. The breadboard circuit was the same one used for lightining up the LED with a potentioneter. The two LED pins from the alarm clock were connected to ground and to the output of the potentiometer.

### 3. Build your light!

**Frankenlight: Hijacking alarm clock:** https://www.youtube.com/watch?v=Q3RmXtOqmd8


![Image of schematic](https://github.com/mviejo33/IDD-Fa18-Lab1/blob/master/IMG_20180903_212643.jpg)
