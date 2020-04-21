---
title: '[转]cookies.sqlite造成FireFox登录状态不能保存的问题'
author: leo_thronton
type: post
date: 2009-07-22T13:16:41+00:00
url: /2009/07/22/转cookies-sqlite造成firefox登录状态不能保存的问题/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1013')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1013" class="bvMsg">
  <div>
    <p>
      不知从什么时候开始，我的FireFox在登录Gmail、Google服务、Del.icio.us及各网站时的“记住登录状态”不好用了，哪怕是选择让它记录一年，只要重启FireFox，就又是未登录状态了……
    </p>
    
    <p>
      从网上找了一大堆解决方案，归结一下大约如下：
    </p>
    
    <p>
          * 在about:config中增加network.cookie.maxNumber及network.cookie.maxPerHost两项<br />     * 在about:config中修改general.useragent.override值（我的原来没有，手工加了一个）<br />     * 停用adblock plus及可能会造成问题的其它FireFox扩展<br />     * 停用防火墙（我用的是NOD32）<br />     * 停用代理服务器<br />     * 删除C:Documents and Settings系统登录名Application DataMozillaFirefoxProfiles随机文件夹名cookies.sqlite
    </p>
    
    <p>
      但实际一一照做后却没有一个见效，正郁闷的时候忽然想起我用的FireFox不是安装版，而是Portable版，Portable版的软件在软件退出时会把软件用到的注册表、配置文件等全都保存在软件目录下的data文件夹中，赶紧到“Dataprofile”中一找，还真有个cookies.sqlite文件，有268K之“巨”，删除之……登录Gmail，重启FireFox，再进Gmail.com，呵呵，搞定！
    </p>
  </div>
</div>