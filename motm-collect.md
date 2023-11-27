# Mission on the Moon - Object Collection
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
sonar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Welcome to Mission on the Moon - Object Collection
![built project](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/project-electriccar-400.png)

## Step 2 @showdialog
Plug your USB cable into the micro:bit. 
![breakout board](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/connect-microbit.gif)

## Step 3 @showdialog
Insert it into the Climate Action Kit board. 
![breakout board](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/breakout-resized.png)

## Step 4 @showhint
Click three dots besides ``|Download|`` button and follow the steps to pair your micro:bit.
![pair gif](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/pairmicrobit-280x203.gif)

## Step 5
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:Setup Driving||`` block inside ``||basic:on start||`` loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo1,
)
```
## Step 6
Change the ``||fwdMotors:right motor to servo3||``. 
Keep the ``||fwdMotors: left motor to servo1||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
```
## Step 7
Click ``||logic:Logic||`` drag and drop ``||logic:if true then||`` block inside ``||basic:forever||`` 
loop.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
basic.forever(function () {
    if (true) {}
        })
```
## Step 8
Click ``||Input:Input||`` drag and drop ``||Input:button A is pressed||``
block to replace the ``||logic:true||`` condition.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
basic.forever(function () {
    if (input.buttonIsPressed(Button.A)) {
    }
})
```
## Step 9
Click ``||Loops:Loops||`` drag and drop ``||Loops:repeat 4 times||`` block
under ``||Logic:if||`` ``||Input:button A is pressed||`` ``||Logic:then||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
basic.forever(function () {
    if (input.buttonIsPressed(Button.A)) {
        for (let index = 0; index < 4; index++){}
        } 
    })
```
## Step 10
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:drive forward at 50||``
block inside ``||loops:repeat 4 times||`` loop block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
0
)
fwdMotors.servo1.fwdSetAngle(0)
basic.forever(function () {
    if (input.buttonIsPressed(Button.A)) {
        for (let index = 0; index < 4; index++) {
            fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
        }
    }
})
```
## Step 11
Click ``||basic:Basic||`` drag and drop ``||basic:pause (ms) 100||`` block
under ``||fwdMotors:drive forward at 50||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(100)
    }
    }
})
```
## Step 12
Change ``||basic:pause (ms) 100||`` to ``||basic: (ms) 2000||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    }
    }
})
```
## Step 13
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:set servo1 0 '||`` 
block under ``||basic:pause (ms) 2000||`` block. Change ``||fwdMotors:servo1||`` to
``||fwdMotors:servo2||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    fwdMotors.servo2.fwdSetAngle(0)
    }
    }
})
```
## Step 14
Change ``||fwdMotors:set servo2 to 0 '||`` to ``||fwdMotors:45||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    fwdMotors.servo2.fwdSetAngle(45)
    }
    }
})
```
## Step 15
Click ``||basic:Basic||`` drag and drop ``||basic:pause (ms) 100||`` under 
``||fwdMotors:set servo2 to 45 '||`` block. Change ``||basic:(ms) 100||`` to
``||basic:(ms) 500||``
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    fwdMotors.servo2.fwdSetAngle(45)
    basic.pause(500)
    }
    }
})
```
## Step 16
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:set servo1 to 0 '||``
block under ``||basic:pause (ms) 500||`` block. Change ``||fwdMotors:servo1||`` to
``||fwdMotors:servo2||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo2.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    fwdMotors.servo2.fwdSetAngle(45)
    basic.pause(500)
    fwdMotors.servo2.fwdSetAngle(0)
    }
    }
})
```
## Step 17
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:stop motors||`` block
under ``||loops:repeat 4 times||`` block.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
)
fwdMotors.servo1.fwdSetAngle(0)
basic.forever(function () {
if (input.buttonIsPressed(Button.A)) {
    for (let index = 0; index < 4; index++) {
    fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 50)
    basic.pause(2000)
    fwdMotors.servo2.fwdSetAngle(45)
    basic.pause(500)
    fwdMotors.servo2.fwdSetAngle(0)
    }
    fwdMotors.stop()
    }
})
```

## Step 18
Click ``||fwdMotors:+||`` on ``||fwdMotors:Setup Driving||``
block inside ``||basic:on start||`` block. Set bias to ``||fwdMotors: 0||``.
```blocks
fwdMotors.setupDriving(
fwdMotors.servo1,
fwdMotors.servo3,
0
)
fwdMotors.servo1.fwdSetAngle(0)
basic.forever(function () {
    if (input.buttonIsPressed(Button.A)) {
        for (let index = 0; index < 4; index++) {
            fwdMotors.drive(fwdMotors.DrivingDirection.Forward, 100)
            basic.pause(2000)
            fwdMotors.servo2.fwdSetAngle(45)
            basic.pause(500)
            fwdMotors.servo2.fwdSetAngle(0)
        }
        fwdMotors.stop()
    }
})
```

## Step 19
``|Download|`` and test your code. 
Congratulations on completing your Mission on the Moon - Object Collection! - Go back to the lesson for more activities and extensions.
