---
title: SymPy Tutorial
author: leo_thronton
type: post
date: 2014-06-21T06:04:01+00:00
url: /2014/06/21/sympy-tutorial/
timeline_notification:
  - 1540188246
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]1_8021EC254B434C50B6E15A663BCE812F_294FC951F2334A7E87D1CDD750C6151B">
  <h1 id="sympy-tutorial">
    <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/">SymPy Tutorial</a>
  </h1>
  
  <p>
    翻译自：<a class="external" href="http://docs.sympy.org/dev/tutorial.html" target="_blank" rel="noopener noreferrer">SymPy Tutorial</a>,其实有人译过了，但我看着不爽……你看我的不爽可以参考他的<a class="external" href="http://blankdesktop.blogbus.com/logs/74200705.html" target="_blank" rel="noopener noreferrer">SymPy简明教程</a>
  </p>
  
  <p>
    <strong>目录</strong>
  </p>
  
  <ul>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section">引言</a>
    </li>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#sympy">SymPy第一步</a> <ul>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#isympy">isympy控制台</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#sympy-1">用SymPy做计算器</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-1">符号</a>
        </li>
      </ul>
    </li>
    
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-2">代数</a>
    </li>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-3">演算</a> <ul>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-4">极限</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-5">微分</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-6">级数展开</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-7">求和</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-8">积分</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-9">复数</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-10">函数</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-11">微分方程</a>
        </li>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-12">代数方程</a>
        </li>
      </ul>
    </li>
    
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-13">线性代数</a> <ul>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-14">矩阵</a>
        </li>
      </ul>
    </li>
    
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-15">模式匹配</a>
    </li>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-16">打印</a> <ul>
        <li>
          <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-17">注意</a>
        </li>
      </ul>
    </li>
    
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-18">更多文档</a>
    </li>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-19">翻译</a>
    </li>
    <li>
      <a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#footnotes">FootNotes</a>
    </li>
  </ul>
  
  <h2 id="section">
    引言
  </h2>
  
  <p>
    SymPy是一个符号数学Python库。它的目标是成为一个全功能的计算机代数系统，同时保持代码的精简而易于理解和课扩展。SymPy完全由Python写成，不需要任何外部库。
  </p>
  
  <p>
    这个教程概述和简介SymPy。阅读它能让你知道SymPy可以为你做什么。如果你想了解更多，阅读<a class="external" href="http://docs.sympy.org/0.7.1/guide.html#guide" target="_blank" rel="noopener noreferrer">SymPy用户指南</a>和<a class="external" href="http://docs.sympy.org/0.7.1/modules/index.html#module-docs" target="_blank" rel="noopener noreferrer">SymPy模块参考</a>。或者直接阅读<a class="external" href="https://github.com/sympy/sympy/" target="_blank" rel="noopener noreferrer">源码</a>。
  </p>
  
  <h2 id="sympy">
    SymPy第一步
  </h2>
  
  <p>
    下载它最简单的方法是去<a class="external" href="http://code.google.com/p/sympy/" target="_blank" rel="noopener noreferrer">http://code.google.com/p/sympy/</a>从“推荐下载”下载最新的压缩包。<sup><a class="footnote" href="http://reverland.org/python/2012/08/30/sympy-tutorial/#fn:1">1</a></sup><span class="Apple-converted-space"> </span><img src="http://fmn.rrimg.com/fmn061/20120901/1800/p_large_M3yG_5d30000027c61261.jpg" alt="downloads" width="0" />
  </p>
  
  <p>
    解压：
  </p>
  
  <pre><code>tar xzf sympy-0.7.1.tar.gz </code></pre>
  
  <p>
    然后用Python解释器尝试它：
  </p>
  
  <pre><code>[lyy@arch ~]cd sympy-0.7.1 [lyy@arch ~]$ python2 Python 2.7.3 (default, Apr 24 2012, 00:00:54) [GCC 4.7.0 20120414 (prerelease)] on linux2 Type "help", "copyright", "credits" or "license" for more information. &gt;&gt;&gt; from sympy import Symbol, cos &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; (1/cos(x)).series(x, 0, 10) 1 + x**2/2 + 5*x**4/24 + 61*x**6/720 + 277*x**8/8064 + O(x**10) </code></pre>
  
  <p>
    你可以如上展示使用SymPy。如果你在你的程序中使用它的话，这确实是推荐的方法。你也可以用<code>./setup.py install</code>像所有其它Python模块一样安装它，或者仅仅在你心爱的发行版中安装相应的包，等等。
  </p>
  
  <p>
    <strong>在archlinux中安装SymPy</strong>
  </p>
  
  <pre><code>[lyy@arch ~]$ sudo pacman -S python2-sympy 警告：python2-sympy-0.7.1-4 已经为最新 -- 重新安装 正在解决依赖关系... 正在查找内部冲突... 目标 (1)： python2-sympy-0.7.1-4 全部安装大小：25.12 MiB 净更新大小：0.00 MiB 进行安装吗？ [Y/n] (1/1) 正在检查软件包完整性 [###############################] 100% (1/1) 正在加载软件包文件 [###############################] 100% (1/1) 正在检查文件冲突 [###############################] 100% (1/1) 正在检查可用硬盘空间 [###############################] 100% (1/1) 正在更新 python2-sympy </code></pre>
  
  <p>
    其它安装SymPy的方法，查阅SymPy主页上的<a class="external" href="http://code.google.com/p/sympy/wiki/DownloadInstallation?tm=2" target="_blank" rel="noopener noreferrer">下载</a>标签。
  </p>
  
  <h3 id="isympy">
    isympy控制台
  </h3>
  
  <p>
    为了试验新功能，或当搞清楚如何做事时，你可以使用我们对IPython的特殊封装<code>isympy</code>(它位于<code>/bin/isympy</code>中，如果你正在从源码文件夹运行的话)，它仅仅是一个已经导入相关sympy模块的标准python shell，定义了符号<code>x,y,z</code>和一些其它东西：
  </p>
  
  <pre><code>[lyy@arch ~]$ cd sympy [lyy@arch ~]$ ./bin/isympy IPython console for SymPy 0.7.1 (Python 2.7.3-64-bit) (ground types: python) These commands were executed: &gt;&gt;&gt; from __future__ import division &gt;&gt;&gt; from sympy import * &gt;&gt;&gt; x, y, z, t = symbols('x y z t') &gt;&gt;&gt; k, m, n = symbols('k m n', integer=True) &gt;&gt;&gt; f, g, h = symbols('f g h', cls=Function) Documentation can be found at http://www.sympy.org In [1]: (1/cos(x)).series(x, 0, 10) Out[1]: 2 4 6 8 x 5⋅x 61⋅x 277⋅x 1 + ── + ──── + ───── + ────── + O(x**10) 2 24 720 8064 </code></pre>
  
  <h3 id="sympy-1">
    用SymPy做计算器
  </h3>
  
  <p>
    SymPy有三种内建的数值类型：浮点数、有理数和整数。
  </p>
  
  <p>
    有理数类用一对整数表示一个有理数：分子和分母，所以<code>Rational(1,2)</code>代表1/2,<code>Rational(5,2)</code>代表5/2等等。
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import * &gt;&gt;&gt; a = Rational(1,2) &gt;&gt;&gt; a 1/2 &gt;&gt;&gt; a*2 1 &gt;&gt;&gt; Rational(2)**50/Rational(10)**50 1/88817841970012523233890533447265625 </code></pre>
  
  <p>
    当计算整型数据时小心处理，因为他们会截取整数部分。这就是为何：
  </p>
  
  <pre><code>&gt;&gt;&gt; 1/2 0 &gt;&gt;&gt; 1.0/2 0.5 </code></pre>
  
  <p>
    然而你可以这样做
  </p>
  
  <pre><code>&gt;&gt;&gt; from __future__ import division &gt;&gt;&gt; 1/2 0.5 </code></pre>
  
  <p>
    真正的除法将要成为python3k的标准，isympy中也是。
  </p>
  
  <p>
    我们也有些特殊的常数，像e和pi，它们被视为符号(1+pi将不被数值求解，它将保持为1+pi)，并且我们可以有任意精度：
  </p>
  
  <pre><code>&gt;&gt;&gt; pi**2 pi**2 &gt;&gt;&gt; pi.evalf() 3.14159265358979 &gt;&gt;&gt; (pi+exp(1)).evalf() 5.85987448204884 </code></pre>
  
  <p>
    就像你看到的，<code>evalf</code>将表达式求解为浮点数。
  </p>
  
  <p>
    这还有一个类表示数学上的无限，叫作<code>oo</code>：
  </p>
  
  <pre><code>&gt;&gt;&gt; oo &gt; 99999 True &gt;&gt;&gt; oo + 1 oo </code></pre>
  
  <h3 id="section-1">
    符号
  </h3>
  
  <p>
    和其它计算机代数系统相比，在SymPy中你不得不显式地声明符号变量：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import * &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; y = Symbol('y') </code></pre>
  
  <p>
    然后你可以使用它们：
  </p>
  
  <pre><code>&gt;&gt;&gt; x+y+x-y 2*x &gt;&gt;&gt; (x+y)**2 (x + y)**2 &gt;&gt;&gt; ((x+y)**2).expand() x**2 + 2*x*y + y**2 </code></pre>
  
  <p>
    使用<code>subs(old, new)</code>用其它符号和数代换它们：
  </p>
  
  <pre><code>&gt;&gt;&gt; ((x+y)**2).subs(x, 1) (y + 1)**2 &gt;&gt;&gt; ((x+y)**2).subs(x, y) 4*y**2 </code></pre>
  
  <p>
    对于剩余的教程，我们假设我们已经运行了：
  </p>
  
  <pre><code>&gt;&gt;&gt; import sys &gt;&gt;&gt; oldhook = sys.displayhook &gt;&gt;&gt; sys.displayhook = pprint </code></pre>
  
  <p>
    这样就有漂亮的打印。参见之后的<a href="http://reverland.org/python/2012/08/30/sympy-tutorial/#section-16">打印</a>部分。如果你安装了unicode字体，你的输出可能看起来有点不同。(将看起来稍微好些)
  </p>
  
  <h2 id="section-2">
    代数
  </h2>
  
  <p>
    对部分分式分解，使用<code>apart(expr, x)</code>：
  </p>
  
  <pre><code>&gt;&gt;&gt; 1/((x+2)*(x+1)) 1 ─────────────── (x + 1)⋅(x + 2) &gt;&gt;&gt; apart(1/((x+2)*(x+1)), x) 1 1 - ───── + ───── x + 2 x + 1 &gt;&gt;&gt; (x+1)/(x-1) x + 1 ───── x - 1 &gt;&gt;&gt; apart((x+1)/(x-1), x) 2 1 + ───── x - 1 </code></pre>
  
  <p>
    把它们重新结合起来，使用<code>together(expr, x)</code>：
  </p>
  
  <pre><code>&gt;&gt;&gt; z = Symbol('z') &gt;&gt;&gt; together(1/x + 1/y + 1/z) x⋅y + x⋅z + y⋅z ─────────────── x⋅y⋅z &gt;&gt;&gt; together(apart((x+1)/(x-1), x), x) x + 1 ───── x - 1 &gt;&gt;&gt; together(apart(1/( (x+2)*(x+1) ), x), x) 1 ─────────────── (x + 1)⋅(x + 2) </code></pre>
  
  <h2 id="section-3">
    演算
  </h2>
  
  <h3 id="section-4">
    极限
  </h3>
  
  <p>
    极限在sympy中使用很简单，它们的语法是<code>limit(function, variable, point)</code>，所以计算当x趋近于0时f(x)的极限，你可以给出<code>limit(f, x, 0)</code>：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import * &gt;&gt;&gt; x=Symbol("x") &gt;&gt;&gt; limit(sin(x)/x, x, 0) 1 </code></pre>
  
  <p>
    你也可以计算在无穷的极限：
  </p>
  
  <pre><code>&gt;&gt;&gt; limit(sin(x)/x,x,0) 1 &gt;&gt;&gt; limit(x,x,oo) ∞ 对于一些不寻常的极限例子，你可以阅读这个测试文件[test_demidovich.py](https://github.com/sympy/sympy/blob/master/sympy/series/tests/test_demidovich.py) </code></pre>
  
  <h3 id="section-5">
    微分
  </h3>
  
  <p>
    你可以使用<code>diff(func, var)</code>微分任何SymPy表达式。例如：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import * &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; diff(sin(x), x) cos(x) &gt;&gt;&gt; diff(sin(2*x), x) 2⋅cos(2⋅x) &gt;&gt;&gt; diff(tan(x), x) 2 tan (x) + 1 </code></pre>
  
  <p>
    你可以检查正确性：
  </p>
  
  <pre><code>&gt;&gt;&gt; limit((tan(x+y)-tan(x))/y, y, 0) 2 tan (x) + 1 </code></pre>
  
  <p>
    高阶微分可以使用<code>diff(func, var, n)</code>来计算：
  </p>
  
  <pre><code>&gt;&gt;&gt; diff(sin(2*x), x, 1) 2⋅cos(2⋅x) &gt;&gt;&gt; diff(sin(2*x), x, 2) -4⋅sin(2⋅x) &gt;&gt;&gt; diff(sin(2*x), x, 3) -8⋅cos(2⋅x) </code></pre>
  
  <h3 id="section-6">
    级数展开
  </h3>
  
  <p>
    使用<code>.series(var, point, order)</code>:
  </p>
  
  <pre><code>&gt;&gt;&gt; cos(x).series(x, 0, 10) 2 4 6 8 x x x x 1 - ── + ── - ─── + ───── + O(x**10) 2 24 720 40320 &gt;&gt;&gt; (1/cos(x)).series(x, 0, 10) 2 4 6 8 x 5⋅x 61⋅x 277⋅x 1 + ── + ──── + ───── + ────── + O(x**10) 2 24 720 8064 </code></pre>
  
  <p>
    另一个简单的例子：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Integral, Symbol, pprint &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; y = Symbol('y') &gt;&gt;&gt; e = 1/(x + y) &gt;&gt;&gt; s = e.series(x, 0, 5) &gt;&gt;&gt; print(s) 1/y - x/y**2 + x**2/y**3 - x**3/y**4 + x**4/y**5 + O(x**5) &gt;&gt;&gt; pprint(s) 2 3 4 1 x x x x ─ - ── + ── - ── + ── + O(x**5) y 2 3 4 5 y y y y None </code></pre>
  
  <h3 id="section-7">
    求和
  </h3>
  
  <p>
    计算给定求和变量界限的f的总和(Summation)。<sup><a class="footnote" href="http://reverland.org/python/2012/08/30/sympy-tutorial/#fn:2">2</a></sup>
  </p>
  
  <p>
    <code>summation(f, (i, a, b))</code>变量i从a到b计算f的和，也就是，
  </p>
  
  <pre><code> b ____  ` summation(f, (i, a, b)) = ) f /___, i = a </code></pre>
  
  <p>
    如果不能计算总和，它将打印相应的求和公式。求值可引入额外的极限计算：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import summation, oo, symbols, log &gt;&gt;&gt; i, n, m = symbols('i n m', integer=True) &gt;&gt;&gt; summation(2*i - 1, (i, 1, n)) 2 n &gt;&gt;&gt; summation(1/2**i, (i, 0, oo)) 2 &gt;&gt;&gt; summation(1/log(n)**n, (n, 2, oo)) ∞ ___  `  -n / log (n) /__, n = 2 &gt;&gt;&gt; summation(i, (i, 0, n), (n, 0, m)) 3 2 m m m ── + ── + ─ 6 2 3 &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; from sympy import factorial &gt;&gt;&gt; summation(x**n/factorial(n), (n, 0, oo)) x ℯ </code></pre>
  
  <h3 id="section-8">
    积分
  </h3>
  
  <p>
    通过<code>integrate()</code>功能(facility)，SymPy对基本和特殊函数定与不定积分有卓越的支持。 该功能使用有力的扩展Risch-Norman算法，启发算法和模式匹配：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import integrate, erf, exp, sin, log, oo, pi, sinh, symbols &gt;&gt;&gt; x, y = symbols('x,y') </code></pre>
  
  <p>
    你可以对基本函数积分：
  </p>
  
  <pre><code>&gt;&gt;&gt; integrate(6*x**5, x) 6 x &gt;&gt;&gt; integrate(sin(x), x) -cos(x) &gt;&gt;&gt; integrate(log(x), x) x⋅log(x) - x &gt;&gt;&gt; integrate(2*x + sinh(x), x) 2 x + cosh(x) </code></pre>
  
  <p>
    特殊函数也可以简单的处理：
  </p>
  
  <pre><code>&gt;&gt;&gt; integrate(exp(-x**2)*erf(x), x) ⎽⎽⎽ 2 ╲╱ π ⋅erf (x) ───────────── 4 </code></pre>
  
  <p>
    还可以计算定积分：
  </p>
  
  <pre><code>&gt;&gt;&gt; integrate(x**3, (x, -1, 1)) 0 &gt;&gt;&gt; integrate(sin(x), (x, 0, pi/2)) 1 &gt;&gt;&gt; integrate(cos(x), (x, -pi/2, pi/2)) 2 </code></pre>
  
  <p>
    反常积分也被支持：
  </p>
  
  <pre><code>&gt;&gt;&gt; integrate(exp(-x), (x, 0, oo)) 1 &gt;&gt;&gt; integrate(log(x), (x, 0, 1)) -1 </code></pre>
  
  <h3 id="section-9">
    复数
  </h3>
  
  <p>
    除了复数单元<code>I</code>是虚数，符号可以被用属性创建(例如 real,positive,complex,等等)这将影响它们的表现：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Symbol, exp, I &gt;&gt;&gt; x = Symbol('x') # a plain x with no attributes &gt;&gt;&gt; exp(I*x).expand() ⅈ⋅x ℯ &gt;&gt;&gt; exp(I*x).expand(complex=True) -im(x) -im(x) ⅈ⋅ℯ ⋅sin(re(x)) + ℯ ⋅cos(re(x)) &gt;&gt;&gt; x = Symbol('x', real=True) &gt;&gt;&gt; exp(I*x).expand(complex=True) ⅈ⋅sin(x) + cos(x) </code></pre>
  
  <h3 id="section-10">
    函数
  </h3>
  
  <p>
    <strong>三角函数:</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import asin, asinh, cos, sin, sinh, symbols, I &gt;&gt;&gt; x, y = symbols('x,y') &gt;&gt;&gt; sin(x+y).expand(trig=True) sin(x)⋅cos(y) + sin(y)⋅cos(x) &gt;&gt;&gt; cos(x+y).expand(trig=True) -sin(x)⋅sin(y) + cos(x)⋅cos(y) &gt;&gt;&gt; sin(I*x) ⅈ⋅sinh(x) &gt;&gt;&gt; sinh(I*x) ⅈ⋅sin(x) &gt;&gt;&gt; asinh(I) ⅈ⋅π ─── 2 &gt;&gt;&gt; asinh(I*x) ⅈ⋅asin(x) &gt;&gt;&gt; sin(x).series(x, 0, 10) 3 5 7 9 x x x x x - ── + ─── - ──── + ────── + O(x**10) 6 120 5040 362880 &gt;&gt;&gt; sinh(x).series(x, 0, 10) 3 5 7 9 x x x x x + ── + ─── + ──── + ────── + O(x**10) 6 120 5040 362880 &gt;&gt;&gt; asin(x).series(x, 0, 10) 3 5 7 9 x 3⋅x 5⋅x 35⋅x x + ── + ──── + ──── + ───── + O(x**10) 6 40 112 1152 &gt;&gt;&gt; asinh(x).series(x, 0, 10) 3 5 7 9 x 3⋅x 5⋅x 35⋅x x - ── + ──── - ──── + ───── + O(x**10) 6 40 112 1152 </code></pre>
  
  <p>
    <strong>球谐函数：</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Ylm &gt;&gt;&gt; from sympy.abc import theta, phi &gt;&gt;&gt; Ylm(1, 0, theta, phi) ⎽⎽⎽ ╲╱ 3 ⋅cos(θ) ──────────── ⎽⎽⎽ 2⋅╲╱ π &gt;&gt;&gt; Ylm(1, 1, theta, phi) ⎽⎽⎽ ⅈ⋅φ -╲╱ 6 ⋅ℯ ⋅sin(θ) ────────────────── ⎽⎽⎽ 4⋅╲╱ π &gt;&gt;&gt; Ylm(2, 1, theta, phi) ⎽⎽⎽⎽ ⅈ⋅φ -╲╱ 30 ⋅ℯ ⋅sin(θ)⋅cos(θ) ────────────────────────── ⎽⎽⎽ 4⋅╲╱ π </code></pre>
  
  <p>
    <strong>阶乘和伽马函数：</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import factorial, gamma, Symbol &gt;&gt;&gt; x = Symbol("x") &gt;&gt;&gt; n = Symbol("n", integer=True) &gt;&gt;&gt; factorial(x) x! &gt;&gt;&gt; factorial(n) n! &gt;&gt;&gt; gamma(x + 1).series(x, 0, 3) # i.e. factorial(x) 2 2 2 2 π ⋅x EulerGamma ⋅x 1 - EulerGamma⋅x + ───── + ────────────── + O(x**3) 12 2 </code></pre>
  
  <p>
    <strong>zeta函数：</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import zeta &gt;&gt;&gt; zeta(4, x) ζ(4, x) &gt;&gt;&gt; zeta(4, 1) 4 π ── 90 &gt;&gt;&gt; zeta(4, 2) 4 π -1 + ── 90 &gt;&gt;&gt; zeta(4, 3) 4 17 π - ── + ── 16 90 </code></pre>
  
  <p>
    <strong>多项式：</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import assoc_legendre, chebyshevt, legendre, hermite &gt;&gt;&gt; chebyshevt(2, x) 2 2⋅x - 1 &gt;&gt;&gt; chebyshevt(4, x) 4 2 8⋅x - 8⋅x + 1 &gt;&gt;&gt; legendre(2, x) 2 3⋅x 1 ──── - ─ 2 2 &gt;&gt;&gt; legendre(8, x) 8 6 4 2 6435⋅x 3003⋅x 3465⋅x 315⋅x 35 ─────── - ─────── + ─────── - ────── + ─── 128 32 64 32 128 &gt;&gt;&gt; assoc_legendre(2, 1, x) ⎽⎽⎽⎽⎽⎽⎽⎽⎽⎽ ╱ 2 -3⋅x⋅╲╱ - x + 1 &gt;&gt;&gt; assoc_legendre(2, 2, x) 2 - 3⋅x + 3 &gt;&gt;&gt; hermite(3, x) 3 8⋅x - 12⋅x </code></pre>
  
  <h3 id="section-11">
    微分方程
  </h3>
  
  <p>
    在 isympy中：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Function, Symbol, dsolve &gt;&gt;&gt; f = Function('f') &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; f(x).diff(x, x) + f(x) 2 d f(x) + ───(f(x)) 2 dx &gt;&gt;&gt; dsolve(f(x).diff(x, x) + f(x), f(x)) f(x) = C₁⋅cos(x) + C₂⋅sin(x) </code></pre>
  
  <h3 id="section-12">
    代数方程
  </h3>
  
  <p>
    在isympy中：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import solve, symbols &gt;&gt;&gt; x, y = symbols('x,y') &gt;&gt;&gt; solve(x**4 - 1, x) [1, -1, -ⅈ, ⅈ] &gt;&gt;&gt; solve([x + 5*y - 2, -3*x + 6*y - 15], [x, y]) {x: -3, y: 1} </code></pre>
  
  <h2 id="section-13">
    线性代数
  </h2>
  
  <h3 id="section-14">
    矩阵
  </h3>
  
  <p>
    矩阵从Matrix类创建：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Matrix, Symbol &gt;&gt;&gt; Matrix([[1,0], [0,1]]) ⎡1 0⎤ ⎢ ⎥ ⎣0 1⎦ </code></pre>
  
  <p>
    它可以包含符号：
  </p>
  
  <pre><code>&gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; y = Symbol('y') &gt;&gt;&gt; A = Matrix([[1,x], [y,1]]) &gt;&gt;&gt; A ⎡1 x⎤ ⎢ ⎥ ⎣y 1⎦ &gt;&gt;&gt; A**2 ⎡x⋅y + 1 2⋅x ⎤ ⎢ ⎥ ⎣ 2⋅y x⋅y + 1⎦ </code></pre>
  
  <p>
    更多有关矩阵信息，参见线性代数教程。
  </p>
  
  <h2 id="section-15">
    模式匹配
  </h2>
  
  <p>
    使用<code>.match()</code>方法，和Wild类对表达式实行模式匹配。这个方法将返回一个发生替换的字典，如下：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Symbol, Wild &gt;&gt;&gt; x = Symbol('x') &gt;&gt;&gt; p = Wild('p') &gt;&gt;&gt; (5*x**2).match(p*x**2) {p: 5} &gt;&gt;&gt; q = Wild('q') &gt;&gt;&gt; (x**2).match(p*x**q) {p: 1, q: 2} </code></pre>
  
  <p>
    如果匹配失败，将返回<code>None</code>：
  </p>
  
  <pre><code>&gt;&gt;&gt; print (x+1).match(p**x) None </code></pre>
  
  <p>
    可以指定<code>Wild</code>类的排除参数去保证一些东西不出现在结果之中：
  </p>
  
  <pre><code>&gt;&gt;&gt; p = Wild('p', exclude=[1,x]) &gt;&gt;&gt; print (x+1).match(x+p) # 1 is excluded None &gt;&gt;&gt; print (x+1).match(p+1) # x is excluded None &gt;&gt;&gt; print (x+1).match(x+2+p) # -1 is not excluded {p_: -1} </code></pre>
  
  <h2 id="section-16">
    打印
  </h2>
  
  <p>
    这里有许多打印表达式的方法：
  </p>
  
  <p>
    <strong>标准</strong>
  </p>
  
  <p>
    这就是<code>str(expression)</code>返回的，看起来想这样：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Integral &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; print x**2 x**2 &gt;&gt;&gt; print 1/x 1/x &gt;&gt;&gt; print Integral(x**2, x) Integral(x**2, x) </code></pre>
  
  <p>
    <strong>漂亮的打印</strong>
  </p>
  
  <p>
    <code>pprint</code>函数产生好看的ascii艺术打印：
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Integral, pprint &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; pprint(x**2) 2 x None &gt;&gt;&gt; pprint(1/x) 1 ─ x None &gt;&gt;&gt; pprint(Integral(x**2, x)) ⌠ ⎮ 2 ⎮ x dx ⌡ None </code></pre>
  
  <p>
    如果你安装了unicode字体，<code>pprint</code>函数将默认使用它。你可以使用<code>use_unicode</code>函数改变这个选项。：
  </p>
  
  <pre><code>&gt;&gt;&gt; pprint(Integral(x**2, x), use_unicode=False) / | | 2 | x dx | / None </code></pre>
  
  <p>
    更多好看的unicode打印另见维基<a class="external" href="https://github.com/sympy/sympy/wiki/Pretty-Printing" target="_blank" rel="noopener noreferrer">Pretty Printing</a>。
  </p>
  
  <p>
    小技巧：在Python解释器中默认使用漂亮的打印，使用：
  </p>
  
  <pre><code>$ python Python 2.5.2 (r252:60911, Jun 25 2008, 17:58:32) [GCC 4.3.1] on linux2 Type "help", "copyright", "credits" or "license" for more information. &gt;&gt;&gt; from sympy import init_printing, var, Integral &gt;&gt;&gt; init_printing(use_unicode=False, wrap_line=False, no_global=True) &gt;&gt;&gt; var("x") x &gt;&gt;&gt; x**3/3 3 x -- 3 &gt;&gt;&gt; Integral(x**2, x) #doctest: +NORMALIZE_WHITESPACE / | | 2 | x dx | / </code></pre>
  
  <p>
    <strong>Python打印</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy.printing.python import python &gt;&gt;&gt; from sympy import Integral &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; print python(x**2) x = Symbol('x') e = x**2 &gt;&gt;&gt; print python(1/x) x = Symbol('x') e = 1/x &gt;&gt;&gt; print python(Integral(x**2, x)) x = Symbol('x') e = Integral(x**2, x) </code></pre>
  
  <p>
    <strong>LaTeX打印</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Integral, latex &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; latex(x**2) x^{2} &gt;&gt;&gt; latex(x**2, mode='inline') $x^{2}$ &gt;&gt;&gt; latex(x**2, mode='equation') begin{equation}x^{2}end{equation} &gt;&gt;&gt; latex(x**2, mode='equation*') begin{equation*}x^{2}end{equation*} &gt;&gt;&gt; latex(1/x) frac{1}{x} &gt;&gt;&gt; latex(Integral(x**2, x)) int x^{2},dx </code></pre>
  
  <p>
    <strong>MathML</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy.printing.mathml import mathml &gt;&gt;&gt; from sympy import Integral, latex &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; print mathml(x**2) &lt;apply&gt;&lt;power/&gt;&lt;ci&gt;x&lt;/ci&gt;&lt;cn&gt;2&lt;/cn&gt;&lt;/apply&gt; &gt;&gt;&gt; print mathml(1/x) &lt;apply&gt;&lt;power/&gt;&lt;ci&gt;x&lt;/ci&gt;&lt;cn&gt;-1&lt;/cn&gt;&lt;/apply&gt; </code></pre>
  
  <p>
    <strong>Pylet</strong>
  </p>
  
  <pre><code>&gt;&gt;&gt; from sympy import Integral, preview &gt;&gt;&gt; from sympy.abc import x &gt;&gt;&gt; preview(Integral(x**2, x)) This is pdfTeX, Version 3.1415926-2.4-1.40.13 (TeX Live 2012/Arch Linux) restricted write18 enabled. entering extended mode (/tmp/tmpGYREx_.tex LaTeX2e &lt;2011/06/27&gt; Babel &lt;v3.8m&gt; and hyphenation patterns for english, dumylang, nohyphenation, ge rman-x-2012-05-30, ngerman-x-2012-05-30, afrikaans, ancientgreek, ibycus, arabi c, armenian, basque, bulgarian, catalan, pinyin, coptic, croatian, czech, danis h, dutch, ukenglish, usenglishmax, esperanto, estonian, ethiopic, farsi, finnis h, french, friulan, galician, german, ngerman, swissgerman, monogreek, greek, h ungarian, icelandic, assamese, bengali, gujarati, hindi, kannada, malayalam, ma rathi, oriya, panjabi, tamil, telugu, indonesian, interlingua, irish, italian, kurmanji, latin, latvian, lithuanian, mongolian, mongolianlmc, bokmal, nynorsk, polish, portuguese, romanian, romansh, russian, sanskrit, serbian, serbianc, s lovak, slovenian, spanish, swedish, turkish, turkmen, ukrainian, uppersorbian, welsh, loaded. (/usr/share/texmf-dist/tex/latex/base/article.cls Document Class: article 2007/10/19 v1.4h Standard LaTeX document class (/usr/share/texmf-dist/tex/latex/base/size12.clo)) (/usr/share/texmf-dist/tex/latex/amsmath/amsmath.sty For additional information on amsmath, use the `?' option. (/usr/share/texmf-dist/tex/latex/amsmath/amstext.sty (/usr/share/texmf-dist/tex/latex/amsmath/amsgen.sty)) (/usr/share/texmf-dist/tex/latex/amsmath/amsbsy.sty) (/usr/share/texmf-dist/tex/latex/amsmath/amsopn.sty)) (/usr/share/texmf-dist/tex/latex/eulervm/eulervm.sty) No file tmpGYREx_.aux. (/usr/share/texmf-dist/tex/latex/eulervm/uzeur.fd) (/usr/share/texmf-dist/tex/latex/eulervm/uzeus.fd) (/usr/share/texmf-dist/tex/latex/eulervm/uzeuex.fd) [1] (./tmpGYREx_.aux) ) Output written on tmpGYREx_.dvi (1 page, 320 bytes). Transcript written on tmpGYREx_.log. This is dvipng 1.14 Copyright 2002-2010 Jan-Ake Larsson [1] </code></pre>
  
  <p>
    如果pyglet被安装了，一个包含LaTeX渲染后表达式的pyglet窗口将被打开：
  </p>
  
  <p>
    <img src="http://fmn.rrimg.com/fmn059/20120903/1210/p_large_ViwY_2fcc000000bf1262.jpg" alt="pyglet" width="0" />
  </p>
  
  <h3 id="section-17">
    注意
  </h3>
  
  <p>
    isympy自动调用<code>pprint</code>,这就是为什么默认情况下你看到的是漂亮的打印。
  </p>
  
  <p>
    注意有一个可用的打印模块<code>sympy.printing</code>。其它通过这个模块的打印方法是：
  </p>
  
  <ul>
    <li>
      <code>pretty(expr)</code>,<code>pretty_print(expr)</code>,<code>pprint(expr)</code>:分别漂亮的表示<code>expr</code>.这是和之前描述的第二层表示是一样的。
    </li>
    <li>
      <code>latex(expr)</code>,<span class="Apple-converted-space"> </span><code>print_latex(expr)</code>：分别返回和打印<code>expr</code>的<a class="external" href="http://www.latex-project.org/" target="_blank" rel="noopener noreferrer">LaTeX</a>表示。
    </li>
    <li>
      <code>mathml(expr)</code>,<code>print_mathml(expr)</code>：分别返回和打印<code>expr</code>的<a class="external" href="http://www.w3.org/Math/" target="_blank" rel="noopener noreferrer">MathML</a>表示。
    </li>
    <li>
      <code>print_gtk(expr)</code>：在<a class="external" href="http://helm.cs.unibo.it/mml-widget/" target="_blank" rel="noopener noreferrer">Gtkmathview</a>打印<code>expr</code>，这是一个呈现MathML代码的GTK部件。<a class="external" href="http://helm.cs.unibo.it/mml-widget/" target="_blank" rel="noopener noreferrer">Gtkmathview</a>要求安装。
    </li>
  </ul>
  
  <h2 id="section-18">
    更多文档
  </h2>
  
  <p>
    现在该学更多有关SymPy的知识了。浏览<a class="external" href="http://docs.sympy.org/dev/guide.html#guide" target="_blank" rel="noopener noreferrer">SymPy用户指南</a>和<a class="external" href="http://docs.sympy.org/dev/modules/index.html#module-docs" target="_blank" rel="noopener noreferrer">SymPy模块参考</a>。
  </p>
  
  <p>
    一定也浏览我们的公共<a class="external" href="http://wiki.sympy.org/" target="_blank" rel="noopener noreferrer">wiki.sympy.org</a>，那里包含了很多我们和我们的用户贡献的示例，教程，cookbook，请自由地编辑它。
  </p>
  
  <h2 id="section-19">
    翻译
  </h2>
  
  <p>
    这个教程还有其它语言：
  </p>
  
  <p>
    <a class="external" href="http://docs.sympy.org/dev/tutorial.de.html" target="_blank" rel="noopener noreferrer">德语</a>
  </p>
  
  <hr />
  
  <h2 id="footnotes">
    FootNotes
  </h2>
  
  <div class="footnotes">
    <ol>
      <li>
        不介意非稳定版我觉得git更方便一些，当然linux包管理器更方便,所以先用你的包管理器安装它。<span class="Apple-converted-space"> </span><a class="reversefootnote" href="http://reverland.org/python/2012/08/30/sympy-tutorial/#fnref:1">↩</a>
      </li>
      <li>
        Compute the summation of f with respect to the given summation variable over the given limits.<span class="Apple-converted-space"> </span><a class="reversefootnote" href="http://reverland.org/python/2012/08/30/sympy-tutorial/#fnref:2">↩</a>
      </li>
    </ol>
  </div>
</div>