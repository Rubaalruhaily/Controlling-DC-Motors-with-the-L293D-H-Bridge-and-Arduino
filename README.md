# Controlling-DC-Motors-with-the-L293D-H-Bridge-and-Arduino
Controlling DC Motors with the L293D H-Bridge and Arduino

# Tools:

* Breadboard.
* Arduino Uno R3.
* DC Motors.
* Wires.
* L293D H Bridge.
* Battery


# Steps:

Each chip contains two full H-bridges (four half H-bridges). That means you can drive four solenoids, two DC motors bi-directionally, or one stepper motor. Just make sure they're good for under 600 mA since that's the limit of this chip. They do handle a peak of 1.2A but that's just for a short amount of time. 

There's a PWM input per driver so you can control motor speed. Runs at 5V logic. Good for motor voltages from 4.5V up to 36V! This wont work well for 3V motors. The motor voltage is separate from the logic voltage.

The L293D has two +V pins (8 and 16). The pin '+Vmotor (8) provides the power for the motors, and +V (16) for the chip's logic. 

Normally we can connect both of these to the Arduino 5V pin. We used a powerful motor, or a higher voltage motor. So we provided the motor with a separate power supply using pin 8 connected to the positive power supply and the ground of the second power supply is connected to the ground of the Arduino.

![18](https://user-images.githubusercontent.com/86341464/127261452-bc240e8d-107b-43c0-816c-abee6a7d66b7.PNG)


# Code:
```
const int leftForward = 2;
const int leftBackward = 3;
const int rightForward = 4;
const int rightBackward = 5;

void setup() 
{
  pinMode(leftForward , OUTPUT);
  pinMode(leftBackward , OUTPUT);
  pinMode(rightForward , OUTPUT);
  pinMode(rightBackward , OUTPUT);

}

void loop()
{
  digitalWrite(leftForward , HIGH);
  digitalWrite(leftBackward , LOW);
  digitalWrite(rightForward , HIGH);
  digitalWrite(rightBackward , LOW);
 
}
```
# Source
https://create.arduino.cc/editor/mertarduinotech/a6386542-05da-4f3e-9bb6-80ddadc8107c/preview
