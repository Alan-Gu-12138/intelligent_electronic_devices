# 智能电子设备开发
## 目前需要做的任务
### 网关
对于网关，需要了解esp32与stm32的连接，还要了解lora模块的连接
网关作为中枢，要创建热点。

esp32与wifi连接；lora与节点连接；串口模块可以用来传输数据

#### esp32与wifi连接

1. **硬件连接确认**
根据readme.md，ESP32-S通过**串口2（PA2/PA3）**与STM32主控板通信，确保硬件连接正确。

2. **ESP32-S模块特性**
从您的资料中可以看到，ESP32-S模块支持AT指令集，您可以在`物联网资料\安信可WIFI模块ESP32\`目录下找到相关文档：
- `esp32_at_instruction_set_and_examples_cn.pdf` - AT指令集和示例
- `esp32-s_product_specification_zh.pdf` - 产品规格书

3. **连接WIFI的AT指令流程**
通常ESP32连接WIFI的步骤是：

```
1. 测试模块响应：AT
2. 设置WIFI模式：AT+CWMODE=1  (1=Station模式)
3. 连接WIFI：AT+CWJAP="SSID","密码"
4. 查询连接状态：AT+CWJAP?
5. 获取IP地址：AT+CIFSR
```

4. **STM32程序实现**
您需要在STM32中编写代码：
- 通过串口2发送AT指令给ESP32-S
- 解析ESP32-S返回的响应
- 实现WIFI连接状态检测和重连机制

5. **调试建议**
- 使用串口模块（串口1）输出调试信息，监控WIFI连接状态
- 在中可能有相关的示例代码可以参考

6. **网页创建**
可以通过esp32创建热点，然后建立独立网页用于显示数据
        
### 节点
对于节点来说，需要了解lora模块的连接、传感器数据接收。

### stm32控制lora模块与网关

### stm32接收传感器数据

将数据通过lora发送给网关的lora

## 任务整体描述
我有一个网关，里面主控板为stm32，通过通过串口 2（PA2/PA3）与 WIFI 模块通讯（WIFI模块为esp32）；stm32与lora通过单片机通过 IO 口模拟 IIC 与光照度传感器通讯（模拟 IIC IO 口：SDA—PB10 SCL---PB11）；stm32通过



# intelligent_electronic_devices
