---
title: '[转帖]超级翻墙组合Autoproxy＋GAppProxy'
author: leo_thronton
type: post
date: 2009-08-01T16:12:23+00:00
url: /2009/08/01/转帖超级翻墙组合autoproxy＋gappproxy/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1021')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1021" class="bvMsg">
  <div>
    <p>
      其实，我们本不必要去学习这些内容的。－－和菜头
    </p>
    
    <p>
      风紧，却不能扯乎。对于我等能自觉抑制网络低俗内容的正常用户来说，学会翻墙实在是被逼的。
    </p>
    
    <p>
      研究了众多翻墙工具和方法，个人感觉在firefox中使用Autoproxy＋GAppProxy组合，是一个不错的选择。
    </p>
    
    <p>
      一、Autoproxy
    </p>
    
    <p>
      Autoproxy 是一个 Firefox插件，用以管理需要使用代理服务器访问的网站列表。与常用的foxproxy插件的最大区别是foxproxy 需要你自己定义哪些网站走代理，而autoproxy 却是由志愿者维护一个被gfw 的网站列表，在列表中的网站会自动走代理出去。这个列表在安装之初就可以被订阅。
    </p>
    
    <p>
      下载地址：<a href="https://addons.mozilla.org/zh_CN/firefox/addon/11009">https://addons.mozilla.org/zh_CN/firefox/addon/11009</a>
    </p>
    
    <p>
      配置指南：<a href="http://hi.baidu.com/flashgive/blog/item/c3db621899229d0e34fa4176.html">http://hi.baidu.com/flashgive/blog/item/c3db621899229d0e34fa4176.html</a>，基本不需要配置。
    </p>
    
    <p>
      注意：autoproxy 只是一个代理管理软件，是foxproxy、torbutton的替代品。因此你还需要一个代理服务器，比如tor（官网已被墙）、ZY门、无界、GAppProxy 。
    </p>
    
    <p>
      二、GAppProxy
    </p>
    
    <p>
      autoproxy默认的代理服务器就是GAppProxy。也支持Tor。
    </p>
    
    <p>
      推荐GAppProxy，因为它运行在Google App Engine上，不需要专门的服务器，Google的网络比较可靠，速度也很快。
    </p>
    
    <p>
      官方网址：<a href="http://code.google.com/p/gappproxy/">http://code.google.com/p/gappproxy/</a>
    </p>
    
    <p>
      使用说明：<a href="http://code.google.com/p/gappproxy/wiki/GAppProxy_Manual_for_Windows">http://code.google.com/p/gappproxy/wiki/GAppProxy_Manual_for_Windows</a>
    </p>
    
    <p>
      下载地址：<a href="http://code.google.com/p/gappproxy/downloads/list">http://code.google.com/p/gappproxy/downloads/list</a>，如果不自已搭建PROXY服务，只需下载GAppProxy-1.0.0beta.exe (GAppProxy的Windows客户端)就可以了。
    </p>
    
    <p>
      安装步骤：
    </p>
    
    <p>
      1、解压文件到任一目录，为绿色软件。
    </p>
    
    <p>
      2、双击运行gui.exe。
    </p>
    
    <p>
      3、勾选第2项，并填入<a href="http://fetchserver1.appspot.com/fetch.py">http://fetchserver1.appspot.com/fetch.py</a>，点Save。
    </p>
    
    <p>
      <img src="http://gappproxy.googlecode.com/svn/wiki/images/GAppProxy_Manual_for_Windows/7.PNG" border="0" />
    </p>
    
    <p>
      这是旧版的图片，新版略有差别，多了一个service按钮，点击可以将此安装为系统的一个服务，开机自动启动。不用再每次点Gui.exe。
    </p>
    
    <p>
      4、点击Hide按钮：隐藏主窗口，在系统右下角托盘栏增加了一个绿圈状图标，在该图标上点击右键菜单的”Restore”项可以恢复显示主窗口。
    </p>
    
    <p>
      OK，可以用了!
    </p>
    
    <p>
      访问facebook、youtube等都正常，速度与正常访问几乎没有差别，twitter好像还有点问题，首页可以进。如果你不能访问，可能是你所在地区的电信屏蔽了GAppProxy服务。那么你只能用autoproxy+tor了。tor可以在这里下载，配置看这里。
    </p>
    
    <p>
      BTW：GAppProxy新版已经支持https访问。
    </p>
  </div>
</div>