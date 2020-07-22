# Object-Counter-Using-8051
Object counter using 8051 microcontroller. This circuit can count  the number of objects passing across a line , 
number of persons passing through a gate/door and so on. The can be simply divided into two sections i.e. the sensor section and the display section.

Sensor.
The sensor part consists of a ultra bright led (with focus), and LDR, opamp LM324 and the associated passive components. 
The LED is placed on one side of the door and the LDR is placed on the other side so that the light from the LED falls directly on the LDR.
As you know, the resistance of the LDR has an inverse relationship with the intensity of the light falling on it. 
The preset resistor R14 is so adjusted that the voltage across the LDR is below 1.5V when it is illuminated.
This voltage (labelled A in the circuit diagram) is connected to the inverting input of the opamp which is wired as a
comparator with reference voltage 1.5V (set using R15 and R16).Capacitor C1 is meant for bypassing noise or anything like 
that which may cause false triggering.Resistor R13 is meant to control the current through the LED.
When the light is falling on the LDR the voltage across it will be less than the reference voltage and so the output of the opamp
remains high. When the light beam is interrupted, the voltage across the LDR goes above the reference voltage and so the opamp output goes low and it indicates a pass.

Display section.
The output of the opamp is fed to the INTO (interrupt 0) pin of the microcontroller. The microcontroller is programmed to count 
the number of negative edge pulses received at the INT0 pin and displays it on the three digit seven segment display.
