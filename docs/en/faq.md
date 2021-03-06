# FAQ {docsify-ignore-all}

**[CORE](#CORE-Question)**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**[UNIT](#UNIT-Question)**

## CORE Question

- **Q1: What's the difference between those Cores?**

    The main difference between these Cores is the internal hardware configuration and kit matching. From the basic version to the upgraded version, the attitude sensor MPU9250 is added and the RAM and FLASH are increased. For details, please visit [here](https://github.com/m5stack/M5-Schematic/blob/master/Core/hardware_difference_between_cores_en.md)。

    <img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/image/m5-docs_table/core_comparison/core_main_comparison_04_en.png">

    <img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/image/m5-docs_table/core_comparison/core_main_comparison_05_en.png">

- **Q2: How to turn off the speaker function of M5Core？**

    Add the following statement to functioin Setup( ){ }

    ```arduino
    dacWrite(M5STACKFIRE_SPEAKER_PIN, 0);
    ```

- **Q3: Some modules cannot be downloaded after stacking with M5Core, such as USB module and M5Core stacking.**

    Probably after the stack, the pins GPIO0 and M5Core on the M5-Bus bus are **not very well connected**.

    In this case, when downloading the program, GPIO0 should always remain low, but because the contact is not good, GPIO0 can not remain low all the time, so the download fails.

    **Solution:** Manually let GPIO0 connect to GND during the download process to ensure that it is pulled low enough。

- **Q4: After the [M5GO bottom](en/base/m5go_bottom) is stacked with the M5Core, the M5Core cannot be turned on, but the base battery in this M5GO bottom is fully charged.**

    It may be that after the stacking, the BATTERY of the lower left corner of the M5-Bus bus on the base is not well connected to the M5Core. This is
     caused by the deviation of the welding position during production. After **the bus pin welding position is slightly biased**, it is easy to see that the BATTERY pin is not in good contact with the M5Core.

    **Solution:** Re-soldering the M5-Bus bus header, the pin header must be strictly aligned with the pad position.

- **Q5: Some computers are connected to the main control, but still can't use Arduino IDE, ESPFlashDownloadTool or M5Burner to burn the program. For example, the following figure using Arduino IDE.**

    <img src="assets/img/faq/faq_03.png">

    **Solution:** you need to connect the capacitor between RST pin and GND pin in your Core (Capacitance value is more than 0.1 uF) or connect GPIO 0 with GND when downloading your firmware so that GPIO 0 keeps low level for an enough time as the third following picture shows.

    <img src="assets/img/faq/faq_05.png" width="80%" height="80%">

    <img src="assets/img/faq/faq_06.png" width="80%" height="80%">

    <img src="assets/img/faq/faq_07.png" width="100%" height="100%">

- **Q6: What special GPIO pins do you need to pay attention to in ESP32?**

    The ESP32 has 34 GPIO pins, of which GPIO 34-39 is only used as an input and cannot be used as an output. Others can be used as both an input and an output pin.

- **Q7: Why does the Stick with MPU9250 burn the factory firmware and press button A, the result shows "No", which means "No 9250"?**

    Restart this Stick and then it can display correctly. Because the code to read the MPU9250 is placed in the setup() function which only was executed once when booting. So reboot and let the Stick detect MPU9250 again.

- **Q8: After getting the FACES Kit or downloading the factory program of the FACES Kit, the following error is displayed on the screen. What happened?**

    <img src="assets/img/faq/faq_08_01.png" width="100%" height="100%">

    This is normal, because there is no main.py file in the program, so this warning is available.

## UNIT Question

- **Q1: What is the difference between the various cameras of M5Stack?**

    The main difference between these cameras is that some pins (OV2640-SIOD, OV2640-VSYNC, GROVE interface), lens type, and whether or not there is PSRAM. For specific differences, please visit [here](https://shimo.im/sheets/gP96C8YTdyjGgKQC/e2041).

    <img src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/image/m5-docs_table/camera_comparison/camera_comparison_en.png">

- **Q2: The camera transmits images to the mobile phone via WIFI, how far can it be transmitted?**

    After testing, using M5Camera indoors can transmit about 20 meters.

<!-- - **Q2: ESP32 有哪些特殊的 GPIO 管脚需要注意？**

    ESP32 有 34 个 GPIO 管脚，其中 GPIO 34-39 仅用作输入，不能作为输出，其他的既可以作为输入又可以作为输出管脚。 -->