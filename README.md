README.md

 Created on: 5 janv. 2013
     Author: Xavier Halgand
     
STM32F4 Discovery board open source project.

"Ambiantiseur" ( Ambientizer in english) is a very basic synthesizer 
which can produce semi-randomly generated musical sequences with a few effects (delay and phaser).
Demo here : http://www.youtube.com/watch?v=fMWcXrCg1iw

Four potentiometers and one switch allow the user to control the machine.
The two position switch allow you to modify 2 x 4 = 8 parameters :
Switch = 0 ->
	pot1 : tempo
	pot2 : notes scales
	pot3 : delay time
	pot4 : delay feedback
Switch = 1 ->
	pot1 : note duration (decay time)
	pot2 : phaser rate
	pot3 : phaser feedback
	pot4 : master volume

When switch is toggled, parameter will be adjusted only when the potentiometer is moved and reaches previous value.
The LEDS light on when the pot is at real position.
That is done for avoiding brutal value jumps. (Could be improved)

The tone generator is an anti-aliased minBLEP sawtooth oscillator with light vibrato.

Wirings :
Switch and pots are 3V board powered.
	switch : PA1
	pot1   : PB1
	pot2   : PC1
	pot3   : PC2
	pot4   : PC4
Three additional pots or switches can be wired on PA2, PA3, PB0. Their values appear in ADC1ConvertedValues[0...7] array.