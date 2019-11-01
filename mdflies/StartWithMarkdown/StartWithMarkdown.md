<font face = 等线>

# <a id='0'>Markdown基本语法</a>

<article class="_2rhmJa"><p>Markdown是一种纯文本格式的标记语言。通过简单的标记语法，它可以使普通文本内容具有一定的格式。</p>
<p>相比WYSIWYG编辑器</p>
<p><strong>优点：</strong><br>
1、因为是纯文本，所以只要支持Markdown的地方都能获得一样的编辑效果，可以让作者摆脱排版的困扰，专心写作。<br>
2、操作简单。比如:WYSIWYG编辑时标记个标题，先选中内容，再点击导航栏的标题按钮，选择几级标题。要三个步骤。而Markdown只需要在标题内容前加#即可</p>
<p><strong>缺点：</strong><br>
1、需要记一些语法（当然，是很简单。五分钟学会）。<br>
2、有些平台不支持Markdown编辑模式。</p>
<p>还好，简书是支持Markdown编辑模式的。</p>
<pre class="line-numbers  language-rust"><code class="  language-rust">开启方式：设置<span class="token punctuation">-&gt;</span>默认编辑器<span class="token punctuation">-&gt;</span>Markdown编辑器
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<h1>一、标题</h1>
<p>在想要设置为标题的文字前面加#来表示<br>
一个#是一级标题，二个#是二级标题，以此类推。支持六级标题。</p>
<p>注：标准语法一般在#后跟个空格再写文字，貌似简书不加空格也行。</p>
<p>示例：</p>
<pre class="line-numbers  language-bash"><code class="  language-bash"># 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
<h4>这是四级标题</h4>
<h5>这是五级标题</h5>
<h6>这是六级标题</h6>
<hr>
<h1>二、字体</h1>
<ul>
<li>
<h5>加粗</h5>
</li>
</ul>
<p>要加粗的文字左右分别用两个*号包起来</p>
<ul>
<li>
<h5>斜体</h5>
</li>
</ul>
<p>要倾斜的文字左右分别用一个*号包起来</p>
<ul>
<li>
<h5>斜体加粗</h5>
</li>
</ul>
<p>要倾斜和加粗的文字左右分别用三个*号包起来</p>
<ul>
<li>
<h5>删除线</h5>
</li>
</ul>
<p>要加删除线的文字左右分别用两个~~号包起来</p>
<p>示例：</p>
<pre class="line-numbers  language-undefined"><code class="  language-undefined">**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<p><strong>这是加粗的文字</strong><br>
<em>这是倾斜的文字</em><br>
<strong><em>这是斜体加粗的文字</em></strong><br>
<del>这是加删除线的文字</del></p>
<hr>
<h1>三、引用</h1>
<p>在引用的文字前加&gt;即可。引用也可以嵌套，如加两个&gt;&gt;三个&gt;&gt;&gt;<br>
n个...<br>
貌似可以一直加下去，但没神马卵用</p>
<p>示例：</p>
<pre class="line-numbers  language-ruby"><code class="  language-ruby"><span class="token operator">&gt;</span>这是引用的内容
<span class="token operator">&gt;</span><span class="token operator">&gt;</span>这是引用的内容
<span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span><span class="token operator">&gt;</span>这是引用的内容
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<blockquote>
<p>这是引用的内容</p>
<blockquote>
<p>这是引用的内容</p>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<blockquote>
<p>这是引用的内容</p>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
<h1>四、分割线</h1>
<p>三个或者三个以上的 - 或者 * 都可以。</p>
<p>示例：</p>
<pre class="line-numbers  language-undefined"><code class="  language-undefined">---
----
***
*****
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：<br>
可以看到，显示效果是一样的。</p>
<hr>
<hr>
<hr>
<hr>
<h1>五、图片</h1>
<p>语法：</p>
<pre class="line-numbers  language-bash"><code class="  language-bash">![图片alt](图片地址 ''图片title'')

