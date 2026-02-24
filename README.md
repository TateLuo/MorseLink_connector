# MorseLink Connector

<div align="center">

## 🌐 Select Language / 选择语言
### 🇨🇳 [中文说明](#中文说明)
### en [English](#english)

</div>

---
![MorseLink Connector Completed Device](completed.png)
> 将传统摩尔斯电键转换为 USB 输入设备的开源硬件方案。  
> An open-hardware USB bridge for connecting a Morse key to a Windows PC.

---

## 中文说明

### 项目定位

MorseLink Connector 是一个开源 USB 接口板，用于将传统机械摩尔斯电键转换为可被 Windows 识别的输入设备。

该项目属于 MorseLink 生态系统的一部分，负责硬件层的信号采集与 USB 通信。

配套上位机软件：  
**MorseLink**  
https://github.com/TateLuo/MorseLink

---

### 项目特性

- USB-C 接口设计  
- 低延迟按键采样  
- 完整开源硬件设计文件  
- 支持 JLCPCB 直接打样  
- 提供可烧录固件镜像  

---

### 仓库文件

| 文件 | 说明 |
|---|---|
| `PCB.pcbdoc` | PCB 设计源文件（Altium Designer） |
| `schematic diagram.schdoc` | 原理图源文件（Altium Designer） |
| `JLC_board_making.zip` | 嘉立创打样制造文件（Gerber/Drill/Flying Probe） |
| `MorseLink_firmware.hex` | 固件烧录文件 |
| `completed.png` | 成品图片 |
| `LICENSE` | Apache-2.0 许可证 |

---

### 快速开始

#### 1) PCB 打样

1. 访问 https://jlcpcb.com/
2. 打开 **Instant Quote / 即时报价**
3. 上传仓库中的 `JLC_board_making.zip` 直接下单

> 注意：请勿解压后重新压缩，以避免制造文件层信息异常。

---

#### 2) 采购与焊接

1. 根据 `schematic diagram.schdoc` 与 `PCB.pcbdoc` 整理 BOM
2. 采购元件并完成焊接
3. 焊后重点检查：
   - 电源与地是否短路
   - USB-C 焊点完整性
   - MCU 与关键器件方向是否正确

---

#### 3) 固件烧录

1. 下载 WCHISPTool  
   https://www.wch-ic.com/downloads/WCHISPTool_Setup_exe.html
2. 使用可传输数据的 USB-C 线连接设备
3. 选择 `MorseLink_firmware.hex`
4. 保持默认设置并烧录

---

#### 4) 上位机配置

1. 下载并运行 MorseLink  
   https://github.com/TateLuo/MorseLink
2. 识别设备并完成参数配置
3. 接入摩尔斯电键进行测试

---

### 兼容性

- 推荐系统：Windows
- 接口：USB-C（连接电脑）+ 电键输入接口

---

### 常见问题（FAQ）

**Q1：打样平台提示文件异常？**  
A：请使用仓库原始 `JLC_board_making.zip`，避免重新压缩。

**Q2：烧录失败？**  
A：优先排查 USB-C 线是否支持数据传输，并检查驱动与端口识别状态。

**Q3：软件无法识别设备？**  
A：确认烧录成功后检查 USB 焊接质量及设备管理器状态。

---

## English

### Overview

MorseLink Connector is an open-hardware USB interface board designed to convert a traditional mechanical Morse key into a USB input device recognized by a computer.

It functions as a standard USB HID input device. In theory, it can work with any Morse training software that supports keyboard or mouse-based keying input.

Companion software (optional):
https://github.com/TateLuo/MorseLink

---

### Features

- USB-C interface
- Low-latency key input
- Standard USB HID device behavior
- Fully open-source schematic and PCB files
- Direct manufacturing support via JLCPCB
- Prebuilt firmware image included

---

### Repository Contents

| File | Description |
|------|------------|
| `PCB.pcbdoc` | PCB source file (Altium Designer) |
| `schematic diagram.schdoc` | Schematic source file |
| `JLC_board_making.zip` | Manufacturing package (Gerber/Drill/Flying Probe) |
| `MorseLink_firmware.hex` | Firmware image for flashing |
| `completed.png` | Finished hardware photo |
| `LICENSE` | Apache-2.0 license |

---

### Quick Start

#### 1) Order the PCB

1. Visit https://jlcpcb.com/
2. Open **Instant Quote**
3. Upload the `JLC_board_making.zip` file directly

> Important: Upload the original ZIP file from the repository.  
> Do not unzip and recompress it, as this may cause manufacturing file recognition issues.

---

#### 2) Assembly

1. Generate a BOM using `schematic diagram.schdoc` and `PCB.pcbdoc`
2. Purchase the required components
3. Assemble and solder all parts
4. After soldering, verify:
   - No short circuit between power and ground
   - Proper USB-C solder joints
   - Correct orientation of MCU and polarized components

---

#### 3) Flash Firmware

1. Download WCHISPTool:  
   https://www.wch-ic.com/downloads/WCHISPTool_Setup_exe.html
2. Connect the board to a Windows PC using a data-capable USB-C cable
3. Open WCHISPTool and select `MorseLink_firmware.hex`
4. Keep default settings and start flashing

---

#### 4) Configure and Test

1. Download and run MorseLink (optional):  
   https://github.com/TateLuo/MorseLink
2. Confirm that the device is recognized by the system
3. Configure parameters if required
4. Connect your Morse key and test key input

---

### Compatibility

- OS: Windows recommended
- Interface: USB-C
- Device Type: Standard USB HID input device

---

## License

Licensed under the **Apache License 2.0**.  
See the `LICENSE` file for details.
