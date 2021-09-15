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
  Fade

  This example shows how to fade an LED on pin 9 using the analogWrite()
  function.

  The analogWrite() function uses PWM, so if you want to change the pin you're
  using, be sure to use another PWM capable pin. On most Arduino, the PWM pins
  are identified with a "~" sign, like ~3, ~5, ~6, ~9, ~10 and ~11.

  This example code is in the public domain.

  https://www.arduino.cc/en/Tutorial/BuiltInExamples/Fade
*/

int led = 9;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by

// the setup routine runs once when you press reset:
void setup() {
  // declare pin 9 to be an output:
  pinMode(led, OUTPUT);
}
```
