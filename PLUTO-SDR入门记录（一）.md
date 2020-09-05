# PLUTO-SDR入门记录（一）

开箱配件包括主机、数据线、两个824 MHz~894MHz/1710 MHz~2170 MHz天线、一个回环馈线。

PLUTO-SDR由亚德诺半导体出品，整体设计方案是AD9363射频收发器+ZYNQ7010FPGA。AD9363的收发频率为325 MHz至3.8 GHz，支持时分双工(TDD)和频分双工(FDD)工作模式，AD/DA为12bit性能优于Hackrf。

![IMG_7239](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/IMG_7239.JPG)

## 1、首先测试一下收到设备的完好性

在windows环境下通过micro usb数据线连接电脑和PLUTO，此时PLUTO会被识别为一个大容量设备，正常情况下PLUTO的LED1灯闪烁，Ready灯常亮。此时通过浏览器打开info.html查看使用说明。

![image-20200904195058524](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/EmDHLQS7Fzqd4av.png)

![image-20200904195210111](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/gMyPdHo63jRBrt7.png)

第一步更新固件可以先跳过，等设备测试完好再更新。先下载windows下的驱动和libiio库进行安装，安装完成后才终端中输入

```
iio_info -s
```

查看设备情况，PLUTO用虚拟网卡功能默认地址为192.168.2.1在许多第三方SDR软件中会采用该IP连接设备

![image-20200904195457490](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/gMyPdHo63jRBrt7.png)

下面列出了PLUTO支持的软件平台

![image-20200904195655620](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/Xdc8UNvz4jPARSx.png)

我们先下载安装IIO Oscilloscope进行硬件完好性的测试，点击usb设备，刷新出设备后点击确定进行连接。

![image-20200904195809748](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/Xdc8UNvz4jPARSx.png)

勾选两个voltage,并开始运行，看到如下表示设备功能完好。

![image-20200904200014942](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/NEpeGjsl9T7tziP.png)

同时我们可以尝试接收一下940Mhz左右的GSM信号，先把天线安装好，设置接收频率945Mhz增益43dB

![image-20200904200645968](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/yFiOcn9bZI6C3lQ.png)

接收效果如下，至此开箱测试工作完成。

![image-20200904203934789](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200904203934789.png)


