---
title: 用NotePad++写python及自动补全
author: leo_thronton
type: post
date: 2011-12-20T19:11:38+00:00
url: /2011/12/20/用notepad写python及自动补全/
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]1_AC6B2A04473D4C89A1728A07E803EC95_36042FCC42EE4E299DF6180274A5788B">
  <p>
    以前一直用eclipse+pydev写python，但是eclipse启动速度实在太悲催了。后来有人推荐用Notepad++。NP确实不错，体积小，绿色且启动速度极快。支持的语言种类也很多，插件巨多，和Emeditor有的一拼。
  </p>
  
  <p>
    将NP和“.py”后缀关联之后就能直接双击打开。支持关键字，括号高亮又能自动缩进，真是好东西呀。不过用惯了eclipse就希望NP能有函数提示和自动补全。
  </p>
  
  <p>
    打开函数补全的方法：&nbsp;&nbsp;&nbsp;&nbsp;
  </p>
  
  <div style="border-bottom:#e0e0e0 1px solid;border-left:#e0e0e0 1px solid;background:#ffffc0 no-repeat 4px 6px;border-top:#e0e0e0 1px solid;border-right:#e0e0e0 1px solid;padding:10px;">
    设置→首选项→备份与自动完成，勾选“所有输入均启用自动完成，函数自动完成”
  </div>
  
  <p align="left">
    <strong>&nbsp;&nbsp;&nbsp;</strong> 函数自动完成的快捷键是ctrl+space，和输入法冲突，遂改成alt+space
  </p>
  
  <p>
    &nbsp;&nbsp;&nbsp; ps:自动注释的快捷键是ctrl+Q
  </p>
  
  <p>
    NP的自动补全之支持函数和单词，括号和引号等不支持。随即放狗去搜，网上推荐都是TextFx。但是安装了这个插件之后不管我怎么弄就是不起作用。搜了n多博客，内容都是一样的，抄来抄去，一会儿说勾选AUTO CLOSE ([{就可以了，一会儿又说要ANSI版的才能用，这样不解决问题啊。最后在sourceforge的wiki里看到还有一个插件叫XBrackets。它的功能比TextFx弱很多，仅仅用来自动补全([{还有&#8221;，这仅有的功能就是我要的功能。
  </p>
  
  <p>
    下载下来之后在：&nbsp;&nbsp;&nbsp;&nbsp;
  </p>
  
  <div style="border-bottom:#e0e0e0 1px solid;border-left:#e0e0e0 1px solid;background:#ffffc0 no-repeat 4px 6px;border-top:#e0e0e0 1px solid;border-right:#e0e0e0 1px solid;padding:10px;">
    插件→XBrackets Lite→Settings 勾选Autocomplete Brackets 就可以了。
  </div>
  
  <p>
    这样Notepad++就能自动补全函数，括号和引号了。
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    <span style="widows:2;text-transform:none;text-indent:0;letter-spacing:normal;font:12px Arial;white-space:normal;orphans:2;color:rgb(34,34,34);word-spacing:0;" class="Apple-style-span"><font color="#000000" face="微软雅黑">ps:</font>谷歌和百度到底是什么关系，为什么谷歌上搜出来的结果不是百度知道就是百度百科要不就是百度的博客，-_-!</span>
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo20.png" alt="菊子曰" style="border:0;" /></a>&nbsp;写博客，就用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>！
  </div>
</div>