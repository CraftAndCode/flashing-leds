# Flashing LEDs

```package
core
radio
microphone
```
```template
basic.forever(function () {
	
})
```

## Step 0 @showDialog
Hello! With this tutorial, you'll learn to control external LEDs with Micro:bit!

## Step 1 @showDialog
Before we start, let's make sure that your LEDs are connected to the Micro:bit according to this schematic:
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/mood%20badge%20schematic.gif)


## Step 2 @showHint
### Turning LEDs on
First, find the ``||pins.digital write pin||`` block in your toolbox under the ``||pins.pins||`` category and place this block inside the ``||basic.forever||`` block.
```hint
This is what it looks like:
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```
## Step 3 @showDialog
The Micro:bit has 25 external connections on the edge connector of the board, which we call 'pins'.
  
There are five large pins, that are also connected to holes in the board labelled: 0, 1, 2, 3V, and GND. The ``||pins.digital write pin||`` block can be used to turn the LEDs connected to the pins on your Micro:bit on and off.

## Step 4 @showHint
### Turning LEDs on
Let's turn the green LED on! Change the value inside the ``||pins.digital write pin||`` block from 0 to 1.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
})
```

## Step 5 @showHint
### Turning LEDs on
The MakeCode simulator has no idea if your Micro:bit has LEDs connected, so it doesn't display them. Let's download your program to check if they light up!
```hint
As you see, the pin labelled `0` is now highlighted. 
That means that your Micro:bit now outputs power through this pin.
```
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/LED0.png)

## Step 6 @showHint
### Flashing LEDs
Now, it's time to make our LED flash! Modify our code as shown to make Micro:bit turn the pin 0 on and off repeatedly, then download your code to Micro:bit.
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    basic.pause(500)
})
```
## Step 7
### Challenge
It's time for a challenge! Your task is to modify the code to blink 2 LEDs simultaneously.
```hint
To blink both LEDs, you need to forever: 
```
* Turn the pin 0 on,
* Turn the pin 1 on,
* Wait for some time,
* Turn the pin 0 off,
* Turn the pin 1 off,
* Wait for some time again.

## Step 8
### Do it yourself
Now use everything you've learned today to program a version of the traffic lights. Make the lights switch from red to green and the other way with buttons!

## Answers
### Challenge
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 0)
    basic.pause(500)
})
```

### Do it yourself @showDialog
Your code can be something like this:
```blocks
pins.digitalWritePin(DigitalPin.P1, 1)
input.onButtonPressed(Button.A, function () {
    pins.digitalWritePin(DigitalPin.P1, 0)
    pins.digitalWritePin(DigitalPin.P0, 1)
})
input.onButtonPressed(Button.B, function () {
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 1)
})
```

