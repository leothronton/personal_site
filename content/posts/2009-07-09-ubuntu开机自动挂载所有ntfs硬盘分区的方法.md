---
title: Ubuntu开机自动挂载所有ntfs硬盘分区的方法
author: leo_thronton
type: post
date: 2009-07-09T17:20:38+00:00
url: /2009/07/09/ubuntu开机自动挂载所有ntfs硬盘分区的方法/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1007')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1007" class="bvMsg">
  <div>
    <div>
      <div style="font-size:14px;">
        <span style="color:rgb(0,0,0);">需要两个软件：ntfs-config和ntfs-3g。从ubuntu8.04开始已经安装了ntfs-3g。</span><br style="color:rgb(0,0,0);" /> <br style="color:rgb(0,0,0);" /> <span style="color:rgb(0,0,0);">在终端运行 sudo apt-get install ntfs-config ntfs-3g</span><br style="color:rgb(0,0,0);" /> <span style="color:rgb(0,0,0);">1.打开应用程序”－>“系统工具”－>“NTFS写入支持配置程序”</span><br style="color:rgb(0,0,0);" /> <span style="color:rgb(0,0,0);">2.选中你要开机自动运行的分区</span><br style="color:rgb(0,0,0);" /> <span style="color:rgb(0,0,0);">3.然后选中“启用内部设备写支持”和“启用外部设备写支持”两项</span><br style="color:rgb(0,0,0);" /> <br style="color:rgb(0,0,0);" /> <span style="color:rgb(0,0,0);">重启后就可以自动挂载NTFS分区了</span></p>
      </div>
    </div>
  </div>
</div>