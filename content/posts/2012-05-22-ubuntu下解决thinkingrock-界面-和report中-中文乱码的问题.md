---
title: Ubuntu下解决Thinkingrock 界面 和Report中 中文乱码的问题
author: leo_thronton
type: post
date: 2012-05-22T18:14:37+00:00
url: /2012/05/22/ubuntu下解决thinkingrock-界面-和report中-中文乱码的问题/
categories:
  - ubuntu

---
<div class="PublishedByWebStory-[6]1_9E2EF8771DEC4211AF4E3B018817FE31_0689EEF5547F4DEAB6917C05F378D5D3">
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/05/170c5d06b780b2a3af21404ee424a96cc7cddc9c.jpg" width="460" height="329" />
  </p>
  
  <p>
    Thinkingrock 是一款跨平台的GTD软件，他完全按照GTD思想来处理你的各种想法。整个流程分为收集，处理，组织，检查，做。
  </p>
  
  <p>
    Thinkingrock是在netbeans基础上编写的，以此实现跨平台。但是在Ubuntu下使用免费版Thinkingrock 2.2.1时出现了如下图所示的情况，中文部分都变成了方框。
  </p>
  
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/05/2e39d17a809230ec29ee057dc2505b4af36bddee.png" width="600" height="480" />
  </p>
  
  <p>
    出现这样情况的原因是安装包中自带的jvm中的字体和系统字体并不相同。解决办法有两种：一个是把/usr/share/fonts/truetype/arphic中的字体复制到Thinkingrock目录中/jre/lib/fonts/fallback目录中。另一个是如果你在系统中安装了如永中office等带jvm的中文软件。可以修改Thinkingrock目录中etc子目录下的thinkingrock.conf。找到jdkhome，将其前面的#去掉并加上支持中文的jre所在路径。修改完成之后Thinkingrock就可以正常显示中文了。如下图。
  </p>
  
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/05/d82d3e22295c7f6966a81198fc82ce66a10cc6de.png" width="600" height="480" />
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    Thinkingrock另一个功能就是输出PDF格式的报表，但他在生成带中文的报表时也出现中文乱码的问题。原因是Thinkingrock输出的PDF所带字体太少，不支持非英文语言。
  </p>
  
  <p>
    先给Thinkingrock增加中文字体，我用的是文泉驿微米黑。
  </p>
  
  <table border="0" width="80%">
    <tr>
      <td width="80%">
        $ cd /tr-2.0.1/tr/resource/fop<br /> $ ln -s /usr/share/fonts/truetype/wqy/wqy-microhei.ttc<br /> $ java -cp ../../modules/ext/fop-0.93.jar:../../modules/ext/avalon-framework-4.2.0.jar:../../modules/ext/commons-logging-1.0.4.jar:../../modules/ext/commons-io-1.1.jar org.apache.fop.fonts.apps.TTFReader -ttcname &#8220;WenQuanYiMicroHei&#8221; wqy-microhei.ttc wqy-microhei.xml
      </td>
    </tr>
  </table>
  
  <p>
    用过这些命令之后在fop文件夹下就会出现wqy-microhei.ttc wqy-microhei.xml 这两个文件了。
  </p>
  
  <p>
    接着修改fop文件夹下的fop.xconf文件。在文件中加上下面一段：
  </p>
  
  <table border="0" width="80%">
    <tr>
      <td width="80%">
        <!&#8211; WenQuanYi Micro Hei Font &#8211;><br /> <font metrics-url=&#8221;wqy-microhei.xml&#8221; kerning=&#8221;yes&#8221; embed-url=&#8221;wqy-microhei.ttc&#8221;><br /> <font-triplet name=&#8221;WenQuanYiMicroHei&#8221; style=&#8221;normal&#8221; weight=&#8221;normal&#8221;/><br /> </font><br /> <font metrics-url=&#8221;wqy-microhei.xml&#8221; kerning=&#8221;yes&#8221; embed-url=&#8221;wqy-microhei.ttc&#8221;><br /> <font-triplet name=&#8221;WenQuanYiMicroHei&#8221; style=&#8221;normal&#8221; weight=&#8221;bold&#8221;/><br /> </font><br /> <font metrics-url=&#8221;wqy-microhei.xml&#8221; kerning=&#8221;yes&#8221; embed-url=&#8221;wqy-microhei.ttc&#8221;><br /> <font-triplet name=&#8221;WenQuanYiMicroHei&#8221; style=&#8221;italic&#8221; weight=&#8221;normal&#8221;/><br /> </font><br /> <font metrics-url=&#8221;wqy-microhei.xml&#8221; kerning=&#8221;yes&#8221; embed-url=&#8221;wqy-microhei.ttc&#8221;><br /> <font-triplet name=&#8221;WenQuanYiMicroHei&#8221; style=&#8221;italic&#8221; weight=&#8221;bold&#8221;/><br /> </font>
      </td>
    </tr>
  </table>
  
  <p>
    完工之后就可以在Thinkingrock中Tools -> Options -> Miscellaneous -> Action Screens选择微米黑字体了。这样输出的中文报表就能正常显示了。
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo20.png" alt="菊子曰" style="border:0;" /></a>&nbsp;写博客，就用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>！
  </div>
</div>