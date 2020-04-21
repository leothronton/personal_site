---
title: 修改GNOME Commander默认打开方式
author: leo_thronton
type: post
date: 2012-05-15T16:56:44+00:00
url: /2012/05/15/修改gnome-commander默认打开方式/
categories:
  - ubuntu

---
<div class="PublishedByWebStory-[6]1_BC56EF18F1864A96A7E40D5EC08EB945_28E2207EEE4041A1BDA311151C8DAF09">
  <p>
    在装了Smplayer之后想把它作为视频的默认播放器，但在GNOME Commander中无法修改右键的默认打开方式，它始终默认用电影播放器来播放。
  </p>
  
  <p>
    想要修改默认打开方式需要手动编辑~/.local/share/applications/defaults.list这个文件，如果不存在需要自己创建。defaults.list内容如下：
  </p>
  
  <table border="0" width="80%">
    <tr>
      <td width="80%">
        [Default Applications]<br /> application/x-glade=glade-3.desktop
      </td>
    </tr>
  </table>
  
  <p>
    application/x-glade是文件类型，glade-3.desktop是程序的快捷方式。
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo20.png" alt="菊子曰" style="border:0;" /></a>&nbsp;<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>：专业的博客管理软件
  </div>
</div>