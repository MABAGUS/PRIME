# Unit Dual-BUTTON {docsify-ignore-all}

<img src="assets/img/product_pics/unit/M5GO_Unit_dual_button.png" width="30%" height="30%"><img src="assets/img/product_pics/unit/unit_dual_button_grove_b.png" width="30%" height="30%">

***

:memo:**[Description](#Description)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:octocat:**[Example](#Example)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; :electric_plug:**[Schematic](#Schematic)** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;🛒**[Purchase](https://www.aliexpress.com/store/product/M5Stack-Official-New-Mini-Dual-Button-Unit-Mini-with-GROVE-Port-Cable-Connector-Compatible-with-FIRE/3226069_32923126250.html?spm=a2g1x.12024536.productList_2187621.9)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:clapper:**[Related Video](#Related-Video)**

## Description

**Dual Button**, as its namesake, has two buttons with different color. If the Button unit is not enough, how about double it up to a pair. They share the exact same mechanism, button status can be detected by the input pin status,simply capture the high/low electrical level.

This unit communicates with M5Core through GROVE B port.

<img src="assets/img/product_pics/unit/dual_button/unit_dual_button_05.png" width="50%" height="50%">

**Output status:**

<img src="assets/img/product_pics/unit/dual_button/unit_dual_button_08.png">

## Product Features

- GROVE interface, support [UIFlow](http://flow.m5stack.com) and [Arduino](http://www.arduino.cc)
- Two Lego-compatible holes

## Include

- 1x Dual BUTTON Unit
- 1x Grove Cable

## Application

- Game Controller
- Remote control switch

## Related Link

- **[Offical Video](https://www.youtube.com/channel/UCozgFVglWYQXbvTmGyS739w)**

- **[Forum](http://forum.m5stack.com/)**

## Example

### 1. Arduino IDE

*The code below is incomplete(just for usage). TO get the complete code, please click [here](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/DUAL_BUTTON/Arduino).*

```arduino
#include <M5Stack.h>

// declaration
int cur_value_red = 0;
int cur_value_blue = 0;

// initialization
M5.begin();
pinMode(26, INPUT);// Red Button Pin setting
pinMode(36, INPUT);// Blue Button Pin setting

// read data
cur_value_red = digitalRead(26);
cur_value_blue = digitalRead(36);
M5.update();
```

### 2. UIFlow

*To get the complete code, please click [here](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/DUAL_BUTTON/UIFlow).*

<img src="assets/img/product_pics/unit/unit_example/DUAL_BUTTON/example_unit_dual_button_05.png">

## Schematic

<img src="assets/img/product_pics/unit/dual_button_sch.png">

### PinMap

<table>
 <tr><td>M5Core (GROVE B)</td><td>GPIO36</td><td>GPIO26</td><td>5V</td><td>GND</td></tr>
 <tr><td>DUAL_BUTTON Unit</td><td>Blue Button Pin</td><td>Red Button Pin</td><td>5V</td><td>GND</td></tr>
</table>

## Related Video

**Joystick Case - Page flipping and selection of menu interface**

<video width="500" height="315" controls>
    <source src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/video/Blog/Twitch201811/M5Game-VARIOUS2.mp4" type="video/mp4">
</video>