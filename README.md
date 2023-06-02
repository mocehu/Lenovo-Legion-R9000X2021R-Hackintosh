# Lenovo-Legion-R9000X2021R-Hackintosh
## 联想拯救者R9000X2021R机型黑苹果EFI配置文件说明

### 本机硬件使用情况

| 硬件名称     | 具体型号                                      | 可用情况                                    |
| ------------ | --------------------------------------------- | ------------------------------------------- |
| CPU          | R7-5800H                                      | 可用                                        |
| 独立显卡     | Nvidia RTX 3060 Laptop                        | 不可用                                      |
| 核显         | AMD Radeon Vega 8                             | 可用，但本机型核显大小锁死512MB无法修改     |
| 网卡         | AX210                                         | 可用 ，原装MTK网卡不可用                    |
| 蓝牙         | AX210                                         | 可用，隔空投送等功能不支持                  |
| 硬盘         | SKHynix_HFS512GDE9X084N+Samsung SSD 980 500GB | 三星980可用，原装海力士不可用，详见硬盘屏蔽 |
| 键盘、触控板 |                                               | 可用                                        |
| 声卡/音频    | Realtek High Definition Audio                 | 本机扬声器和麦克风不可用，外接耳机可用      |
| 内存         | 海力士8G+美光32G                              | 可用                                        |
| USB、摄像头  | 本机型无需禁用XCHI控制器                      | 可用，本机型无需禁用XCHI控制器              |
| 电池         | SMP 71.0Wh                                    | 无法识别                                    |
| 屏幕         | 京东方 2560*1440 165hz                        | 无法调整亮度，系统只支持60hz                |

### 注意事项

在提供的Bigsur和Monterey两个EFI文件中选择对应系统版本所需的EFI并将内容覆盖即可

提供的文件中均删除设备序列号等信息，请使用OC编辑器自动生成

本文件中默认开启核显，请在**安装**和**升级**MacOS前请在config.plist中**禁用nootedred.kext（核显驱动）**，安装完成后再开启！

本EFI中内置固态屏蔽文件SSDT-SSDHIDE-DISABLE.aml，在EFI->OC->ACPI->SSDT-SSDHIDE-DISABLE.aml中，首次安装请在config.plist中**禁用SSDT-SSDHIDE-DISABLE.aml**，安装完成后根据机器的实际情况机型修改后使用，详见下面的固态屏蔽说明

本机型强烈建议安装Bigsur系统，Monterey卡顿非常频繁不建议使用！

### 小白从零开始参考资料

国光黑苹果教程👍👍👍: https://apple.sqlsec.com/
隔壁机型的1: https://github.com/zabdottler/Lenovo-Yoga-16S-hackintosh
隔壁机型的2: https://shenhai.cool/d/428
硬盘屏蔽参考: https://heipg.cn/tutorial/block-nv-dgpu-or-pm981.html#%E4%BF%AE%E6%94%B9%E9%A2%84%E7%BC%96%E8%AF%91%E7%9A%84-SSDT

### 硬盘屏蔽说明

如果你的机器上没有不支持的固态比如PM981，PM981A，SKHynix_HFS512GDE9X084N等，直接跳过此步，并在config.plist中删除或者禁用SSDT-SSDHIDE-DISABLE.aml

如果有不支持的固态，请在安装MacOS前在Windows的设备管理器中查看设备路径，如图所示，如果你的刚好和我一样，那么可用直接用我的文件无需任何更改，如果不一样，那就需要拆掉硬盘，安装MacOS后在MacOS中修改SSDT-SSDHIDE-DISABLE.aml文件，或者把你的路径发给一个有MacOS的人帮你修改后再使用，修改的工具在上面给出的参考链接中有提供，最好提前下载好放到u盘等位置后直接安装。

![](https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/HideSSD.png?raw=true)
![]([https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/HideSSD.png?raw=true](https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/%E8%AE%BE%E5%A4%87%E7%AE%A1%E7%90%86%E5%99%A8%E6%9F%A5%E7%9C%8B%E8%B7%AF%E5%BE%84.png?raw=true))


## 截图

![](https://raw.githubusercontent.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/main/image/bigsur-2.png)

![](https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/Bigsur-1.png?raw=true)

![](https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/Monterey-info2.png?raw=true)

![](https://github.com/mocehu/Lenovo-Legion-R9000X2021R-Hackintosh/blob/main/image/Montery-info1.png?raw=true)
