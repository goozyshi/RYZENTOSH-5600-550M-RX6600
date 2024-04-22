# RYZENTOSH-5600-550M-RX6600

👏 **AMD YES** ！基于 OpenCore0.98 的 Ryzen 5600 + Asus B550M-plus + Rx6600 安装的黑苹果，主要用来敲代码，刚需功能已完善，欢迎 star 完善。

## 💻 设备信息

<br>

[![OpenCore](https://img.shields.io/badge/OpenCore-0.9.8-lightblue.svg)](https://github.com/acidanthera/OpenCorePkg) [![macOS](https://img.shields.io/badge/macOS-13.5.2-F09337.svg)](https://www.apple.com/macos/ventura)

</br>

| **设备**     | **型号**                                                     |
| ------------ | ------------------------------------------------------------ |
| **CPU**      | 3,5 GHz AMD Ryzen 5 5600 6-Core Processor                    |
| **显卡**     | 撼讯 AMD Radeon RX 6600 8 GB                                 |
| **内存**     | 16GB KingBank DDR4 2666MHZ                                   |
| **主板**     | [ASUS TUF GAMING B550M-PLUS](https://www.asus.com.cn/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b550m-plus/) |
| **SSD**      | ZHITAI Ti600 1TB                                             |                                                          |
| **Ethernet** | Realtek RTL8125 2.5GbE Controller （主板自带）               |
| **Audio**    | Realtek ALCS1200A (**layout-id=11**， 其他型需要更改layout-id或者 启动项的 alcid，可以查询[AppleALC-Supported codecs](https://github.com/acidanthera/applealc/wiki/supported-codecs)) |

## ✅ 功能

-  CPU power management
-  Graphics acceleration
-  Ethernet
-  Keyboard & Mouse
-  USB ports
-  HDMI video & audio output.
-  iCloud & App Store & iMessage

## ❌ 问题

-  **Wi-Fi/Bluetooth**： 之前买了个 **Fenvi FV-HB1200** ，WIFI免驱，隔空投送、蓝牙需要驱动，实测 **WIFI 可以正常运行但蓝牙经常断连**，基本1分钟左右自动断开，**体验极差**，因为我的需求只是连接我的 JBL 音箱 放个响，后面直接买个有线耳机搞定了。

​	![](./static/fenvi.png)

-  airDrop： 没有蓝牙所以没有隔空投送

-  microphone： 麦克风

## 🎉一些优化

### 性能监控-英语

- CPU 监控：[AMD POWER GADGET App](https://github.com/trulyspinach/SMCAMDProcessor) ⚠️ 需要**搭配 SMCAMDProcessor.kext** 使用
- 显示器亮度调节 🔅：[MonitorControl App](https://github.com/MonitorControl/MonitorControl)

![](./static/amd-power-gadget.png)

###   RX6600 显卡仿冒

获取**Device Path**:

![](./static/pcie.png)

```xml
<key>这里写你显卡的实际的设备路径(Hackintool PCIE里面可以看到)</key>
  <dict>
    <key>@0,name</key>
    <string>ATY,Henbury</string>
    <key>@1,name</key>
    <string>ATY,Henbury</string>
    <key>@2,name</key>
    <string>ATY,Henbury</string>
    <key>@3,name</key>
    <string>ATY,Henbury</string>
    <key>ATY,DeviceName</key>
    <string>W6600X</string>
    <key>ATY,EFIVersion</key>
    <string>01.01.270</string>
    <key>ATY,FamilyName</key>
    <string>Radeon Pro</string>
    <key>device_type</key>
    <string>ATY,HenburyParent</string>
    <key>model</key>
    <string>AMD Radeon RRO W6600X</string>
    <key>name</key>
    <string>ATY,Henbury</string>
  </dict>
```

在 OpenCore Configurator 应该是这样的：

![](./static/pcie-occ.png)

## 致谢

- 镜像来源：[黑果小兵的部落阁](https://blog.daliansky.net/macOS-Monterey-12.5.1-21G83-Release-version-with-OC-0.8.4-CLOVER-5148-and-FirPE-original-image.html)
- 教程入门：[国光的黑苹果安装教程：手把手教你配置 OpenCore](https://github.com/sqlsec/Hackintosh/tree/main)
