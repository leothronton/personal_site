---
title: '[转]synergy一套鼠键控制多个PC（synergy设置教程）'
author: leo_thronton
type: post
date: 2012-04-01T18:01:36+00:00
url: /2012/04/01/转synergy一套鼠键控制多个pc（synergy设置教程）/
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]1_E232C24EADBA43D59CFCC1BDEEA8B92D_04D40A5BF9624E2DB4E7395D1FB8604C">
  <p>
    <a href="http://www.freewaremaster.net/synergy.htm">synergy一套鼠键控制多个PC（synergy设置教程）</a>
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/04/b702e6f8933cf6ccf03f95ef51ecd5fdf9cbfb9b.png" width="645" height="302" />
  </p>
  
  <p>
    如果你是一个搞电脑吃饭的人，一定会遇到同时使用多台电脑的时候，在不同的电脑间换来换去是一个非常麻烦的事。现在为你介绍一款软件，它可以让你用一套鼠标和键盘控制多个电脑，你要做的就是把电脑显示器放到你的视野内就可以了。这款软件的名字叫synergy。
  </p>
  
  <p>
    <strong>1.synergy是什么？</strong>
  </p>
  
  <p>
    Synergy 是一款能够让使用者仅用一套键盘鼠标，就同时操控多部计算机的免费工具软件。使用者能够在包括 Windows 、 Linux 、 Mac OS 等不同的系统上安装它，并且在设定好主从关系后，就能够透过一组键盘鼠标来进行多部计算机的操控。<br /> 这样子的操控方式，对于拥有笔记型计算机的人来说尤其方便，你能够将笔记型计算机与家中的桌上型计算机设定好主从关系，如此一来，就能够利用笔记型计算机来操控两部计算机，不需要额外的切换装置的帮忙，就能够方便地完成许多工作。<br /> 使用者在使用 Synergy 时要特别注意的是，必须要仔细设置主从关系的切换设定，如此才能够顺利地透过鼠标光标的移动来切换目前所使用的计算机，不至于因为鼠标光标一移到新计算机，就无法切换为原计算机的窘境。
  </p>
  
  <p>
    <strong>2.synergy下载</strong>
  </p>
  
  <p>
    软件名称：synergy<br /> 软件语系：英文<br /> 软件大小：959KB<br /> 操作系统：Windows XP / Vista / 7 （相容32、64位元）<br /> 官方网站：<a href="http://synergy-foss.org/">http://synergy-foss.org/</a><br /> 立即下载：1.3.4-Windows-x86.exe | 1.3.4-Windows-x64.exe | 1.3.4-Linux-x86_64.deb |&nbsp; 1.3.4-Linux-i686.deb | 1.3.4-Linux-x86_64.rpm
  </p>
  
  <p>
    <strong>3.synergy使用设置</strong>
  </p>
  
  <p>
    <strong>服务器设置</strong>
  </p>
  
  <p>
    首先在 computerA 上启动 Synergy， 选择 Share this computer&#8217;s keyboard and mouse (server)。
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/04/e72848f9bbfe51990601b329ac6708d8d5e63b70.png" width="463" height="357" /><br /> 然后单击下面的Configure&#8230;按钮，以配置各个屏幕。 单击 Screens 下面的 + 按钮，输入 Screen Name 为 computerA，确定。 同样的方法依次添加 computerB 和 computerC。<br /> 然后我们要设置这三个屏幕的布局。在 Links 的列表框下方有一排输入框和选择框， 将其依次设置为以下的内容然后单击下方的 + 按钮。<br /> 0 to 100% of the left of computerA goes to 0 to 100% of computerB<br /> 0 to 100% of the right of computerB goes to 0 to 100% of computerA<br /> 0 to 100% of the left of computerC goes to 0 to 100% of computerA<br /> 0 to 100% of the right of computerA goes to 0 to 100% of computerC<br /> 这样我们就将三个屏幕设置为 B &#8211; A &#8211; C 的布局了。 注意两个屏幕之间的连接是双向的，比如我们设置了 B <- A， 也要同时设置 B -> A，否则鼠标从 A 移动到 B 之后就无法回到 A 了。 最终的结果如下。<br /> <img border="0" src="http://leothronton.files.wordpress.com/2012/04/19dd6b33bef11e6607fb551ef35a4695c978fced.png" width="550" height="383" />
  </p>
  
  <p>
    回到主界面，单击 Advanced&#8230; 按钮，确认Screen Name的内容为 computerA，确定。
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/04/857de24cec6b0dcf0478fba6f1cc6a9716bd6f4e.png" width="370" height="341" /><br /> 至此服务器端设置完毕，先不要关闭 Synergy 的对话框。
  </p>
  
  <p>
    <strong>客户端设置</strong>
  </p>
  
  <p>
    在 computerB 上启动 Synergy，选择Use another computer&#8217;s shared keybord and mouse(client)， 并在下面的主机名处填写 computerA。
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/04/be2a9b43f288dcc1b3ba1097e2f87f323df4f645.png" width="470" height="361" />
  </p>
  
  <p>
    然后单击 Advanced&#8230; 按钮，确认Screen Name的内容为 computerB。
  </p>
  
  <p>
    在 computerC 上用同样的方法进行设置。
  </p>
  
  <p>
    <strong>测试</strong>
  </p>
  
  <p>
    在 computerA 上单击 Test 按钮，然后依次在 computerB 和 computerC 上单击 Test 按钮。我们试着在 computerA 上将鼠标移动到屏幕左侧， 就会看到鼠标移动到了 computerB 上，而此时键盘也在控制 computerB； 然后将鼠标移动到 computerB 屏幕右侧，鼠标就会回到 computerA； 再将鼠标移动到 computerA 右侧，鼠标就会移动到 computerC 上。
  </p>
  
  <p>
    <strong>启动</strong>
  </p>
  
  <p>
    最后依次在每台电脑上单击 AutoStart&#8230; 按钮， 选择登录时自动启动或者电脑启动时自动启动 Synergy，单击Install按钮。 最后回到主界面，单击 Start 按钮关闭 Synergy 设置窗口即可。
  </p>
</div>