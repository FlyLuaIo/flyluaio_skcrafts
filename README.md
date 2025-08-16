# Quickmadedevice

Quickmadedevice 是用于 X-Plane 11/12 的 USB 设备处理插件。它具有出色的可扩展性，可以自行添加更多飞机。

其内置的 Lua 语言引擎对于编程初学者来说也很容易上手。

https://x-plane.vip/quickmade/

支持 X-Plane 11/12/MSFS2020/2024。

https://www.quickmadesim.com/?page_id=194&lang=en

# 功能特性

*   零帧率（FPS）影响
*   操纵杆按键自动分配（手动分配数百个按键非常痛苦）
*   旋转编码器加速
*   内置 Lua 语言引擎
*   易于调试：无需重启 X-Plane 即可即时重新加载 Lua 文件
*   飞机冷舱（cold and dark）同步
*   飞机模拟故障同步
*   支持 Win/Lin/Mac
*   原生支持 Apple ARM 芯片

## 游戏兼容性列表 ##

https://docs.qq.com/sheet/DWERFQnRmVUFZeHBi?tab=00...

## 下载

https://github.com/cpuwolf/Quickmadedevice/releases

## 提供安装程序

![qmdev](img/qmdevinstaller.gif)

## 更多 Lua 开发者文档

https://github.com/cpuwolf/Quickmadedevice/wiki

## 截图 ##
<img width="354" alt="截屏2023-10-30 08 16 39" src="https://github.com/cpuwolf/Quickmadedevice/assets/1320329/d13b6540-eba4-422a-98b9-1ef75fbf7c59">

![qmdev](img/qmdev_setup.jpg)
![qmdev](img/nocost.jpg)

### 在 Linux/MacOS 上安装 ###

#### 在 MacOS 上安装 ####
1.  从 (https://www.java.com/en/download/) 下载并安装 Java。
2.  从终端执行以下命令：
    ```
    java -jar Qmdev_Setup.jar
    cd <...>/X-Plane 12/Resources/plugins/qmdev
    xattr -dr com.apple.quarantine *
    ```

#### 在 Ubuntu 18.04 上安装 ####
```
sudo apt install openjdk-11-jre
java -jar Qmdev_Setup.jar
```

#### Linux 手动配置 ####

编辑 hidraw 设备访问权限

sudo vim /etc/udev/rules.d/99-joysticks.rules

KERNEL=="event*", NAME="input/%k", MODE="0666", GROUP="input"

KERNEL=="hidraw*", SUBSYSTEM=="hidraw", MODE="0666", GROUP="input"

#### Linux 内核贡献 ####
修复 Linux 内核操纵杆按钮最大数量限制

https://patchwork.kernel.org/patch/11657985/

## 版本信息 ##
### V2.0 ###
进一步优化性能
在 .cfg 中添加新关键字 DFKEY
添加 disfast 数据引用以暂时禁用快速按键
添加 QCDU, QG1K 设备

### V5.0 ###
移除对 FlyWithLua 的依赖，因为 Flywithlua 会影响帧率，不符合预期
引入内置 ulua

### V6.0 ###
原生支持 MacOS M1
移除所有 .cfg 文件，并将内容添加到 Lua 中

### V6.1 ###
读取 Lua 文件时添加弹出窗口

### V6.3 ###

此更新需要您更新 QFCU 固件
https://www.quickmadesim.com/?page_id=658&lang=en

核心更改：

*   Qmdev 核心修复了读取错误数据引用值的 Bug
*   更新 X-Plane SDK 4.0.1
*   修复了一个 USB 日志错误

Lua 脚本更改：

*   添加 QFCU 默认 XP12 A333 支持

*   更新 Toliss Airbus XP12 QFCU 亮度控制更改
*   更新 Toliss Airbus XP12 QFCU 开/关机逻辑
*   更新 Toliss Airbus XP12 QCDU 开/关机逻辑
*   更新 IXEG B737 classic plus XP12 QMCP737 A/T LED 灯
*   更新 IXEG B737 classic plus XP12 QCDU EXEC 灯

*   更新 ZIBO B737 XP12 QCDU EXEC 灯
*   更新 Flightfactor B757 XP12 QCDU EXEC/MSG 灯
*   更新 Flightfactor B757 XP12 QMCP737C IAS/MACH 逻辑
*   更新 Flightfactor A320 XP12 QFCU 开/关机逻辑
*   更新 Flightfactor A320 XP12 QCDU 开/关机逻辑

*   修复 Toliss Airbus XP12 QFCU SPD/HDG 预选功能
*   修复 Toliss Airbus XP12 QFCU EFIS Baro 偏差
*   修复 Flightfactor A320 XP12 QFCU SPD/HDG 预选功能
*   修复 JarDesign Airbus QFCU HDG/ALT/BARO 旋转功能

## 开发者文档 ##

如何编写自己的 .lua 脚本文件

https://github.com/cpuwolf/Quickmadedevice/wiki/Qmdev-.lua-files
