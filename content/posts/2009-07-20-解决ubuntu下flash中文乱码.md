---
title: 解决ubuntu下flash中文乱码
author: leo_thronton
type: post
date: 2009-07-20T07:07:25+00:00
url: /2009/07/20/解决ubuntu下flash中文乱码/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1009')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1009" class="bvMsg">
  <div>
    <span style="font-family:宋体;">ubuntu中， 为浏览器firefox安装flash插件后，发现提示框中的中文会变成方框。解决办法如下：</span><br style="font-family:宋体;" /> <br style="font-family:宋体;" /> <span style="font-family:宋体;">1.在终端中输入：sudo gedit /etc/fonts/conf.d/49-sansserif.conf</span><br style="font-family:宋体;" /> <span style="font-family:宋体;">2.将其中的sans-serif或者serif用中文字体的名字代替。</span><br style="font-family:宋体;" /> <br style="font-family:宋体;" /> <span style="font-family:宋体;">比如：我的系统中安装了微软雅黑，我则用msyh代替sans-serif和serif，结果如下：</span><br style="font-family:宋体;" /> <br style="font-family:宋体;" /> <span style="font-family:宋体;"><match target=”pattern”></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><test qual=”all” name=”family” compare=”not_eq”></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><string>msyh</string></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"></test></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><test qual=”all” name=”family” compare=”not_eq”></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><string>msyh</string></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"></test></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><test qual=”all” name=”family” compare=”not_eq”></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><string>monospace</string></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"></test></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><edit name=”family” mode=”append_last”></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"><string>msyh</string></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"></edit></span><br style="font-family:宋体;" /> <span style="font-family:宋体;"></match></p> 
    
    <p>
      完工。<br /></span></div> </div>