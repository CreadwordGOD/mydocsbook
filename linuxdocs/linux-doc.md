---
description: 如何在linux中使用
---

# linux教程

{% hint style="danger" %}
**使用此软件前** **, 需已查看**[**必备确认**](../faq/errorfaq.md)****
{% endhint %}

{% hint style="info" %}
**请注意! 如果你是linux菜鸟!切勿使用此软件!**
{% endhint %}

## 简介

Linux上推荐使用ShellClash 具有很强的支持性与兼容性, 推荐使用!

项目地址: [ShellClash](https://github.com/juewuy/ShellClash)

### 兼容性

* 支持各种基于OpenWrt或使用OpenWrt二次定制开发的路由器设备
* 支持各种运行标准Linux系统（如Debian/CenOS/Armbian等）的设备
* 兼容Padavan固件（保守模式）、潘多拉固件以及华硕/梅林固件
* 兼容各类使用Linux内核定制开发的各类型设备

## 准备

使用linux, 建议拥有linux基础与网络基础

**运行时的额外依赖**：

大部分的设备/系统都已经预装了以下的大部分依赖，使用时如无影响可以无视之

```bash
bash/ash		必须		#全部缺少时无法安装及运行脚本
curl/wget		必须		#全部缺少时无法在线安装及更新，无法使用节点保存功能
iptables		重要		#缺少时只能使用纯净模式
systemd/rc.common	一般		#全部缺少时只能使用保守模式
iptables-mod-nat	一般		#缺少时无法使用redir模式，混合模式
ip6tables-mod-nat	较低		#缺少时影响redir模式，混合模式对ipv6的支持
crontab			较低		#缺少时无法启用定时任务功能
net-tools		极低		#缺少时无法正常检测端口占用
ubus/iproute-doc	极低		#缺少时无法正常获取本机host地址
```

**本教程以Centos7 进行演示, 其余版本 自行替换命令即可**

```c
yum update -y && yum install wget curl -y
```

## 安装

{% tabs %}
{% tab title="Github直连" %}
```bash
export url='https://raw.githubusercontent.com/juewuy/ShellClash/master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
```
{% endtab %}

{% tab title="JsdelivrCDN源" %}
```bash
export url='https://cdn.jsdelivr.net/gh/juewuy/ShellClash@master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
```
{% endtab %}

{% tab title="wget安装" %}
```bash
export url='https://cdn.jsdelivr.net/gh/juewuy/ShellClash@master' && wget -q --no-check-certificate -O /tmp/install.sh $url/install.sh  && sh /tmp/install.sh && source /etc/profile &> /dev/null
```
{% endtab %}

{% tab title="低版本wget(提示不支持https)" %}
```bash
#Test版本-酱紫表私人http源
export url='http://sc.qust.me/' && wget -q -O /tmp/install.sh $url/install_n.sh  && sh /tmp/install.sh && source /etc/profile &> /dev/null
```
{% endtab %}

{% tab title="非root用户" %}
```bash
#安装后请额外执行以下命令以读取环境变量
source ~/.bashrc &> /dev/null
```
{% endtab %}
{% endtabs %}

安装完成管理脚本后，执行如下命令以**运行管理脚本**

```bash
clash #正常模式运行
clash -h #脚本帮助及说明
clash -u #卸载脚本
clash -t #测试模式运行
```

安装中的设置

![](<../.gitbook/assets/image (32).png>)

## 导入订阅链接

在我们网站内复制你的订阅链接

![](<../.gitbook/assets/image (35).png>)

将你的订阅链接后面加上Clash参数,会请求我们内置的Clash规则

示例: 我的订阅链接**\&flag=clash**

看图

随后启动使用即可

**管理地址如果是内网IP, 请自行替换为公网IP !!!!!!!!**

**别再拿内网IP 问为什么访问不了管理页面!!!!!!!!!!!!! 求你了**&#x20;

![](<../.gitbook/assets/image (36).png>)

![](<../.gitbook/assets/image (37).png>)







