---
title: '[转]Chrome使用技巧-使用Google https（SSL）加密搜索'
author: leo_thronton
type: post
date: 2012-09-25T14:10:26+00:00
url: /2012/09/25/转chrome使用技巧-使用google-https（ssl）加密搜索/
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]1_73CE662E20FA4932A46381862A5B46BA_BE8B827D35584301BF32D0FFA7ECD211">
  <p>
    发表于 2010/05/26 由 麦子地
  </p>
  
  <p>
    <img border="0" align="left" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/09/8aca4e3065fa9e6456f4e2a70c8677315e3f52ec.png" width="171" height="40" />前面有两篇文章提到了如何通过扩展的方式让Firefox自动使用Google https加密搜索，在Chrome（Google浏览器）中使用Google https（ssl）加密搜索的设置相对来说更加简单。<br /> Chrome有多种便捷的搜索方式，参见“Chrome使用技巧-搜索引擎的设置与使用方法”，其中最方便的莫过于在地址栏中输入关键词，回车后直接使用默认搜索引擎进行搜索。下面就介绍通过修改默认搜索引擎的办法让Chrome使用Google安全搜索。
  </p>
  
  <p>
    1. 先测试一下能不能直接打开<a href="https://www.google.com/">https://www.google.com</a>，很可能会出现的问题是浏览器自动转向到谷歌香港<a href="http://www.google.com.hk/">http://www.google.com.hk</a>。<br /> 解决方法：先访问一次<a href="http://www.google.com/ncr">http://www.google.com/ncr</a> ，以后再打开<a href="https://www.google.com/">https://www.google.com</a>或者<a href="http://www.google.com/">http://www.google.com</a>就不会再转向到谷歌香港了。
  </p>
  
  <p>
    2. 在地址栏上点击鼠标右键，选择“修改搜索引擎”
  </p>
  
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/09/2e1b44581357697c43bac62ba37bbd6a88534454.png" width="402" height="244" /><br /> 3. 在“搜索引擎”窗口中，点击右侧的“添加”；
  </p>
  
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/09/3c5d584a1dda75dac42720da9a9257a651ab8259.png" width="500" height="312" />
  </p>
  
  <p>
    4. 将<a href="https://www.google.com/">https://www.google.com</a>添加到列表中。在窗口中填入以下内容
  </p>
  
  <ul>
    <li>
      名称：Google
    </li>
    <li>
      关键字：ssl （选填，可以在地址栏中输入关键字快速选择搜索引擎）
    </li>
    <li>
      网址：<a href="https://www.google.com/search?hl=zh-CN&source=hp&q=%s&aq=f&aqi=&aql=&oq=&gs_rfai">https://www.google.com/search?hl=zh-CN&source=hp&q=%s&aq=f&aqi=&aql=&oq=&gs_rfai</a>=
    </li>
  </ul>
  
  <p>
    <img border="0" src="http://192.168.3.16/wordpress/wp-content/uploads/2012/09/4b85f9352b45692f8346558bbdb0da4e5d53725f.png" width="276" height="208" />
  </p>
  
  <p>
    5. 确定后，在第2步中的界面右侧将其设置为默认搜索引擎。
  </p>
  
  <p>
    按照上述四步设置完毕后，就可以直接使用能躲开第三方拦截的Google加密搜索了。
  </p>
  
  <p>
    版权声明：本站原创文章可以任意转载，请务必完整保留以下版权信息：<br /> 转载自麦子地 链接地址: <a href="http://www.maizidi.com/chrome-use-google-https-ssl/">Chrome使用技巧-使用Google https（SSL）加密搜索</a>
  </p>
</div>