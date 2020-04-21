---
title: ANSYS V12安装问题1：Invalid license file：the FLexlm ID in the file does not mat …
author: leo_thronton
type: post
date: 2011-11-16T20:40:28+00:00
url: /2011/11/16/ansys-v12安装问题1：invalid-license-file：the-flexlm-id-in-the-file-does-not-mat/
categories:
  - 收集
tags:
  - system
  - 文件夹
  - 无线网卡
  - 笔记本
  - 解决方法

---
<div class="PublishedByWebStory-[6]51_EB4B8A41D5BD40649F669AA8D0C547DB_AD8C99F574FE40DC86733677B5326252">
  <div>
    <font size="3"><br /></font>
  </div>
  
  <table>
    <tr>
      <td>
        <div id="blog_text">
          <p>
            在安装ansys V12的过程中，碰到了这个问题。在最后加载license时，弹出Invalid license file：the FLexlm ID in the file does not match the system Flexlm ID. 出现这个问题是因为ansys自动找到的网卡地址，与实际的网卡地址不符，一般是因为电脑禁止了网卡所致。
          </p>
          
          <p>
          </p>
          
          <p>
            你可以‘运行’——cmd——ipconfig/all 看能不能找到网卡ID，也就是常说的MAC地址，如果找不到，就肯定是这个原因了。
          </p>
          
          <p>
            解决方法：
          </p>
          
          <p>
            右击“我的电脑”——选择“属性”——选择“硬件”——“设备管理器”——查看网卡是否有问题（打叉或者问号）——右击启用网卡，即可。
          </p>
          
          <p>
            再重新生成license文件，放在指定文件夹下，重新安装加载license，问题就解决了。
          </p>
          
          <p>
            <span><br /></span>
          </p>
          
          <p>
            <span>PS：如果上述方法不能解决的话，也可能是</span><span>在安装时没有关闭</span><span>笔记本的无线网卡导致。</span>
          </p></p>
        </div>
      </td>
    </tr>
  </table>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo24.png" alt="菊子曰" style="border:0;" /></a>&nbsp;我用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>写博客，你呢？
  </div>
</div>