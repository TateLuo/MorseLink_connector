# MorseLink Connector

![MorseLink Connector 完成图 / Completed Device](completed.png)

> 将摩尔斯电键连接到 Windows 电脑的开源硬件连接器。  
> An open-hardware connector for using a Morse key with a Windows PC.

---

## 中文说明

### 项目简介

MorseLink Connector 用于把传统摩尔斯电键转换为可通过 USB 与电脑交互的输入设备。  
本仓库提供了复刻硬件所需的关键文件：原理图、PCB 源文件、制板打样包以及固件镜像。

配套上位机软件（用于按键配置与使用）：  
**MorseLink**: <https://github.com/TateLuo/MorseLink>

### 仓库文件

| 文件 | 说明 |
|---|---|
| `PCB.pcbdoc` | PCB 设计源文件（Altium Designer） |
| `schematic diagram.schdoc` | 原理图源文件（Altium Designer） |
| `JLC_board_making.zip` | 嘉立创打样所需制造文件（Gerber/Drill/Flying Probe） |
| `MorseLink_firmware.hex` | 固件烧录文件 |
| `completed.png` | 成品图片 |
| `LICENSE` | Apache-2.0 许可证 |

### 快速开始

#### 1) PCB 打样

1. 访问 <https://jlcpcb.com/>。
2. 打开 **Instant Quote / 即时报价**。
3. 上传仓库中的 `JLC_board_making.zip` 直接下单。

> 仓库内的 `JLC_board_making.zip` 已包含生产文件，且压缩包中附有 `PCB下单必读.txt`。

#### 2) 采购与焊接

1. 根据 `schematic diagram.schdoc` 与 `PCB.pcbdoc` 整理 BOM。
2. 采购元件并完成焊接。
3. 焊后建议重点检查：
   - 供电与地是否短路；
   - USB-C 相关焊点完整性；
   - 关键器件方向与极性。

#### 3) 固件烧录

1. 安装 WCHISPTool：<https://www.wch-ic.com/downloads/WCHISPTool_Setup_exe.html>
2. 使用可传输数据的 USB-C 线连接设备与 Windows 电脑。
3. 在工具中选择 `MorseLink_firmware.hex`。
4. 保持默认配置，点击烧录。

#### 4) 上位机配置

1. 下载并运行 MorseLink：<https://github.com/TateLuo/MorseLink>
2. 识别设备并完成参数配置。
3. 接入摩尔斯电键进行测试。

### 兼容性

- 推荐系统：**Windows**（烧录与使用流程基于 Windows 工具链）。
- 接口：USB-C（连接电脑）+ 电键输入接口（连接摩尔斯电键）。

### 常见问题（FAQ）

**Q1：打样平台提示文件异常？**  
A：请优先使用仓库原始 `JLC_board_making.zip`，避免“解压后重压缩”导致层文件变化。

**Q2：烧录失败？**  
A：先排查 USB-C 线是否仅供电；再检查驱动识别、端口状态及 `hex` 文件选择是否正确。

**Q3：上位机识别不到设备？**  
A：确认烧录成功后，再检查 USB 接口焊接质量与设备管理器中的识别状态。

---

## English

### Overview

MorseLink Connector is an open-hardware bridge that enables a traditional Morse key to work with a Windows PC via USB.

This repository includes the essential files for reproduction:
- schematic source,
- PCB source,
- manufacturing package,
- firmware image.

Companion software:
**MorseLink**: <https://github.com/TateLuo/MorseLink>

### Repository Contents

| File | Description |
|---|---|
| `PCB.pcbdoc` | PCB source file (Altium Designer) |
| `schematic diagram.schdoc` | Schematic source file (Altium Designer) |
| `JLC_board_making.zip` | Manufacturing package for JLCPCB (Gerber/Drill/Flying Probe) |
| `MorseLink_firmware.hex` | Firmware image for flashing |
| `completed.png` | Finished hardware photo |
| `LICENSE` | Apache-2.0 license |

### Quick Start

1. **Order PCB** on JLCPCB by uploading `JLC_board_making.zip`.
2. **Assemble hardware** according to schematic/PCB design.
3. **Flash firmware** with WCHISPTool and `MorseLink_firmware.hex`.
4. **Configure in MorseLink software** and test your key input.

WCHISPTool download:  
<https://www.wch-ic.com/downloads/WCHISPTool_Setup_exe.html>

### Compatibility

- OS: Windows recommended.
- Interface: USB-C to PC.

---

## License

Licensed under **Apache License 2.0**. See `LICENSE` for details.
