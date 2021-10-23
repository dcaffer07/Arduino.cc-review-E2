# Aurduino.cc-review-E2 (NotSoBasicAurduino)
## Table of Contents

##### [LED Blink W/ Button](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#led-blink-w-button---aurduino-review-assignment) 
#### [LED Fade](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#led-fade-wo-button)
#### [Potentiometers](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#potentiometers-1) 
#### [Photoresistor](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#photoresistor-1) 

## LED Blink w/ Button - Aurduino review assignment
#### Description:
> Get the LED to blink when you push the button and have a counter print numbers up to 10 for each blink (will blink 10 times).
#### Goal
> Get the LED to blink when you push the button and have a counter print numbers up to 10 for each blink (will blink 10 times).  Additionally, we simple just want to refamiliarize ourselves with code and aurduino for future assignments.
#### Wriring 
> Very straight forward, simply connect an LED to the groundand a pin for power supply ad direction, and than add resisters to ensure proper use of electricity, and button to begin the loop...
<img src="https://user-images.githubusercontent.com/71406831/133668640-a781d8e3-5f1d-4e4d-ab7f-e9eb001982fe.png" alt="wiring2" style="width:500px;">

#### Code

```C++
 
int ledPin = 2;
int buttonPin = 13;
int buttonState = LOW;
int counter = 1;

void setup() {
  Serial.begin(9600);
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);

}



void loop() {
  buttonState = digitalRead(buttonPin);
  Serial.print(buttonState);
  Serial.print("\t");
  if (buttonState == HIGH) {

    if (counter > 0 && counter < 11) {
      counter = counter + 1;
      Serial.println(counter);
      digitalWrite(2, HIGH);
      delay(250);
      digitalWrite(2, LOW);
      delay(250);
    }
    else if (counter == 10) {
      Serial.println("Done!");
      digitalWrite(buttonState, LOW);
    }
    else {
      
      digitalWrite(ledPin, LOW);
      Serial.println("Off!");
     
    }
  }
}
```
#### Reflection:
> Easy. simple, but was great to get back into it!!!!!!!!!!!!!!!!!
## LED Fade w/o Button

#### Description:

> Make an LED fade in and out.
#### Goal:

> The goal and prurpose of this assignment was to eintroduce and familiarize ourselves to aurdunos and their code again.  In this assigment we were tasked with making an LED fade in and out, rather than blink without a button, or really any other restrictions such as speed or amopunt of times.  The primary differnece in accomplishing this in thge code compared to having an LED blink was using the anaolgWrite(); function rather than the digitalWrite(); function.  Asside from that they used many of the same things such as connecfting and establishing ppins, serial.print.ln, ect.
#### Wiriring

> Ver6y straight forward, simply connect an LED to the groundand a pin for power supply ad direction, and than add resisterns to ensure proper use of electricity...
<img src="https://user-images.githubusercontent.com/71406831/133321835-78fca232-3509-4fd2-81b5-626428592a99.png" alt="wiring"  style="width:500px;">

#### Code

```C++
  /*

int led = 9;           // the pin that the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(led, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // set the brightness of pin 9:
  analogWrite(led, brightness);

  // change the brightness for next time through the loop:
  brightness = brightness + fadeAmount;

  // reverse the direction of the fading at the ends of the fade:
  if (brightness == 0 || brightness == 255) {
    fadeAmount = -fadeAmount ;
  }
  // wait for 30 milliseconds to see the dimming effect
  delay(30);
}
```

And here it is in all its glory

<img src="https://github.com/dcaffer07/LED-review-E2/blob/main/Media/fade.gif?raw=true" alt="wiring"  style="width:500px;">

#### Reflection:
> All in all I think that this assigmant was extermely effective in refreshing our memory of code and getting back into the swing of things.  I enjoyed geting to begin with things that I was comfortable with and than gradually introducing harder and less familiar material such as the analogWrite()function.  It was great to get back into the swiung of things and I look forward to creatinmg more code in the future.


## Potentiometers

#### Description:
> Wire up a breadboard potentiometer to control the brightness of an LED
#### Goal:
>The goal here was to familiarize ourselves with a potentoiometer and how it operates.  We wewre also able to expand our knoowledge of code and its varuiouse functions by making something become brighter accordingly, without a deffinete sate or repeating loop.


