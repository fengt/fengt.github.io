---
layout: post
title: mac 添加公司域配置说明
---

> 以下操作，针对mac使用网线转接头成功连接后的配置。

1、打开“系统偏好设置”，点击“用户与群组”，如图：

![an image alt text]({{site.baseurl}}/images/technology/mac01.png "mac01")

2、进入页面后，点击解锁按钮（输入mac用户名和密码），点击“登录选项”，在右侧点击“加入”，如图：

![an image alt text]({{site.baseurl}}/images/technology/mac02.png "mac02")

3、在弹出窗口中，点击“打开目录实用工具”，点击解锁按钮（输入mac用户名和密码），如图：

![an image alt text]({{site.baseurl}}/images/technology/mac03.png "mac03")

4、选择“Active Directory”双击，在Active Directory域中输入域名“rfdoa.cn”，点击绑定，输入网络管理员的用户名和密码，如图：

![an image alt text]({{site.baseurl}}/images/technology/mac04.png "mac04")

![an image alt text]({{site.baseurl}}/images/technology/mac05.png "mac05")

5、上述完成后，打开浏览器访问百度，如果无法访问，需配置一下代理为自动代理，如图：

a、进入“网络”配置窗口，点击“USB以太网”，右侧点击“高级”，如图：

![an image alt text]({{site.baseurl}}/images/technology/mac06.png "mac06")

b、进入子窗口，点击“代理”，选择“自动发现代理”，确认即可，如图：

![an image alt text]({{site.baseurl}}/images/technology/mac07.png "mac07")

c、回到父窗口，点击“应用”即可。