---
title: 用Notepad++ 调试 Python 及缩进问题
author: leo_thronton
type: post
date: 2012-01-03T18:46:26+00:00
url: /2012/01/03/用notepad-调试-python-及缩进问题/
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]1_509DED8DAFD247EC980F7350058D776B_BD2D4718086249AC87AC6DE4BD14607B">
  <p>
    &nbsp;&nbsp;&nbsp; 用Notepad++编写python非常方便。NP体积小，打开速度快，是编写小规模代码的理想选择。但是在代码编写完之后，能不能方便地调试程序呢？
  </p>
  
  <p>
    答案是肯定的，不过先要做一点设置。
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/01/e52a0fca67a4effc91d27410d50e27508ec188fa.png" width="310" height="197" />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  </p>
  
  <p>
    &nbsp;<span style="text-align:left;widows:2;text-transform:none;background-color:rgb(240,246,251);text-indent:0;letter-spacing:normal;display:inline!important;font:12px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:rgb(70,70,70);word-spacing:0;">NP默认F5键位运行程序，在“输入运行程序名”中填写：</span>
  </p>
  
  <div style="border-bottom:#e0e0e0 1px solid;border-left:#e0e0e0 1px solid;background:#ffffc0 no-repeat 4px 6px;border-top:#e0e0e0 1px solid;border-right:#e0e0e0 1px solid;padding:10px;">
    <span style="text-align:left;widows:2;text-transform:none;background-color:rgb(240,246,251);text-indent:0;letter-spacing:normal;display:inline!important;font:12px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:rgb(70,70,70);word-spacing:0;">cmd /k X:PythonXXpython.exe &#8220;$(FULL_CURRENT_PATH)&#8221; & PAUSE & EXIT</span>
  </div>
  
  <p>
    然后点保存，选择相应的快捷键，然后点OK。注意快捷键不能再用F5。除非你在 设置→管理快捷键 中另外设置。
  </p>
  
  <p>
    <img border="0" src="http://leothronton.files.wordpress.com/2012/01/6121eaf5ce91808117290875d37ffeecca09b40c.png" width="286" height="200" />
  </p>
  
  <p>
    这样设置之后，就能在Notpad++中直接调试python 代码了。
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    不过有个问题。将在别处编写的python代码拷贝到Notpad++中，修改之后再调试时，经常会出现“IndentationError: unexpected indent”这个错误。
  </p>
  
  <p>
    引起这个错误的原因是tab和空格缩进混用。
  </p>
  
  <p>
    我们知道python语法对缩进的要求非常严格。python中要求一个tab为4个空格长度，而NP使用的是默认1个tab长度。更改方法为：
  </p>
  
  <p>
    设置→首选项→语言→在右下角“标签尺寸4”勾选 “以空格取代”。这个选项隐藏得够深的。<img border="0" src="http://leothronton.files.wordpress.com/2012/01/7bebb950b8b84a60aacb2c6d99476d8553f8af0f.png" width="721" height="416" />
  </p>
  
  <p>
    完成之后就一切正常了，修改别人的代码也不出现缩进报错了。
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo20.png" alt="菊子曰" style="border:0;" /></a>&nbsp;<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>：专业的博客管理软件
  </div>
</div>