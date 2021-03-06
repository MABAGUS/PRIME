# Unit NCIR {docsify-ignore-all}

<img src="assets/img/product_pics/unit/M5GO_Unit_ncir.png" width="30%" height="30%"><img src="assets/img/product_pics/unit/unit_ncir_grove_a.png" width="30%" height="30%">

***

:memo:**[Description](#Description)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:octocat:**[Example](#Example)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; :electric_plug:**[Schematic](#Schematic)** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;🛒**[Purchase](https://www.aliexpress.com/store/product/M5Stack-Official-NCIR-Unit-MLX90614-Contactless-Temperature-Sensor-Module-70C-382-2C-GROVE-I2C-Development-Board/3226069_32947772098.html?spm=a2g1x.12024536.productList_5885013.pic_4)**

## Description

**NCIR** featured with built-in infrared sensor **MLX90614**. It can be used to measure the surface temperature of a human body or other object.

Unlike most temperature sensors, this sensor measures infrared light bouncing off of remote objects so it can sense temperature without having to touch them physically. Simply point the sensor towards what you want to measure and it will detect the temperature by absorbing IR waves emitted. Because it doesn't have to touch the object it's measuring, it can sense a wider range of temperatures than most digital sensors: from -70°C to +380°C! It takes the measurement over an 90-degree field of view so it can be handy for determining the average temperature of an area.

Connect with M5Core via GROVE A IIC(0x5A).

## Product Features

- Operating voltage: 4.5 to 5.5V
- Measuring temperature range: -70°C ~ 382.2°C
- Measurement accuracy at room temperature: ±0.5°C
- Field of view: 90°
- Sofrware Development Platform: Arduino, UIFlow(Blockly, Python)
- Two Lego-compatible holes

## Include

- 1x NCIR Unit
- 1x Grove Cable

## APPLICATION

-  Body Temperature Measurement
-  Object (biological) Motion Detection

## Related Link

- **[Offical Video](https://www.youtube.com/channel/UCozgFVglWYQXbvTmGyS739w)**

- **[Forum](http://forum.m5stack.com/)**

-  **Datasheet** - [MLX90614](https://pdf1.alldatasheet.com/datasheet-pdf/view/218977/ETC2/MLX90614.html)

## Example

### 1. Arduino IDE

*The code below is incomplete. TO get complete code, please click [here](https://github.com/m5stack/M5Stack/tree/master/examples/Unit/NCIR).*

```arduino
#include <M5Stack.h>
#include <Wire.h>

#define NCIR_ADDR 0x5A

// declaration
uint16_t result;
float temperature;

// initialization
Wire.begin();\
M5.begin();

// read data
Wire.beginTransmission(NCIR_ADDR);Wire.write(0x07);Wire.endTransmission(false);
Wire.requestFrom(NCIR_ADDR, 2);
result = Wire.read();// Receive DATA
result |= Wire.read() << 8;// Receive DATA

// store temperature value
temperature = result * 0.02 - 273.15;
```

<img src="assets/img/product_pics/unit/unit_example/NCIR/example_unit_ncir_04.png">

### 2. UIFlow

*TO get complete code, please click [here](https://github.com/m5stack/M5-ProductExampleCodes/tree/master/Unit/NCIR/UIFlow).*

<img src="assets/img/product_pics/unit/unit_example/NCIR/example_unit_ncir_03.png">

## Schematic

<img src="assets/img/product_pics/unit/ncir_sch.JPG">

### PinMap

<table>
 <tr><td>M5Core (GROVE A)</td><td>GPIO22</td><td>GPIO21</td><td>5V</td><td>GND</td></tr>
 <tr><td>NCIR Unit</td><td>SCL</td><td>SDA</td><td>5V</td><td>GND</td></tr>
</table>