# DFRobot_Sensor
这是一个虚拟的传感器，IIC地址不可改变,不对应任何实物，可以通过IIC和SPI口来控制它，假设它有下面这些功能
 * 向寄存器0里写入数据，点亮不同颜色的LED灯
 * 从寄存器1里读出数据，高四位表示光线强度，低四位表示声音强度
 * 从寄存器2 bit0里写入数据，写1表示正常模式，写0表示低功耗模式
 * 从寄存器3 读取数据，读到的是芯片版本0xDF

这里需要显示拍照图片，可以一张图片，可以多张图片（不要用SVG图）

![正反面svg效果图](https://github.com/fary99/DFRobot_Sensor/blob/master/resources/images/SEN0245svg1.png)


## 产品链接（链接到英文商城）
    SKU：产品名称

## Table of Contents

* [Summary](#summary)
* [Installation](#installation)
* [Methods](#methods)
* [Compatibility](#compatibility)
* [History](#history)
* [Credits](#credits)

## Summary

这里填写当前Arduino软件库完成了基础功能，特色功能

## Installation

To use this library, first download the library file, paste it into the \Arduino\libraries directory, then open the examples folder and run the demo in the folder.

## Methods

```C++
  /**
   * @brief 初始化函数
   * @return 返回0表示初始化成功，返回其他值表示初始化失败
   */
  int begin(void);
  
  /**
   * @brief 获取声音强度值
   * @return 返回声音强度，单位是DB
   */
  uint16_t getSoundStrength(void);

  /**
   * @brief 获取光线强度值
   * @return 返回光线强度，单位是流明
   */
  uint16_t getLightStrength(void);
  
    /**
   * @brief 切换模式
   * @return 返回0操作成功, 返回其他值操作失败
   */

  uint8_t switchMode(uint8_t mode);
  /**
   * @brief 设置LED灯的颜色
     @note  设置颜色后，0.2秒后生效
   * @param r 红色通道颜色值，范围0-255
   * @param g 绿色通道颜色值，范围0-255
   * @param b 蓝色通道颜色值，范围0-255
   */
   void setLED(uint8_t r, uint8_t g, uint8_t b);

   /**
   * @brief 设置LED灯的颜色
     @note  设置颜色后，0.2秒后生效
   * @param color rgb565格式的颜色值
   */
   void setLED(uint16_t color);
```

## Compatibility

| MCU           | Work Well | Work Wrong | Untested | Remarks |
| ------------- | :-------: | :--------: | :------: | ------- |
| Arduino uno   |           |            |          |         |
| Mega2560      |           |            |          |         |
| Leonardo      |           |            |          |         |
| mPython/ESP32 |           |            |          |         |
| micro:bit     |           |            |          |         |


## History

- data 2020-11-20
- version V0.1


## Credits

Written by Alexander(fary_young@dfrobot.com), 2020. (Welcome to our [website](https://www.dfrobot.com/))