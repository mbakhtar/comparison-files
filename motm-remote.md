# Mission on the Moon - Bluetooth Remote
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
sonar=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Welcome to Mission on the Moon - Bluetooth Remote
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
Click ``||Radio:Radio||`` drag and drop ``||Radio:radio set group||`` block 
inside ``||basic:on start||`` loop.
```blocks
radio.setGroup(1)
```
## Step 6
Click ``||Input:Input||`` drag and drop ``||Input:on button A pressed||`` block
on the workspace.
```blocks
input.onButtonPressed(Button.A, function () {
    })
radio.setGroup(1)
```
## Step 7
Right click ``||Input:on button A pressed||`` block and duplicate it. Change
``||Input:A||`` to ``||Input:B||``.
```blocks
input.onButtonPressed(Button.A, function () {
    })
input.onButtonPressed(Button.B, function () {
})
radio.setGroup(1)
```
## Step 8
Right click ``||Input:on button A pressed||`` block and duplicate it. Change
``||Input:A||`` to ``||Input:A+B||``.
```blocks
input.onButtonPressed(Button.A, function () {
    })
input.onButtonPressed(Button.B, function () {
})
radio.setGroup(1)
input.onButtonPressed(Button.AB, function () {
})
```
## Step 9
Click ``||Radio:Radio||`` drag and drop ``||Radio:on radio received||``
``||Variables:receivedString||`` block.
on the workspace.
```blocks
input.onButtonPressed(Button.A, function () {
})
input.onButtonPressed(Button.AB, function () {
})
input.onButtonPressed(Button.B, function () {
})
radio.onReceivedString(function (receivedString) {
})
radio.setGroup(1)
```
## Step 10
Click ``||Radio:Radio||`` drag and drop ``||Radio:radio send string||`` block 
inside ``||Input:on button A pressed||`` block, ``||Input:on button B pressed||`` 
block and ``||Input:on button A+B pressed||`` block.
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("")
})
input.onButtonPressed(Button.B, function () {
radio.sendString("")
})
input.onButtonPressed(Button.AB, function () {
radio.sendString("")
})
radio.onReceivedString(function (receivedString) {
})
radio.setGroup(1)
```
## Step 11
Click ``||Basic:Basic||`` drag and drop ``||Basic:show icon||`` block 
under ``||Radio:radio send string||`` block. Repeat this for ``||Input:on button B pressed||``
block and ``||Input:on button A+B pressed||`` block. 
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
radio.onReceivedString(function (receivedString) {
})
radio.setGroup(1)
```
## Step 12
Click ``||Basic:Basic||`` drag and drop ``||Basic:show string||`` block under
``||Radio:on radio received||`` ``||Variables:receivedString||`` block.
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendString("")
    basic.showIcon(IconNames.Heart)
})
radio.onReceivedString(function (receivedString) {
    basic.showString("")
})
radio.setGroup(1)
```
## Step 13
Add messages to all ``||Radio:radio send string||`` blocks.
- Type ``||How's the weather||`` inside ``||Input:on button A pressed||`` block.
- Type ``||Call Again||`` inside ``||Input:on button B pressed||`` block.
- Type ``||It's a blizzard going on||`` inside ``||Input:on button A+B pressed||`` block.
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("How's the weather")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("Call again")
    basic.showIcon(IconNames.Heart)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendString("It's blizzard going on")
    basic.showIcon(IconNames.Heart)
})
radio.onReceivedString(function (receivedString) {
    basic.showString("")
})
radio.setGroup(1)
```
## Step 14
Change ``||Basic:show icon||`` ``||basic:Heart icons||`` under all ``||Input:Input||`` blocks.
- Change to ``||Basic:Yes icon||`` inside ``||Input:on button A pressed||`` 
block.
- Change to ``||Basic:Square icon||`` inside ``||Input:on button B pressed||``
block.
- Change to ``||Basic:Sad icon||`` inside ``||Input:on button A+B pressed||``
block.
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("How's the weather")
    basic.showIcon(IconNames.Yes)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("Call again")
    basic.showIcon(IconNames.Square)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendString("It's blizzard going on")
    basic.showIcon(IconNames.Sad)
})
radio.onReceivedString(function (receivedString) {
    basic.showString("")
})
radio.setGroup(1)
```
## Step 15
Drag and drop ``||Variables:receivedString||`` from the ``||Radio:on radio received||``
block to replace ``||Basic:show string||`` parameter.
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("How's the weather")
    basic.showIcon(IconNames.Yes)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("Call again")
    basic.showIcon(IconNames.Square)
})
input.onButtonPressed(Button.AB, function () {
    radio.sendString("It's blizzard going on")
    basic.showIcon(IconNames.Sad)
})
radio.onReceivedString(function (receivedString) {
    basic.showString(receivedString)
})
radio.setGroup(1)
```
## Step 16
``|Download|`` and test your code. 
Congratulations on completing your Mission on the Moon - Bluetooth Remote Prototype! - Go back to the lesson for more activities and extensions.
