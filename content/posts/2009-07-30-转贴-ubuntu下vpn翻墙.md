---
title: '[转贴] Ubuntu下VPN翻墙'
author: leo_thronton
type: post
date: 2009-07-30T16:30:05+00:00
url: /2009/07/30/转贴-ubuntu下vpn翻墙/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1020')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1020" class="bvMsg">
  一直一来及埃夫达不溜真是让人头疼，把偶经常光顾的网站都封的差不多了，试了不少“梯子”，都没有成功，无奈之下一直用代理网站，不过今天终于找到了一较完美的<span>解决</span>方法，拿出来分享一下<font>9 J; S4 g2 Z/ W8 m( q. t</font><br /> 在众多的梯子中，VPN和SSH无疑是效率最高的。Linkideo提供的VPN不再免费后，UltraVPN无疑是一个很好的替代品。<br /> <span style="display:none;">3 D, G& p7 W$ ]. s</span>UltraVPN提供的VPN<span>服务</span>基于开源的OpenVPN，网站为<span>Windows</span>和Mac编译好了安装包，我们只需在<a href="http://ultravpn.fr/" target="_blank" rel="noopener noreferrer">UltraVPN的网站</a>上注册一个帐号，安装好<span>下载</span>来的程序，无需设置，马上可以享受穿墙而过的快感。但是ultravpn并没有为linux<span>用户</span>提供这样的方便，linux需要自己下载OpenVPN的源码编译安装。不过Ubuntu的用户不用那么麻烦，搞掂UltraVPN只需如下几步：<font>7 K# H- t2 F0 S8 V5 [% k</font><br /> 1. 注册帐号。<font>&#8216; @0 _% S6 X3 &#125;; R; j&#8217; M9 q" e&#8217; n/ h</font><br /> 到<a href="http://ultravpn.fr/account.htm" target="_blank" rel="noopener noreferrer">这里</a>输入帐号、<span>密码</span>，帐号立马到手。邮箱是可选项，用于找回密码。<font>9 j- P! P- g# g5 a</font><br /> 2. 获取ca证书和帐号配置文件。这一步有二个渠道完成。<br /> <span style="display:none;">) &#123;# p" J% J6 S+ ]; V</span>2.1 借助Windows或Mac的机器安装好UltraVPN之后，复制<span>软件</span>安装路径中config目录下的ca.crt、client.ovpn和stealthy connect.ovpn三个文件。<br /> <span style="display:none;">+ I% E& X2 c7 [) O" y0 u&#8217; T( Q</span>2.2 下载偶为大家准备的<a href="http://c75ujq.blu.livefilestore.com/y1pOEhOJdCJWGbj4pnjEqIqc_Tsy5_dIV2yT1luxysxspAxro3OIIqEu5WWJRRkrRyAmiIIb_1GvWbdGDUujHDf4w/ca.crt?download" target="_blank" rel="noopener noreferrer">ca.crt</a>、<a href="http://c75ujq.blu.livefilestore.com/y1pGHe2CmyTHHOWf6JvZ1hOGnMdeDclrmBHr5VtIDFgJ9Rvwn_dOfkZfORsqWeTY4A9fhzLEM-6i57iJfusM3piGQ/client.ovpn?download" target="_blank" rel="noopener noreferrer">client.ovpn</a>、<a href="http://c75ujq.blu.livefilestore.com/y1pGHe2CmyTHHOzXyTn_oAkzITWOw0mhSyq2JI-wjFPxWkYN7HQhccPFkV_RoM6jIzxFfuXN0sJmLLh8KoJZmMScg/stealthy connect.ovpn?download" target="_blank" rel="noopener noreferrer">stealthy connect.ovpn</a>.<br /> <span style="display:none;">% F0 [5 k: V  B* i4 A* t# ?. P</span>3. 安装OpenVPN。<br /> <span style="display:none;">, X5 &#123;0 x% Q- M1 S</span>$ sudo apt-get install network-manager-openvpn4. 建立VPN连接。这一步也有两种方式完成。<font>&#8216; k" f0 H/ u; r+ e/ r: l</font><br /> 4.1 导入式。右键点击<span>网络</span>连<br /> 接图标，选择“Edit<br /> Connections…”，切换标签到“VPN”，点“Import“，选择第2步获取的client.ovpn文件（也可以选择stealthy<br /> connect.ovpn文件，用于创建安全连接），在弹出的编辑界面中填好第1 步注册的用户名、密码，”CA<br /> Certificate”选择第2步获取的”ca.crt”文件，点”<span>App</span>ly”完成。<font>1 U4 i7 L& l5 V</font><br /> 4.2 输入式。右键点击网络连接图标，选择“Edit<br /> Connections…”，切换标签到“VPN”，点“Add“创建连接。在弹出的“Chose a VPN Connection<br /> Type”界面中选择“OpenVPN”，<br /> 点“Create“，进入连接编辑页面。“Gateway“填“servers443.ultravpn.net”，“Type”选“Password<br /> “，接下来填用户名、密码、选“ca.crt“，点”Apply”完成。<font>6 I6 w1 u! D8 ~+ R5 &#125;</font><br /> <font>  G! [3 x. V: [; G# y</font></p> 
  
  <p>
    <span style="display:none;"><img src="http://tech.techweb.com.cn/images/default/attachimg.gif" border="0" /></span> 
  </p>
  
  <div style="z-index:999;clip:rect(auto,auto,auto,auto);left:387px;top:914px;display:none;">
    <a href="http://tech.techweb.com.cn/attachment.php?aid=6211&k=289e39b0c11c464e6f217f76a44472cc&t=1248970600&nothumb=yes&sid=f8b89%2BbQEQm1HochBOlPGTcHISJsP67CHRHWdjfY4aLagzY" title="3730667707_d4ff61ccb4_o.png" target="_blank" rel="noopener noreferrer"><strong>下载</strong></a> (27.83 KB)</p> 
    
    <div>
      2009-7-20 08:55
    </div>
  </div>
  
  <p>
    <font>% e1 P6 R, [1 i1 P2 k$ @</font><br /> <font>" i( H* h( p" J" ~8 f</font><br /> 5. 连接VPN。左键点击网络连接图标，在“VPN Connections“中选择第3步创建的连接，就可直通巴黎了。如果在第五步时遇到“no<br /> valid vpn secrets“的提示，那意味着你安装的network-manager-openvpn版本有Bug，解决方法如下：<font>0 E& P2 E&#8217; `&#8217; ]1 R1 s2 r</font><br /> $ sudo gedit /etc/apt/sources.list在文件后面加入以下两行：<br /> <span style="display:none;">4 W7 L0 H  I( k9 p1 w6 ]0 F( X" d</span>deb <a href="http://ppa.launchpad.net/network-manager/ppa/ubuntu" target="_blank" rel="noopener noreferrer">http://ppa.launchpad.net/network-manager/ppa/ubuntu</a> <你的<span>系统</span>版本代号> main deb-src <a href="http://ppa.launchpad.net/network-manager/ppa/ubuntu" target="_blank" rel="noopener noreferrer">http://ppa.launchpad.net/network-manager/ppa/ubuntu</a> <你的系统版本代号> main然后接着执行命令：<br /> <span style="display:none;">* j6 s# J, C$ k0 i/ g&#8217; k</span>$ sudo apt-get update $ sudo apt-get dist-upgrade如果提示没有秘钥,执行命令：<br /> <span style="display:none;">: b1 `; i2 z5 i# _1 p( e: Z</span>$ gpg &#8211;keyserver keyserver.ubuntu.com &#8211;recv-keys 248DD1EEBC8EBFE8 $ gpg &#8211;export -a 248DD1EEBC8EBFE8|sudo apt-key add &#8211;</div>