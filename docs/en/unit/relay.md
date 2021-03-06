# Unit RELAY {docsify-ignore-all}

<img src="assets/img/product_pics/unit/M5GO_Unit_relay.png" width="30%" height="30%"><img src="assets/img/product_pics/unit/unit_relay_grove_b.png" width="30%" height="30%">

***

:clapper: **[Video Tutorial](#Video-Tutorial)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:memo:**[Description](#Description)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:octocat:**[Example](#Example)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; :electric_plug:**[Schematic](#Schematic)** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;🛒**[Purchase](https://www.aliexpress.com/store/product/M5Stack-Official-Mini-Relay-Unit-DC-3A-30V-AC-3A-220V-with-Triode-Driven-GROVE-Port/3226069_32922856211.html?spm=a2g1y.12024536.productList_5885013.subject_24)**

## Description

**RELAY**, as its namesake, is a M5Unit that implenments a Relay functions. Relay can be used as an electrically operated switch, uses an electromagnet to mechanically operate a switch,to where it is necessary to control a large power load circuit by a separate low-power signal, like a digital signal output from a mircoprocessor. Up to 30V DC and 220V AC.

There are 3 pins named: ON, OFF, COM. You can program to make COM connect to ON or OFF, just by high and low out put of a digital GPIO.

## Product Features

-  Single-BUS control
-  Up to 3A @ 30 V DC or 220 V AC
- Software Development Platform: Arduino, UIFlow(Blockly,Python)
- Two Lego-compatible holes

## Include

- 1x RELAY Unit
- 1x Grove Cable
- 1x 3.96 soket

## Application

- Remote control of high-power appliances, such as refrigerators, air conditioners, TVs, etc.

## Related Link

- **[Offical Video](https://www.youtube.com/channel/UCozgFVglWYQXbvTmGyS739w)**

- **[Forum](http://forum.m5stack.com/)**

## Example

### 1. Arduino IDE

*The code below is incomplete. To get complete code, please click [here](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/RELAY/Arduino).*

```arduino
#include <M5Stack.h>

void setup() {
  M5.begin();
  M5.Lcd.clear(BLACK);
  M5.Lcd.setTextFont(4);
  M5.Lcd.setTextColor(YELLOW, BLACK);
  //disable the speak noise
  dacWrite(25, 0);
  pinMode(26, OUTPUT);// RELAY Pin setting
}

void loop(void) {
  digitalWrite(26, HIGH);// RELAY Unit work
  delay(500);
  digitalWrite(26, LOW);// RELAY Unit stop work
  delay(500);
}
```

### 2. UIFlow

*To get complete code, please click [here](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/RELAY/UIFlow).*

<img src="assets/img/product_pics/unit/unit_example/RELAY/example_unit_relay_01.png">

## Schematic

<img src="assets/img/product_pics/unit/relay_sch.JPG">

### PinMap

<table>
 <tr><td>M5Core(GROVE B)</td><td>GPIO36</td><td>GPIO26</td><td>5V</td><td>GND</td></tr>
 <tr><td>RELAY Unit</td><td> </td><td>RELAY Controlling Pin</td><td>5V</td><td>GND</td></tr>
</table>

## Video Tutorial

**Program with UIFlow**

<video width="500" height="315" controls>
    <source src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/video/LukeVideo/Blinking%20a%20bulb%20with%20the%20M5%20Relay%20unit..mp4" type="video/mp4">
</video>