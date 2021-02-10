# REKA:BIT Extension for Microsoft MakeCode

This library provides the driver for [**REKA:BIT** - Simplifying micro:bit for Robotics](https://www.cytron.io/p-reka-bit).

![REKA:BIT](https://raw.githubusercontent.com/CytronTechnologies/pxt-rekabit/master/icon.png)

### DC Motors

Run Motor 1 forward at 50% speed when button A is pressed, brake the motor when button B is pressed.

```blocks
input.onButtonPressed(Button.A, function () {
    rekabit.runMotor(MotorChannel.M1, MotorDirection.Forward, 127)
})
input.onButtonPressed(Button.B, function () {
    rekabit.brakeMotor(MotorChannel.M1)
})
```

### Servos

Button A pressed - Rotate Servo 1 to 0 degree.
Button B pressed - Rotate Servo 1 to 180 degrees (By setting the pulse width to 2500 us).
Button A+B pressed - Disable Servo 1. No pulse is sent to Servo 1 and it can be rotated by hand.

```blocks
input.onButtonPressed(Button.A, function () {
    rekabit.setServoPosition(ServoChannel.S1, 0)
})
input.onButtonPressed(Button.AB, function () {
    rekabit.disableServo(ServoChannel.S1)
})
input.onButtonPressed(Button.B, function () {
    rekabit.setServoPulseWidth(ServoChannel.S1, 2500)
})
```

## RGB LEDs

Clear all RGB pixels.

```blocks
rekabit.clearAllRgbPixels()
```

Change the RGB pixels brightness to maximum.

```blocks
rekabit.setRgbBrightness(255)
```

Show color green on all RGB pixels and change the color one by one to red.

```blocks
rekabit.setAllRgbPixelsColor(0x00ff00)
basic.pause(1000)
rekabit.setRgbPixelColor(0, 0xff0000)
basic.pause(500)
rekabit.setRgbPixelColor(1, 0xff0000)
```

## License

MIT

## Supported targets

* for PXT/microbit

