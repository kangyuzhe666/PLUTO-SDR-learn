

# PLUTO-SDR入门记录（二）

PLUTO支持多个软件平台，目前在windows上比较常用的是sdr#(sdr sharp)、matlab，linux平台主要有GNU Radio等。但是安装的时候要注意，这3款软件直接安装是不能使用的，要在软件的基础上安装支持PLUTO的插件才能使用。

## 1、windows下sdr#的安装与使用

sdr#的下载链接：https://airspy.com/download/

支持PLUTO插件的下载链接：https://github.com/Manawyrm/sdrsharp-plutosdr/releases/tag/v0.5.4

sdr#是免安装版，因此将插件解压到的文件合并到sdr#中即可，在FrontEnd.xml中添加PLUTO索引。

![image-20200905100341849](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905100341849.png)

```
<add key="PlutoSDR" value="SDRSharp.PlutoSDR.PlutoSDRIO,SDRSharp.PlutoSDR" />
```

打开SDRSharp.exe

![image-20200905100505004](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905100505004.png)

将数据电缆插入电脑，同时最好在Rx端安装一个接收FM频段的拉杆天线

![image-20200905100835591](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905100835591.png)

选择信号源为PlutoSDR，在设置中根据自己的需求调节增益，选自WFM收听FM广播。如果你所在的位置信号较好即可收听到当地的FM

![IMG_7257](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/IMG_7257.JPG)

## 2、windows下matlab安装与PLUTO插件的安装

​        matlab的强大功能自然不必多说，上面安装的sdr#只能进行收音类似与收音机功能。不能进行信号的分析和自定义信号的发射，而PLUTO不单单是一个sdr接收机更大的一个功能是它可以进行信号的发射因此学习使用matlab是很必要的。

​        我们这里安装的是matlab2018b版本，这个版本对PLUTO插件有比较好的兼容性其他版本请谨慎安装。

![image-20200905102052823](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102052823.png)



![image-20200905102024005](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102024005.png)

安装好PLUTO插件后可以在附加功能->管理附加功能中连接PLUTO

![image-20200905102252706](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102252706.png)

![image-20200905102327724](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102327724.png)

注意不要勾选更新固件

![image-20200905102505313](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102505313.png)

![image-20200905102532031](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102532031.png)

一直next到打开例程

![image-20200905102640312](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102640312.png)

测试一下收音机功能

![image-20200905102743894](https://picture-1253612317.cos.ap-nanjing.myqcloud.com/img/image-20200905102743894.png)

输入持续100s收音，设备为PLUTO，接收频率为101.6MHz即可收到音频。当然接收频率根据当地FM电台确定，你可以自己随意更改。

<u>**注意**</u>

<u>PLUTO搭载的AD9363默认的收发频率为325 MHz至3.8 GHz，理论上是不能收发FM频段，可以通过官方提高的指令在PLUTO终端中破解为AD9364，收发频率扩大到70MHz~6GHz覆盖FM频段。这个自行百度搜索破解这里不赘述</u>





