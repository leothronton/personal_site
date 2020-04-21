---
title: Project Euler 第三题的一个nb算法
author: leo_thronton
type: post
date: 2013-01-27T14:38:29+00:00
url: /2013/01/27/project-euler-第三题的一个nb算法/
categories:
  - 未分类

---
题目：求<span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">600851475143 的最大质因数。</span>

<span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">搞了2,3个小时，搞出来的算法效率都很低。网上发现一个nb算法。改成python后如下：</span>

<span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">————————————————————————————————————</span>

<span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">def maxPrime():</p> 

<p>
  n=600851475143
</p>

<p>
  d=2</span>
</p>

<p>
  while d<n/d:
</p>

<p>
  if n%d==0:
</p>

<p>
  n=int(n/d)
</p>

<p>
  else:
</p>

<p>
  d=d+1
</p>

<p>
  return n
</p>

<p>
  <span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;"></p> 
  
  <p>
    if __name__==&#8221;__main__&#8221;:
  </p>
  
  <p>
    from time import clock
  </p>
  
  <p>
    start=clock()
  </p>
  
  <p>
    finish=clock()
  </p>
  
  <p>
    print(&#8220;the largest prime factor is {0}tt{1}s&#8221;.format(maxPrime(),(finish-start)/1000000))</span>
  </p>
  
  <p>
    <span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">————————————————————————————————————</span>
  </p>
  
  <p>
    结果:
  </p>
  
  <p>
    the largest prime factor is 6857 4.462223927783368e-13s
  </p>
  
  <p>
    <span style="widows:2;text-transform:none;background-color:#ffffff;text-indent:0;letter-spacing:normal;display:inline!important;font:16px 'WenQuanYi Micro Hei Mono', 'WenQuanYi Micro Hei', 'Microsoft Yahei Mono', 'Microsoft Yahei', sans-serif;white-space:normal;orphans:2;float:none;color:#000000;word-spacing:0;-webkit-text-size-adjust:auto;">————————————————————————————————————</span>
  </p>
  
  <p>
    哎，差距啊~
  </p>