#### Wiring
> In this wiring, all was famikliar in terms of hooking think up to 5v, ground, and the variiouse pins using wires and risiters, howver what was new in this wiring was connecting the middle connection wire of the potentiometer to A0, which simply gave the potentiometer itrs relevemnce by determinig brightness with the LED.
<img src="https://user-images.githubusercontent.com/71406831/134237138-7d672a4f-f634-42a7-8e5b-8e36e8f16fc3.png" alt="wiring"  style="width:500px;">

#### Code

```C++


int LED_PIN = 3;  // LED is attached to

// the setup routine runs once when you press reset:
void setup() {

  Serial.begin(9600);

  pinMode(LED_PIN, OUTPUT);
}

// the loop routine runs over and over again forever:
void loop() {
  // reads the input on analog pin A0 (value between 0 and 1023)
  int analogValue = analogRead(A0);

  // scales brightness
  int brightness = map(analogValue, 0, 1023, 0, 255);

  // sets the brightness LED that connects to  pin 3
  analogWrite(LED_PIN, brightness);

  // print out the value
  Serial.print("Analog: ");
  Serial.print(analogValue);
  Serial.print(", Brightness: ");
  Serial.println(brightness);
  delay(100);
}
```

#### [*Evidence (or the device in all its glory via tinker cad (was absent the day we did this so it was suggested that I do this Digitally!!*))](https://www.tinkercad.com/things/iL3KHLuNY8Q-fantabulous-jaiks/editel)

<img src="https://hackster.imgix.net/uploads/attachments/1144713/led_light_ll76wHKBOA.gif?auto=compress&gifq=35&w=680&h=510&fit=max" alt="wiring"  style="width:500px;">

[Image credit goes to Wieselly](https://hackster.imgix.net/uploads/attachments/1144713/led_light_ll76wHKBOA.gif?auto=compress&gifq=35&w=680&h=510&fit=max)

#### Reflection
> This assigjment was interesting because we were able to incorperate new coding and wiring methods.  Thcan ofcourse be challenging however it was proballby my favorite assignment so far.

## Photoresistor

#### Description:
> Your task is to develop a night light that automatically comes on when it gets dark.  Or in other words, when you cut of the photresistors light source, an LED should turn on.

#### Goal:
> To incorporate new, and more complex functions into our coding knowledge to further our overall knowledge and understanding of how things opporate.  Also because it's gonna be fun!!!!

#### Wiring

> Give LED power and pin, give PHOTORESISTOR power and pin, make it happen so that when light is taken away, power is supplyed to the LED.  This wiring was not too complicated or diferent at all, and I would say that the wiring for some of the previouse assignments was harder, because really all this was was hooking u an LED and making it corrospond to a button which we have done numerouse times, only now rather than a button we are using a photoresistor...
<img src="https://user-images.githubusercontent.com/71406831/135154892-4c6eeadd-1860-45de-8185-c711fea61efe.png" alt="wiring"  style="width:500px;">

#### Code
> We used the analog pin A0 and the command analogRead() to read the value of the photoresistor which was the overall basis and "spicy part of the assignment".

```C++

int light = 0; // store the current light value

void setup() {
    // put your setup code here, to run once:
    Serial.begin(9600); //configure serial to talk to computer
    pinMode(8, OUTPUT); // configure digital pin 13 as an output
}

void loop() {
    // put your main code here, to run repeatedly:
    light = analogRead(A0); // read and save value from PR
    
    Serial.println(light); // print current light value
 
    if(light > 450) { // If it is bright...
        Serial.println("It is quite light!");
        digitalWrite(8,LOW); //turn left LED off
    }
    else { // If it's dark...
        Serial.println("It is pretty dark!");
        digitalWrite(8,HIGH); // Turn left LED on
    }
    delay(1000); // don't spam the computer!
}

```

#### Evidence (The Photoresistor in all its glory!)
<img src="https://github.com/dcaffer07/LED-review-E2/blob/main/Media/Phgotoresitor%20gif.gif?raw=true" alt="wiring"  style="width:500px;">

#### Reflection
> All in all I really enjoyed this assignemnt, I think it did a good job incorporating some of the things that we did in the past with neer things making for a fun and cool experience.  This was by far my favoritre assignemnt so far and I look forwar to more like it in the future!

[Back to Top](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#led-blink-w-button---aurduino-review-assignment)
