# LED-review-E2
## Aurduino review assignment

### LED Blink w/ Button

### LED Fade w/o Button
#### Description:
> Make an LED fade in and out.
#### Goal:
> The goal and prurpose of this assignment was to eintroduce and familiarize ourselves to aurdunos and their code again.  In this assigment we were tasked with making an LED fade in and out, rather than blink without a button, or really any other restrictions such as speed or amopunt of times.  The primary differnece in accomplishing this in thge code compared to having an LED blink was using the anaolgWrite(); function rather than the digitalWrite(); function.  Asside from that they used many of the same things such as connecfting and establishing ppins, serial.print.ln, ect.
#### Wiriring
> Ver6y straight forward, simply connect an LED to the groundand a pin for power supply ad direction, and than add resisterns to ensure proper use of electricity...
<img src="https://user-images.githubusercontent.com/71406831/133321835-78fca232-3509-4fd2-81b5-626428592a99.png" alt="Italian Trulli"  style="width:500px;">
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
