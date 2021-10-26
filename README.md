IPv6攻击检测工具
=============================

## 描述
6Guard旨在检测覆盖[the THC-IPv6 suit](http://thc.org/thc-ipv6/)规范的安全攻击检测工具。可进行IPv6安全攻击实验检测及安全防护，也可帮助网络管理员有效检测常见的IPv6攻击。

本工具基于[mzweilin/IPv6-Attack-Detector](https://github.com/mzweilin/IPv6-Attack-Detector)进行开发，并修复一些因依赖包版本兼容及程序逻辑问题。

攻击检测样例输出：
```
    [ATTACK]
    Timestamp: 2012-08-19 14:48:27
    Reported by: Honeypot-apple-2A:C4:2D
    Type: DoS
    Name: Fake Echo Request
    Attacker: [Unknown]  00:00:de:ad:be:ef (CETIA)
    Victim  : [Honeypot-apple-2A:C4:2D]  40:3C:FC:2A:C4:2D (Apple, Inc.)
    Utility: THC-IPv6: smurf6
    Packets: b12fe3415c1d61c1da085cb8811974a2.pcap
```

## 安装
### Ubuntu环境
1. 安装Scapy依赖：`sudo apt-get install python-scapy`
2. 安装tcpdump工具 `sudo apt-get install tcpdump`
3. 下载ipv6-attack-detector并解压.


## 使用
1. 进入 6Guard 目录.
2. 运行: `$ sudo ./conf_generator.py` 生成配置文件-（*备注: 若conf/Honeypot-XX.ini文件中未识别到MAC地址，请手动输入指定网卡或Interface的MAC地址*）
3. 运行: `$ sudo ./6guadrd.py`进行检测


**说明**
* 第一次运行 6guard, 将提醒您选择 genuine Router Advertisement 消息.
* 攻击告警消息将被实时打印到输出窗口.
* 攻击消息也将记录到'./log/'输出文件中.
* 攻击源数据文件将记录到./pcap/目录下的.pcap文件中.
