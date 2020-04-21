---
title: '[转]Windows XP系统下建立VPN服务器(图)'
author: leo_thronton
type: post
date: 2009-05-19T15:13:27+00:00
url: /2009/05/19/转windows-xp系统下建立vpn服务器图/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!990')?authkey=yuBuArwciRo%24"
categories:
  - 计算机与 Internet

---
<div id="msgcns!8F6A31FABB4CD362!990" class="bvMsg">
  <div>
    <div>
      <span>首先服务里面：<br /> windows自带防火墙 （windows firewall/internet connection sharing(ICS)）要停止（或允许1723端口）<br /> 远程注册表服务(remote Registry) 必需开启<br /> server服务(Server)必需开启<br /> router路由服务(Routing and Remote Access)必需开启</span>
    </div>
    
    <div>
      <span><br /> 建立VPN：在计算机管理——>服务里，将Routing and Remote Access这项服务启用并设成自动启动，（将本机的防火墙先关闭）系统默认是禁用的，启用后，在网上邻居里，会出现在一个传入连接<br /> 双击这个传入连接。在常规里</span> </p> 
      
      <div>
        <span><img src="http://farm4.static.flickr.com/3408/3542525289_f824bce143.jpg" border="0" /></span>
      </div>
      
      <p>
        <span>，好，这样一个VPN已经架设好了，下面我们来建立一个VPN的拨号。<br /> 输入用户名，也就是刚刚传入连接的里的，USER，下面我所选的用户名qiyue。也就是你本机的用户名和密码。好，输入用户名和密码拨号。好拨号成功了，我们再来看看能不能正常打开网页，好，一个网页也打不开。为什么？这是因为我们还没有在本机路由表里添加路由。<br /> 本机IP地址为192.168.0.9,</span><span><br /> 只能访问192.168.0.9,所以我们要通过route add 添加一个静态的路由表<br /> 添加一个我们VPN所要访问的网段，比如，ping <font color="#0066a7">www.163.com</font>,得到IP地址：220.181.28.53<br /> 再用route add 220.181.28.0 mask 255.255.255.0 125.124.142.238，这163这个IP段都添加进去，所以我们只可以打开和163在同一网段的网站，<br /> 现在你拨的VPN就可以访问163了哦，要想访问其他的网站或上QQ，自己添加路由表。<br />     对方如果已接入了宽带的，我们在VPN设置的时候记得要把TCP/IP属性制定为内网的地址，在允许呼叫方访问我的局域网打钩，允许呼叫的计算机指定其IP地址也打钩。</span></div> 
        
        <div>
          <span><br /> 访问方</span>
        </div>
        
        <div>
          <p>
            <span><br /> 网上邻居 &#8212; 属性，创建一个新的连接——连接到我工作场所的网络——虚拟专用网络连接——公司名（随便）——主机名或IP地址（我这里用的是DNS动态域名，july01.3322.org）然后一路完成。输入用户名和密码进入。</span>
          </p>
          
          <p>
            <span>关于访问方连上VPN后宽带连接会自动断掉，那是要去在VPN连接上点属性，把默认网关前面的勾去掉。</span>
          </p>
          
          <p>
            <span><img src="http://farm4.static.flickr.com/3317/3542524999_91335c7e83.jpg" border="0" /></span>
          </p></p>
        </div></div> 
        
        <p>
          <ins><ins></ins></ins></div>