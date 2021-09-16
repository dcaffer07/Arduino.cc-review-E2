# LED-review-E2
## Aurduino review assignment

### LED Blink w/ Button
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
### LED Fade w/o Button

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
 Fade

 This example shows how to fade an LED on pin 9
 using the analogWrite() function.

 This example code is in the public domain.
 */

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
#### Reflection:
> All in all I think that this assigmant was extermely effective in refreshing our memory of code and getting back into the swing of things.  I enjoyed geting to begin with things that I was comfortable with and than gradually introducing harder and less familiar material such as the analogWrite()function.  It was great to get back into the swiung of things and I look forward to creatinmg more code in the future.
