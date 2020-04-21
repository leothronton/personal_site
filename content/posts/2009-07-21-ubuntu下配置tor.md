---
title: Ubuntu下配置Tor
author: leo_thronton
type: post
date: 2009-07-21T12:52:42+00:00
url: /2009/07/21/ubuntu下配置tor/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1010')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1010" class="bvMsg">
  <div>
    <p>
      Tor（洋葱路由）是著名的翻强软件，用户通过Tor可以在因特网上进行匿名交流。在Ubuntu下使用Tor还需要Privoxy的支持。Privoxy是一款带过滤功能的代理服务器。
    </p>
    
    <p>
      1。安装 privoxy：
    </p>
    
    <p>
      sudo apt-get install tor privoxy
    </p>
    
    <p>
      2。安装Tor：
    </p>
    
    <p>
      由于9.04官方源中没有tor了，所以只能自行添加源
    </p>
    
    <p>
        deb     <a href="http://mirror.noreply.org/pub/tor">http://mirror.noreply.org/pub/tor</a> etch main<br />   deb-src <a href="http://mirror.noreply.org/pub/tor">http://mirror.noreply.org/pub/tor</a> etch main
    </p>
    
    <p>
      更新：如果是9.04，可能还需要添加密钥：
    </p>
    
    <p>
      gpg &#8211;keyserver keys.gnupg.net &#8211;recv 94C09C7F<br /> gpg &#8211;export 94C09C7F | sudo apt-key add &#8211;
    </p>
    
    <p>
      然后在终端执行
    </p>
    
    <p>
      sudo apt-get update<br /> sudo apt-get install tor
    </p>
    
    <p>
      即可完成tor安装
    </p>
    
    <p>
      3。配置Tor：
    </p>
    
    <p>
      在终端执行
    </p>
    
    <p>
      sudo gedit /etc/privoxy/config
    </p>
    
    <p>
      在最前面加上下面这一行（别漏了那个不起眼的“.”）：
    </p>
    
    <p>
      forward-socks4a / localhost:9050 .
    </p>
    
    <p>
      你可能希望 privoxy 不要把什么事情都记录下来，找到下面的两行，通过在它们前面添加“#”注释掉它们：
    </p>
    
    <p>
      &#8230;<br /> logfile logfile<br /> &#8230;<br /> jarfile jarfile<br /> &#8230;
    </p>
    
    <p>
      保存修改了的 /etc/privoxy/config 文件。
    </p>
    
    <p>
      重新启动 privoxy 服务 ，在终端执行
    </p>
    
    <p>
      sudo /etc/init.d/privoxy restart
    </p>
    
    <p>
      4。使用Tor：<br /> 在Ubuntu下使用Tor的最简单的办法就是使用Firefox＋Torbutton这个插件。当Torbutton安装完之后。点击右下角Torbutton就可改变Tor的工作状态。使用很简单。
    </p>
    
    <p>
      5。验证Tor是否正常工作<br /> 你可以去<a href="http://www.ip138.com/">http://www.ip138.com/</a> 检查你的ip地址
    </p>
    
    <p>
       
    </p>
    
    <p>
       
    </p>
  </div>
</div>