图片alt就是显示在图片下面的文字，相当于对图片内容的解释。
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>示例：</p>
<pre class="line-numbers  language-cpp"><code class="  language-cpp"><span class="token operator">!</span><span class="token punctuation">[</span>blockchain<span class="token punctuation">]</span><span class="token punctuation">(</span>https<span class="token operator">:</span><span class="token operator">/</span><span class="token operator">/</span>ss0<span class="token punctuation">.</span>bdstatic<span class="token punctuation">.</span>com<span class="token operator">/</span><span class="token number">70</span>cFvHSh_Q1YnxGkpoWK1HF6hhy<span class="token operator">/</span>it<span class="token operator">/</span>
u<span class="token operator">=</span><span class="token number">702257389</span><span class="token punctuation">,</span><span class="token number">1274025419</span><span class="token operator">&amp;</span>fm<span class="token operator">=</span><span class="token number">27</span><span class="token operator">&amp;</span>gp<span class="token operator">=</span><span class="token number">0.</span>jpg <span class="token string">"区块链"</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>

![](https://upload-images.jianshu.io/upload_images/6860761-fd2f51090a890873.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/550/format/webp)

<p><strong>上传本地图片直接点击导航栏的图片标志，选择图片即可</strong></p>
<h1>六、超链接</h1>
<p>语法：</p>
<pre class="line-numbers  language-csharp"><code class="  language-csharp"><span class="token punctuation">[</span>超链接名<span class="token punctuation">]</span><span class="token punctuation">(</span>超链接地址 <span class="token string">"超链接title"</span><span class="token punctuation">)</span>
title可加可不加
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>示例：</p>
<pre class="line-numbers  language-csharp"><code class="  language-csharp"><span class="token punctuation">[</span>简书<span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>jianshu<span class="token punctuation">.</span>com<span class="token punctuation">)</span>
<span class="token punctuation">[</span>百度<span class="token punctuation">]</span><span class="token punctuation">(</span>http<span class="token punctuation">:</span><span class="token operator">/</span><span class="token operator">/</span>baidu<span class="token punctuation">.</span>com<span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<p><a href="https://www.jianshu.com/u/1f5ac0cf6a8b" target="_blank">简书</a><br>
<a href="http://baidu.com" target="_blank" rel="nofollow">百度</a></p>
<p>注：Markdown本身语法不支持链接在新页面中打开，貌似简书做了处理，是可以的。别的平台可能就不行了，如果想要在新页面中打开的话可以用html语言的a标签代替。</p>
<pre class="line-numbers  language-xml"><code class="  language-xml"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>a</span> <span class="token attr-name">href</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>超链接地址<span class="token punctuation">"</span></span> <span class="token attr-name">target</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>_blank<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>超链接名<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>a</span><span class="token punctuation">&gt;</span></span>

示例
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>a</span> <span class="token attr-name">href</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>https://www.jianshu.com/u/1f5ac0cf6a8b<span class="token punctuation">"</span></span> <span class="token attr-name">target</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>_blank<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>简书<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>a</span><span class="token punctuation">&gt;</span></span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<hr>
<h1>七、列表</h1>
<ul>
<li>
<h5>无序列表</h5>
</li>
</ul>
<p>语法：<br>
无序列表用 - + * 任何一种都可以</p>
<pre class="line-numbers  language-undefined"><code class="  language-undefined">- 列表内容
+ 列表内容
* 列表内容

注意：- + * 跟内容之间都要有一个空格

<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<ul>
<li>列表内容</li>
</ul>
<ul>
<li>列表内容</li>
</ul>
<ul>
<li>列表内容</li>
</ul>
<ul>
<li>
<h5>有序列表</h5>
</li>
</ul>
<p>语法：<br>
数字加点</p>
<pre class="line-numbers  language-undefined"><code class="  language-undefined">1.列表内容
2.列表内容
3.列表内容

注意：序号跟内容之间要有空格
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<p>1.列表内容<br>
2.列表内容<br>
3.列表内容</p>
<ul>
<li>
<h5>列表嵌套</h5>
</li>
</ul>
<p><strong>上一级和下一级之间敲三个空格即可</strong></p>
<ul>
<li>
<p>一级无序列表内容</p>
<ul>
<li>二级无序列表内容</li>
<li>二级无序列表内容</li>
<li>二级无序列表内容</li>
</ul>
</li>
<li>
<p>一级无序列表内容</p>
<ol>
<li>二级有序列表内容</li>
<li>二级有序列表内容</li>
<li>二级有序列表内容</li>
</ol>
</li>
</ul>
<ol>
<li>
<p>一级有序列表内容</p>
<ul>
<li>二级无序列表内容</li>
<li>二级无序列表内容</li>
<li>二级无序列表内容</li>
</ul>
</li>
<li>
<p>一级有序列表内容</p>
<ol>
<li>二级有序列表内容</li>
<li>二级有序列表内容</li>
<li>二级有序列表内容</li>
</ol>
</li>
</ol>
<hr>
<h1>八、表格</h1>
<p>语法：</p>
<pre class="line-numbers  language-ruby"><code class="  language-ruby">表头<span class="token operator">|</span>表头<span class="token operator">|</span>表头
<span class="token operator">--</span><span class="token operator">-</span><span class="token operator">|</span><span class="token punctuation">:</span><span class="token operator">--</span><span class="token punctuation">:</span><span class="token operator">|</span><span class="token operator">--</span><span class="token operator">-</span><span class="token punctuation">:</span>
内容<span class="token operator">|</span>内容<span class="token operator">|</span>内容
内容<span class="token operator">|</span>内容<span class="token operator">|</span>内容

第二行分割表头和内容。
<span class="token operator">-</span> 有一个就行，为了对齐，多加了几个
文字默认居左
<span class="token operator">-</span>两边加：表示文字居中
<span class="token operator">-</span>右边加：表示文字居右
注：原生的语法两边都要用 <span class="token operator">|</span> 包起来。此处省略
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>示例：</p>
<pre class="line-numbers  language-ruby"><code class="  language-ruby">姓名<span class="token operator">|</span>技能<span class="token operator">|</span>排行
<span class="token operator">--</span><span class="token operator">|</span><span class="token punctuation">:</span><span class="token operator">--</span><span class="token punctuation">:</span><span class="token operator">|</span><span class="token operator">--</span><span class="token punctuation">:</span>
刘备<span class="token operator">|</span>哭<span class="token operator">|</span>大哥
关羽<span class="token operator">|</span>打<span class="token operator">|</span>二哥
张飞<span class="token operator">|</span>骂<span class="token operator">|</span>三弟
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<table>
<thead>
<tr>
<th>姓名</th>
<th style="text-align:center">技能</th>
<th style="text-align:right">排行</th>
</tr>
</thead>
<tbody>
<tr>
<td>刘备</td>
<td style="text-align:center">哭</td>
<td style="text-align:right">大哥</td>
</tr>
<tr>
<td>关羽</td>
<td style="text-align:center">打</td>
<td style="text-align:right">二哥</td>
</tr>
<tr>
<td>张飞</td>
<td style="text-align:center">骂</td>
<td style="text-align:right">三弟</td>
</tr>
</tbody>
</table>
<h1>九、代码</h1>
<p>语法：<br>
单行代码：代码之间分别用一个反引号包起来</p>
<pre class="line-numbers  language-go"><code class="  language-go">    <span class="token string">`代码内容`</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行</p>
<pre class="line-numbers  language-go"><code class="  language-go"><span class="token punctuation">(</span><span class="token string">``</span><span class="token string">`)
  代码...
  代码...
  代码...
(`</span><span class="token string">``</span><span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<blockquote>
<p>注：为了防止转译，前后三个反引号处加了小括号，实际是没有的。这里只是用来演示，实际中去掉两边小括号即可。</p>
</blockquote>
<p>示例：</p>
<p>单行代码</p>
<pre class="line-numbers  language-go"><code class="  language-go"><span class="token string">`create database hero;`</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>代码块</p>
<pre class="line-numbers  language-kotlin"><code class="  language-kotlin"><span class="token punctuation">(</span>```<span class="token punctuation">)</span>
    function <span class="token keyword">fun</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
         echo <span class="token string">"这是一句非常牛逼的代码"</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
    <span class="token keyword">fun</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">(</span>```<span class="token punctuation">)</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：</p>
<p>单行代码</p>
<p><code>create database hero;</code></p>
<p>代码块</p>
<pre class="line-numbers  language-kotlin"><code class="  language-kotlin">function <span class="token keyword">fun</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">{</span>
  echo <span class="token string">"这是一句非常牛逼的代码"</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>
<span class="token keyword">fun</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<h1>十、流程图</h1>
<pre class="line-numbers  language-php"><code class="  language-php">```flow
st<span class="token operator">=</span><span class="token operator">&gt;</span>start<span class="token punctuation">:</span> 开始
op<span class="token operator">=</span><span class="token operator">&gt;</span>operation<span class="token punctuation">:</span> My Operation
cond<span class="token operator">=</span><span class="token operator">&gt;</span>condition<span class="token punctuation">:</span> Yes <span class="token keyword">or</span> No<span class="token operator">?</span>
e<span class="token operator">=</span><span class="token operator">&gt;</span>end
st<span class="token operator">-</span><span class="token operator">&gt;</span><span class="token property">op</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token property">cond</span>
<span class="token function">cond</span><span class="token punctuation">(</span>yes<span class="token punctuation">)</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token property">e</span>
<span class="token function">cond</span><span class="token punctuation">(</span>no<span class="token punctuation">)</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token property">op</span>
<span class="token operator">&amp;</span>```
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code><button class="VJbwyy" type="button" aria-label="复制代码"><i aria-label="icon: copy" class="anticon anticon-copy"><svg viewBox="64 64 896 896" focusable="false" class="" data-icon="copy" width="1em" height="1em" fill="currentColor" aria-hidden="true"><path d="M832 64H296c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h496v688c0 4.4 3.6 8 8 8h56c4.4 0 8-3.6 8-8V96c0-17.7-14.3-32-32-32zM704 192H192c-17.7 0-32 14.3-32 32v530.7c0 8.5 3.4 16.6 9.4 22.6l173.3 173.3c2.2 2.2 4.7 4 7.4 5.5v1.9h4.2c3.5 1.3 7.2 2 11 2H704c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32zM350 856.2L263.9 770H350v86.2zM664 888H414V746c0-22.1-17.9-40-40-40H232V264h432v624z"></path></svg></i></button></pre>
<p>效果如下：<br>
简书不支持流程图，所以截了个图</p>

![](https://upload-images.jianshu.io/upload_images/6860761-9d9524ba31047696.png?imageMogr2/auto-orient/strip|imageView2/2/w/751/format/webp)

</article>

内容来自简书，[原文链接](https://www.jianshu.com/p/191d1e21f7ed?tdsourcetag=s_pctim_aiomsg)

[![返回顶端](https://s2.ax1x.com/2019/10/30/K4zn8f.png)](#0)

[![backToIndex](https://s2.ax1x.com/2019/10/29/KfK1e0.png)](https://github.com/GUET-CSSTA-GC/ORG-POLICY#)

</font>