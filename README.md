# Arduino.cc-review-E2 (NotSoBasicArduino)
## Table of Contents

##### [LED Blink W/ Button](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#led-blink-w-button---aurduino-review-assignment) 
#### [LED Fade](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#led-fade-wo-button)
#### [Potentiometers](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#potentiometers-1) 
#### [Photoresistor](https://github.com/dcaffer07/LED-review-E2/blob/main/README.md#photoresistor-1) 

## LED Blink w/ Button - Arduino review assignment
#### Description:
> Get the LED to blink when you push the button and have a counter print numbers up to 10 for each blink (will blink 10 times).  Additionally, we simply just want to refamiliarize ourselves with code and arduino for future assignments.
#### Wriring 
> Very straight forward, simply connect an LED to the ground and a pin for power supply and direction and then add resistors to ensure proper use of electricity, and a button to begin the loop or function...
<img src="https://user-images.githubusercontent.com/71406831/133668640-a781d8e3-5f1d-4e4d-ab7f-e9eb001982fe.png" alt="wiring2" style="width:500px;">

Image credit goes to [The Robotics Back-End](https://roboticsbackend.com/arduino-turn-led-on-and-off-with-button/)

#### Code

```C++
 
int ledPin = 2; // Just settin up pins and laying foundation for work to come
int buttonPin = 13; // ^
int buttonState = LOW; // Saying the defualt button state is low
int counter = 1;

void setup() {
  Serial.begin(9600);
  pinMode(ledPin, OUTPUT); //  Conecting things to initialize.  Setting up inputs/outputs.  When this occurs.... this will occur
  pinMode(buttonPin, INPUT);

}



void loop() {
  buttonState = digitalRead(buttonPin); // Saying to read button... if pressed or high... light will turn on... if not... defualt stae of off.
  Serial.print(buttonState);
  Serial.print("\t");
  if (buttonState == HIGH) {

    if (counter > 0 && counter < 11) {
      counter = counter + 1;
      Serial.println(counter); // what will print as the program operates.
      digitalWrite(2, HIGH); // just the prcess of what will happen when button is pressed.
      delay(250);
      digitalWrite(2, LOW);
      delay(250);
    }
    else if (counter == 10) {
      Serial.println("Done!"); // if button on... print stuff but if not, serial print DONE.
      digitalWrite(buttonState, LOW);
    }
    else {
      
      digitalWrite(ledPin, LOW);
      Serial.println("Off!"); // off
     
    }
  }
}
```
#### Reflection:
> Easy. simple, but was great to get back into it!!!!!!!!!!!!!!!!!
> 
## LED Fade w/o Button

#### Description:
> The goal and purpose of this assignment was to reintroduce and refamiliarize ourselves to ardunios and code.  In this assigment we were tasked with making an LED fade in and out, rather than blink without a button, or really any other restrictions such as speed or amount of times.  The primary difference in accomplishing this in the code compared to having an LED blink was using the anaolgWrite(); function rather than the digitalWrite(); function.  Aside from that we will be using many of the same things such as connecting and establishing pins, serial.print.ln, ect.
#### Wiriring

> Very straight forward, simply connect an LED to the ground and a pin for power supply and direction, and than add resistors to ensure proper use of electricity...
<img src="https://raw.githubusercontent.com/zsiller38/Engineering2-Arduino/main/images/ArduinoPhade.png" alt="wiring"  style="width:500px;">

Image credit goes to [Zach S. (BIG ZACH)](https://github.com/zsiller38/Engineering2-Arduino)

#### Code

```C++

int led = 9; // setting up pins
int brightness = 0;
int fadeAmount = 5; // fade amount, or establishing how much brightness or light will be presnts depending.

void setup() {
  pinMode(led, OUTPUT); // LED is output so what will be changed.
}


void loop() { // fad and keep due to loop, don't stop.

  analogWrite(led, brightness); // allows for this to work 
  brightness = brightness + fadeAmount; // brigtness will be however much impact or relevnce fade has.

  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount; // simply setting brightness bounds for LED
  }
  delay(30);
}

```
Code credit goes to [Zach S.](https://github.com/zsiller38/Engineering2-Arduino) I did my code on the device at school not on arduino.cc, and so when submitting this at home on my chromebook I don't have the code :(.  Put all in arduino.cc! (Comments applied were own)

And here it is in all its glory (evidence)

<img src="https://github.com/dcaffer07/LED-review-E2/blob/main/Media/fade.gif?raw=true" alt="wiring"  style="width:500px;">

#### Reflection:
> All in all I think that this assigmant was extermely effective in refreshing our memory of code and getting back into the swing of things. However some takeaways...
> - AnalogWrite(); gives fading effect so that ther is not one set value for a brightness but instead there is continuose unconditional change.
> - Make sure that pins are directed to the correct area, and use side sections on breadboard to connect graound and 5v rather than tryong to directly connect.
> - When using other wiring make sure to give credit.  It can be easy to forget but have to be carefull about it. image --> cred goes to xxx
>
> Overall the assignment did not introduce too many new factors however these are important things to keep in mind.

## Potentiometers

#### Description:
> Wire up a breadboard and potentiometer to control the brightness of an LED. The goal here was to familiarize ourselves with a potentoiometer and how it operates.  We were also able to expand our knoowledge of code and its variouse functions by making something become brighter accordingly, without a deffinate state or a repeating loop.


#### Wiring
> In this wiring, all was familiar in terms of hooking things up to 5v, ground, and the variouse pins using wires and resitors, however what was new in this wiring was connecting the middle connection wire of the potentiometer to A0, which simply gave the potentiometer its relevence by determining brightness with the LED.
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
  // reads the input on analog pin A0 (value between 0 and 1023) or we can think of it as a energy or brightness level
  int analogValue = analogRead(A0);

  // scales brightness or gives it variation as potentiometer turned.
  int brightness = map(analogValue, 0, 1023, 0, 255);

  // sets the brightness LED that connects to pin 3
  analogWrite(LED_PIN, brightness);

  // print out the value
  Serial.print("Analog: "); // when runs print amount of energy depending on value. 
  Serial.print(analogValue);
  Serial.print(", Brightness: ");  // output ior what is being determined through all of this is brightness.
  Serial.println(brightness);
  delay(100);
}
```

#### [*Evidence (or the device in all its glory via tinker cad (was absent the day we did this so it was suggested that I do this Digitally!!*))](https://www.tinkercad.com/things/iL3KHLuNY8Q-fantabulous-jaiks/editel)

<img src="https://hackster.imgix.net/uploads/attachments/1144713/led_light_ll76wHKBOA.gif?auto=compress&gifq=35&w=680&h=510&fit=max" alt="wiring"  style="width:500px;">

[Image credit goes to Wieselly](https://hackster.imgix.net/uploads/attachments/1144713/led_light_ll76wHKBOA.gif?auto=compress&gifq=35&w=680&h=510&fit=max)

#### Reflection
> This assignment was interesting because we were able to incorperate new coding and wiring methods.  That of course can be challenging however it was proballby my favorite assignment so far. some takeways...
> - Potentiometer- potential energy, if A0 (analog read) interperites greater umph via turn of potentiometer and vice versa.
> - When printing things make sure to be soecific about what is being printed in terms of lik "" for simplicity and effectiveness.
> - When writing... do not overthink, i initially overthought this howver after having been walked through it its not complicated so don't make it complicated.
>
> Really cool assigment and look forward to ore like it

## Photoresistor

#### Description:
> The task is to develop a night light that automatically comes on when it gets dark.  Or in other words, when you cut of the photoresistors light source, an LED should turn on. Here we want to incorporate new, and more complex functions into our coding knowledge to further our overall knowledge and understanding of how things opporate.  Also because it's gonna be fun!!!!

#### Wiring

> Give LED power and pin, give PHOTORESISTOR power and pin, make it happen so that when light is taken away, power is supplyed to the LED.  This wiring was not too complicated or different at all, and I would say that the wiring for some of the previouse assignments was harder, because really all this was was hooking up an LED and making it correspond to a button which we have done numerouse times, only now rather than a button we are using a photoresistor...
<img src="https://user-images.githubusercontent.com/71406831/135154892-4c6eeadd-1860-45de-8185-c711fea61efe.png" alt="wiring"  style="width:500px;">

#### Code
> We used the analog pin A0 and the command analogRead() to read the value of the photoresistor which was the overall basis and "spicy part of the assignment".

```C++

int light = 0; // initial state of light

void setup() {
    // put your setup code here, to run once:
    Serial.begin(9600); // connect things together so they can function
    pinMode(8, OUTPUT); // connect inputs and outputs
}

void loop() {
    // put your main code here, to run:
    light = analogRead(A0); // read in order to export a value or result
    
    Serial.println(light); // run depending on lighting results
 
    if(light > 450) { // If it is bright...
        Serial.println("It is quite light!");
        digitalWrite(8,LOW); //turn left LED off
    }
    else { // If it's dark...
        Serial.println("It is pretty dark!");
        digitalWrite(8,HIGH); // Turn left LED on
    }
    delay(1000); // just giving device a way to not be overwhelemed.
}

```

#### Evidence (The Photoresistor in all its glory!)
<img src="https://github.com/dcaffer07/LED-review-E2/blob/main/Media/Phgotoresitor%20gif.gif?raw=true" alt="wiring"  style="width:500px;">

#### Reflection
> All in all I really enjoyed this assignemnt, again... some takeways... 
> - Use "if" "else" to express, if lightgretarer than this.. do this, if not do this and use specific values to work with.
> - Same deal as potentiometer, use former knowledge and examples in code, makes everything easier.  Didn't initially but helps a lot.
> - Genually think.  what is the goal, how can I achieve.  Again, keep it simple, don't ver complicate.
>
> I think it did a good job incorporating some of the things that we did in the past with neer things making for a fun and cool experience.  This was by far my favoritre assignemnt so far and I look forwar to more like it in the future!

[Back to Top](https://github.com/dcaffer07/Aurduino.cc-review-E2/blob/main/README.md#aurduinocc-review-e2-notsobasicaurduino)


