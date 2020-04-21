---
title: ubuntu 下安装eclipse with python3.x
author: leo_thronton
type: post
date: 2012-06-06T15:29:17+00:00
url: /2012/06/06/ubuntu-下安装eclipse-with-python3-x/
categories:
  - ubuntu

---
<div class="PublishedByWebStory-[6]1_A829981614AC4129B2F556542F7FC8BD_66282677BB12421F85343113678AFDCA">
  <p>
    先装 python3，没啥好说的<br /> 再装eclipse：<br /> 1.&nbsp; 先在源里装eclipse。<br /> 2.&nbsp; 安装好eclipse之后：<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1）&nbsp; Help->Install New Software&#8230;<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2）&nbsp; 点&#8221;Add&#8221;在弹出菜单里&#8221;Name&#8221;里填PyDev，位置里填<a href="http://pydev.org/updates">http://pydev.org/updates</a>，点OK。<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3）&nbsp; 在弹出菜单里选上PyDev，一路Next直到Finish。安装完会要重启一次eclipse。<br /> 3.&nbsp; 配置PyDev：<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1）&nbsp; 重启后打开eclipse，选Windows->Preferences.<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2）&nbsp; 在左边选Pydev->Interpreter &#8211; Python.<br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3）&nbsp; 点New，在Interpreter里，Name填python3.x。 在Interpreter Executable点Browse，在/usr/bin里找到python3.x。点Open，点2次OK，点Apply。
  </p>
  
  <p>
    4. 验证：<br /> &nbsp;&nbsp;&nbsp; 1）&nbsp; File->New->Pydev Project<br /> &nbsp;&nbsp;&nbsp; 2）&nbsp; Projcet Name填 pytest3.x，在Grammar Version选3.x。点完成。<br /> &nbsp;&nbsp;&nbsp; 3）&nbsp; 在左边pytest3.x的文件夹上右键，New->File，吓填个名字.py，输入如print(&#8216;Hello&#8217;),点F11，如果正常运行则配置OK了。&nbsp;
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo20.png" alt="菊子曰" style="border:0;" /></a>&nbsp;写博客，就用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>！
  </div>
</div>