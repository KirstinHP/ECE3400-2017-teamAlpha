# ECE 3400 2017: Team Alpha

Our team members: Claire Chen, Christopher Fedors, Ryan O'Hern, and Kirstin Petersen

This website describes useful links, solutions to the labs, and our final robot, we hope you will find it useful and create much better websites yourselves!

## Lab 1: Microprocessors

//Goal:// 

The goal of this lab is to get acquainted with the Arduino Uno and to build and control a basic robot. 

//Lab://

First, we installed the Arduino IDE from this link: https://www.arduino.cc/en/Main/Software 

Second, we tested the blink sketch on the Arduino (File->Examples->Basics->Blink):
Code-snippet:

<video>



Third, we modified it to work with an external LED, by adding these lines of code:

```C
pinMode(9, OUTPUT); //Setup pin 9 as output
digitalWrite(ledPin, HIGH); //Turn on LED
digitalWrite(ledPin, LOW); //Turn off LED
```

<video>

Fourth, we communicated over serial interface:

Serial.begin(9600); //Setup serial interface to communicate with 9600 baudrate
Serial.println('Alpha team!'); //Send text 

<Screenshot>

Fifth, we read an analog input from a potentiometer connected to A0, and used it to control the brightness of the LED:

potmeter = analogRead(A0); //Reads an ADC conversion from pin A0 using default settings for the ADC (10 bit conversion).
Serial.println(potmeter);  //Send the potmeter value to the screen
analogWrite(ledPin, potmeter>>2); //The analog write function only takes 8bits, so we have to divide our value by 4

Sixth, we controlled a continuous rotation servo-motor using the library servo.h:

#include <Servo.h>  //Library
Servo myservo;      //Declare instance
myservo.attach(11); //Attach the servo input to pin 11 (set it up as a pwm output, 20Hz)
myservo.write(0);   //0 is full speed reverse, 90 no speed, 180 full speed ahead

<video>

Finally, we assembled our robot and made it drive in a square:

<pic of parts>

<video>

//Helpful links://

* We found the [Arduino website](http://lmgtfy.com/?q=arduino+analog+write Arduino website) to be incredibly helpful.
* Also, this [https://playground.arduino.cc/Main/ShowInfo code] allows you to diagnose your Arduino Uno. Here, you can see how fast a clock cycle really is, how long a conversion takes, etc.

# Lab 2 Signal Processing

Buzzer and IR?

# Lab 3 Wireless Communication








