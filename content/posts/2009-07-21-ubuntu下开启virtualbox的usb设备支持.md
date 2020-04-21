---
title: Ubuntu下开启virtualbox的usb设备支持
author: leo_thronton
type: post
date: 2009-07-21T21:38:24+00:00
url: /2009/07/21/ubuntu下开启virtualbox的usb设备支持/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1011')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1011" class="bvMsg">
  <div>
    <p>
      首先到SUN的主页下载Virtualbox。直接用命令apt-get install 安装的版本不支持usb。
    </p>
    
    <p>
      安装好的virtualbox默认也不支持usb设备的，需要手工修改一些设置。
    </p>
    
    <p>
      1.修改为usb设备增加普通用户权限<br /> 1.1 增加一个名为usbfs的用户组<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo groupadd usbfs<br />  
    </p>
    
    <p>
      1.2 增加当前用户到工作组<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo adduser YOURNAME usbfs  //其中YOURNAME是本人系统的登录名字<br />  
    </p>
    
    <p>
      1.3 得到usbfs组的id<br /> 执行如下命令<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> cat /etc/group | grep usbfs<br /> usbfs:x:1002:YOURNAME,root
    </p>
    
    <p>
      其中1002就是usbfs组的id了。
    </p>
    
    <p>
      1.4 修改 /etc/fstab 文件<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo gedit /etc/fstab
    </p>
    
    <p>
      在文件的末尾增加一行<br /> 代码:<br /> none /proc/bus/usb usbfs devgid=1002,devmode=664 0 0
    </p>
    
    <p>
      其中 devgid=1002，其中的1002就是刚才的usbfs的组id
    </p>
    
    <p>
      1.5 为 /proc/bus/usb 增加权限<br /> 首先为/proc/bus/usb放开所有权限，也就是所有人都能访问。<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo chmod 777 /proc/bus/usb<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a>
    </p>
    
    <p>
      然后为/proc/bus/usb设置所有者为当前用户，我的当前用户是YOURNAME。<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo chown YOURNAME /proc/bus/usb<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a>
    </p>
    
    <p>
      1.6 重启电脑<br /> 代码:<br /> <a href="mailto:YOURNAME@YOURNAME-laptop:~$">YOURNAME@YOURNAME-laptop:~$</a> sudo reboot
    </p>
    
    <p>
      修改完必须重启，否则无法生效
    </p>
    
    <p>
      2.配置virtualbox<br /> 在virtualbox的配置明细/usb中，开启usb控制器和usb2.0控制器，然后点击“从设备列表中添加筛选器”<br /> 相关设置会自动的添加到筛选器列表中。
    </p>
  </div>
</div>