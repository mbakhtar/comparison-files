# How Wind Turbines Capture Kinetic Energy
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Bienvenue dans le tutoriel de codage pour Comment les turbines éoliennes capturent  l’énergie cinétique.
![built project](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/project-windturbine-200.png)

## Step 2 @showdialog
Dans ce tutoriel, nous allons calculer le temps des révolutions, puis nous allons l’utiliser pour résoudre l’équation permettant de trouver le (TPM) de la turbine éolienne.

## Step 3 @showdialog
Allume la plaque de la trousse d’action climatique.
![breakout board](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/breakout-turn-on.png)

## Step 4 @showhint
Clique sur les trois points à côté du bouton ``|Download|`` et puis, clique sur Connecter l’appareil. Ensuite, suis les étapes pour coupler ton micro:bit.
![pair gif](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/pairmicrobit-280x203.gif)

## Step 5 @showhint
Ensuite, clique sur le bouton ``|Download|`` pour télécharger le projet vide afin de  démarrer les simulateurs.

## Step 6 @showhint
Regarde sous le simulateur @boardname@ pour voir la carte de la trousse d’action climatique et les capteurs connectés.  Essaie de tourner le cadran de ton projet, le simulateur virtuel y réagira.![wind](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/simulator-6-Dial.gif)

## Step 7
Clique sur ``||fwdSensors:Capteurs||`` drag and drop
``||fwdSensors:en dial1 tourné par difference||`` block in workspace.
```blocks
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    })
```
## Step 8
Right Clique sur ``||fwdSensors:en dial1 tourné par difference||`` block and duplicate. _Note: New block will be grey._
![greyed out example](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/dial-greyed-out-demo.png)

## Step 9
Change the direction arrow of the greyed out ``||fwdSensors:en dial1 tourné par difference||`` block. _Note: Greyed out block will turn green._
![dial direction](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/dial-direction-switch.gif)
```blocks
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    })
```
## Step 10
Clique sur ``||fwdSensors:Capteurs||`` drag and drop
``||fwdSensors:on touch down||`` block in workspace.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    })
```
## Step 11
Clique sur ``||fwdMotors:Moteurs||`` drag and drop
``||fwdMotors:mettre leftServo 50 %||`` inside
``||fwdSensors:en dial1 tourné par difference||`` block. Change ``||fwdMotors:leftServo||``
to ``||fwdMotors:middleServo||``.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(50)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    })
```
## Step 12
Right Clique sur ``||fwdMotors:mettre middleServo 50 %||`` block and duplicate.
Drag and drop inside the second ``||fwdSensors:en dial1 tourné par difference||`` block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(50)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(50)
})
```
## Step 13
Clique sur ``||fwdSensors:Capteurs||``. Drag ``||fwdSensors:dial1 position absolue||`` oval block close to ``||fwdMotors:mettre middleServo 50 %||`` replace ``||fwdMotors:50 %||`` of ``||fwdMotors:mettre middleServo 50 %||`` block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(50)
})
```
## Step 14
Repeat the last step, Clique sur ``||fwdSensors:Capteurs||``.
Drag ``||fwdSensors:dial1 position absolue||`` oval block close to the other
``||fwdMotors:mettre middleServo 50 %||`` replace ``||fwdMotors:50 %||`` of ``||fwdMotors:mettre middleServo 50 %||`` block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 15
Clique sur ``||fwdMotors:Moteurs||`` drag and drop ``||fwdMotors:mettre leftServo 50 %||`` block
 inside ``||fwdSensors:on touch down||`` block. Change ``||fwdMotors:leftServo||`` to ``||fwdMotors:middleServo||``.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(50)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 16
Change speed of ``||fwdMotors:mettre middleServo 50 %||`` block inside ``||fwdSensors:on touch down||``
to ``||0||``.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```

## Step 17
Clique sur on ``||Variables:Variables||`` and make ``||Variables:2||`` ``||Variables:Variables||``.
- ``||Variables:start_time||``
- ``||Variables:stop_time||``
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 18
Clique sur on ``||Variables:Variables||`` drag and drop ``||Variables:définir start_time à 0||``
inside ``||Basic:au démarrage||`` block. Repeat this for ``||Variables:définir stop_time à 0||`` block.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 19
Clique sur ``||Input:Entrée||``  drag and drop ``||Input:on button A pressed||`` block on the workspace.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
})
```
## Step 20
Clique sur ``||Input:Entrée||``  drag and drop another ``||Input:on button A pressed||`` block on the workspace.
_Note: This block will be greyed out._ Change the ``||Input:button A||`` to ``||Input:button B||``.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.B, function () {
})
```
## Step 21
Clique sur ``||Variables:Variables||`` drag and drop ``||Variables:définir start_time à 0||`` inside
``||Input:on button A pressed||``.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
})
```
## Step 22
Clique sur ``||Variables:Variables||`` drag and drop ``||Variables:définir stop_time à 0||`` inside
``||Input:on button B pressed||``.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
stop_time = 0
})
```
## Step 23
Clique sur ``||Basic:Basic||`` drag and drop ``||Basic:show number||`` block under
``||Variables:définir stop_time à 0||`` inside ``||Input:on button B pressed||`` block.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
stop_time = 0
basic.showNumber(0)
})
```
## Step 24
Clique sur ``||Math:Math||`` drag and drop
``||Math:Division operator||`` block to replace the ``||Basic:0||`` of
``||Basic:show number||`` block. For ``||Math:Division||`` change the 
right ``||Math:0||`` to ``||Math:1000||``.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
stop_time = 0
basic.showNumber(0/1000)
})
```
## Step 25
Clique sur ``||Math:Math||`` drag and drop
``||Math:Subtraction operator||`` block to replace the left ``||Math:0||`` of
``||Math:0 / 1000||`` block. 
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
stop_time = 0
basic.showNumber((0-0)/1000)
})
```
## Step 26
Clique sur ``||Variables:Variables||`` drag and drop ``||Variables:stop_time||`` to
replace left ``||Math:0||``. Drag and drop ``||Variables:start_time||`` to replace
right ``||Math:0||``.
```blocks
let stop_time = 0
let start_time = 0
let revolutions = 0
let RPM = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = 0
})
input.onButtonPressed(Button.B, function () {
stop_time = 0
basic.showNumber((stop_time - start_time)/1000)
})
```
## Step 27
Clique sur ``||Input:Entrée||``  and then ``||Input:...more||`` drag and drop ``||Input:running time||`` block to replace
``||0||`` in ``||Variables:start_time||`` and ``||Variables:stop_time||``
nested in ``||Input:on button A pressed||`` and ``||Input:on button B pressed||``
respectively.
```blocks
let stop_time = 0
let start_time = 0
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.middleServo.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CCW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.DialDirection.CW, function (difference) {
    fwdMotors.middleServo.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
input.onButtonPressed(Button.A, function () {
start_time = input.runningTime()
})
input.onButtonPressed(Button.B, function () {
stop_time = input.runningTime()
basic.showNumber((stop_time - start_time)/1000)
})
```
## Step 28 @showhint
``|Download|`` and test your code. Clique sur the bulb icon to see how
the simulator shows the components working.
![dial-servo](https://climate-action-kits.github.io/pxt-fwd-edu/tutorial-assets/simulator-13-wind.gif)

## Step 29 @showdialog
Congratulations on completing your How Wind Turbines Capture Kinetic Energy Project!

## Step 30 @showdialog
After your project is complete, go back to the lesson for more challenges and extensions.
