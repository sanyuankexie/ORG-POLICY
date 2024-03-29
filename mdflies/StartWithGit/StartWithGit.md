<font face = 等线>

![gitLogo](https://s2.ax1x.com/2019/10/30/KhqyRJ.png)  

[![backToIndex](https://s2.ax1x.com/2019/10/29/KfK1e0.png)](https://github.com/GUET-CSSTA-GC/ORG-POLICY#)

# 开始了解git


## <a id='0'>点击目录跳转到：</a>

[Git简介](#1)  
[Git的诞生](#2)  
[集中式VS分布式](#3)  
[安装Git](#4)  
[创建版本库](#5)  
[时光机穿梭](#6)  
[版本回退](#7)  
[工作区和暂存区](#8)  
[管理修改](#9)  
[撤销修改](#10)  
[删除文件](#11)  
[远程仓库](#12)  
[添加远程仓库](#13)  
[从远程仓库克隆](#14)  
[分支管理](#15)  
[创建和合并分支](#16)  
[解决冲突](#17)  
[分支管理策略](#18)  
[Bug分支](#19)  
[Feature分支](#20)  
[多人协作](#21)  
[变基](#22)  
[标签管理](#23)  
[创建标签](#24)  
[操作标签](#25)  
[使用GitHub](#26)  
[自定义Git](#27)  
[忽略特殊文件](#28)  
[提问-答疑区](#29)

---

## <a id='1'>Git简介</a>

Git是什么？

Git是目前世界上最先进的分布式版本控制系统（没有之一）。

Git有什么特点？简单来说就是：高端大气上档次！

那什么是版本控制系统？

如果你用Microsoft Word写过长篇大论，那你一定有这样的经历：

想删除一个段落，又怕将来想恢复找不回来怎么办？有办法，先把当前文件“另存为……”一个新的Word文件，再接着改，改到一定程度，再“另存为……”一个新文件，这样一直改下去，最后你的Word文档变成了这样：

![](https://www.liaoxuefeng.com/files/attachments/918921393733152/0)

过了一周，你想找回被删除的文字，但是已经记不清删除前保存在哪个文件里了，只好一个一个文件去找，真麻烦。

看着一堆乱七八糟的文件，想保留最新的一个，然后把其他的删掉，又怕哪天会用上，还不敢删，真郁闷。

更要命的是，有些部分需要你的财务同事帮助填写，于是你把文件Copy到U盘里给她（也可能通过Email发送一份给她），然后，你继续修改Word文件。一天后，同事再把Word文件传给你，此时，你必须想想，发给她之后到你收到她的文件期间，你作了哪些改动，得把你的改动和她的部分合并，真困难。

于是你想，如果有一个软件，不但能自动帮我记录每次文件的改动，还可以让同事协作编辑，这样就不用自己管理一堆类似的文件了，也不需要把文件传来传去。如果想查看某次改动，只需要在软件里瞄一眼就可以，岂不是很方便？

这个软件用起来就应该像这个样子，能记录每次文件的改动：

<table class="uk-table">
<thead>
<tr><th>版本</th><th>文件名</th><th>用户</th><th>说明</th><th>日期</th></tr>
</thead>
<tbody>
<tr><td>1</td><td>service.doc</td><td>张三</td><td>删除了软件服务条款5</td><td>7/12 10:38</td></tr>
<tr><td>2</td><td>service.doc</td><td>张三</td><td>增加了License人数限制</td><td>7/12 18:09</td></tr>
<tr><td>3</td><td>service.doc</td><td>李四</td><td>财务部门调整了合同金额</td><td>7/13 9:51</td></tr>
<tr><td>4</td><td>service.doc</td><td>张三</td><td>延长了免费升级周期</td><td>7/14 15:17</td></tr>
</tbody>
</table>

这样，你就结束了手动管理多个“版本”的史前时代，进入到版本控制的20世纪。

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='2'>Git的诞生</a>

很多人都知道，Linus在1991年创建了开源的Linux，从此，Linux系统不断发展，已经成为最大的服务器系统软件了。

Linus虽然创建了Linux，但Linux的壮大是靠全世界热心的志愿者参与的，这么多人在世界各地为Linux编写代码，那Linux的代码是如何管理的呢？

事实是，在2002年以前，世界各地的志愿者把源代码文件通过diff的方式发给Linus，然后由Linus本人通过手工方式合并代码！

你也许会想，为什么Linus不把Linux代码放到版本控制系统里呢？不是有CVS、SVN这些免费的版本控制系统吗？因为Linus坚定地反对CVS和SVN，这些集中式的版本控制系统不但速度慢，而且必须联网才能使用。有一些商用的版本控制系统，虽然比CVS、SVN好用，但那是付费的，和Linux的开源精神不符。

不过，到了2002年，Linux系统已经发展了十年了，代码库之大让Linus很难继续通过手工方式管理了，社区的弟兄们也对这种方式表达了强烈不满，于是Linus选择了一个商业的版本控制系统BitKeeper，BitKeeper的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。

安定团结的大好局面在2005年就被打破了，原因是Linux社区牛人聚集，不免沾染了一些梁山好汉的江湖习气。开发Samba的Andrew试图破解BitKeeper的协议（这么干的其实也不只他一个），被BitMover公司发现了（监控工作做得不错！），于是BitMover公司怒了，要收回Linux社区的免费使用权。

Linus可以向BitMover公司道个歉，保证以后严格管教弟兄们，嗯，这是不可能的。实际情况是这样的：

Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！一个月之内，Linux系统的源码已经由Git管理了！牛是怎么定义的呢？大家可以体会一下。

Git迅速成为最流行的分布式版本控制系统，尤其是2008年，GitHub网站上线了，它为开源项目免费提供Git存储，无数开源项目开始迁移至GitHub，包括jQuery，PHP，Ruby等等。

历史就是这么偶然，如果不是当年BitMover公司威胁Linux社区，可能现在我们就没有免费而超级好用的Git了。

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='3'>集中式VS分布式</a>

Linus一直痛恨的CVS及SVN都是集中式的版本控制系统，而Git是分布式版本控制系统，集中式和分布式版本控制系统有什么区别呢？

先说集中式版本控制系统，版本库是集中存放在中央服务器的，而干活的时候，用的都是自己的电脑，所以要先从中央服务器取得最新的版本，然后开始干活，干完活了，再把自己的活推送给中央服务器。中央服务器就好比是一个图书馆，你要改一本书，必须先从图书馆借出来，然后回到家自己改，改完了，再放回图书馆。

![central-repo](https://www.liaoxuefeng.com/files/attachments/918921540355872/0)

集中式版本控制系统最大的毛病就是必须联网才能工作，如果在局域网内还好，带宽够大，速度够快，可如果在互联网上，遇到网速慢的话，可能提交一个10M的文件就需要5分钟，这还不得把人给憋死啊。

那分布式版本控制系统与集中式版本控制系统有何不同呢？首先，分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

和集中式版本控制系统相比，分布式版本控制系统的安全性要高很多，因为每个人电脑里都有完整的版本库，某一个人的电脑坏掉了不要紧，随便从其他人那里复制一个就可以了。而集中式版本控制系统的中央服务器要是出了问题，所有人都没法干活了。

在实际使用分布式版本控制系统的时候，其实很少在两人之间的电脑上推送版本库的修改，因为可能你们俩不在一个局域网内，两台电脑互相访问不了，也可能今天你的同事病了，他的电脑压根没有开机。因此，分布式版本控制系统通常也有一台充当“中央服务器”的电脑，但这个服务器的作用仅仅是用来方便“交换”大家的修改，没有它大家也一样干活，只是交换修改不方便而已。

![distributed-repo](https://www.liaoxuefeng.com/files/attachments/918921562236160/0)


当然，Git的优势不单是不必联网这么简单，后面我们还会看到Git极其强大的分支管理，把SVN等远远抛在了后面。

CVS作为最早的开源而且免费的集中式版本控制系统，直到现在还有不少人在用。由于CVS自身设计的问题，会造成提交文件不完整，版本库莫名其妙损坏的情况。同样是开源而且免费的SVN修正了CVS的一些稳定性问题，是目前用得最多的集中式版本库控制系统。

除了免费的外，还有收费的集中式版本控制系统，比如IBM的ClearCase（以前是Rational公司的，被IBM收购了），特点是安装比Windows还大，运行比蜗牛还慢，能用ClearCase的一般是世界500强，他们有个共同的特点是财大气粗，或者人傻钱多。

微软自己也有一个集中式版本控制系统叫VSS，集成在Visual Studio中。由于其反人类的设计，连微软自己都不好意思用了。

分布式版本控制系统除了Git以及促使Git诞生的BitKeeper外，还有类似Git的Mercurial和Bazaar等。这些分布式版本控制系统各有特点，但最快、最简单也最流行的依然是Git！

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='4'>安装Git</a>  

在Windows上安装Git
在Windows上使用Git，可以从Git官网直接下载安装程序，（网速慢的同学请移步国内镜像），然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![install-git-on-windows](https://www.liaoxuefeng.com/files/attachments/919018718363424/0)

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。你也许会担心，如果有人故意冒充别人怎么办？这个不必担心，首先我们相信大家都是善良无知的群众，其次，真的有冒充的也是有办法可查的。

注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='5'>创建版本库</a>  

什么是版本库呢？版本库又名仓库，英文名repository，你可以简单理解成一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

所以，创建一个版本库非常简单，首先，选择一个合适的地方，创建一个空目录.如果你使用Windows系统，为了避免遇到各种莫名其妙的问题请确保目录名（包括父目录）不包含中文。
第二步，通过git init命令把这个目录变成Git可以管理的仓库：

```
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```

瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），细心的读者可以发现当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。

如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。

[点击前往观看相关视频](https://www.bilibili.com/video/av51215681?zw)

也不一定必须在空目录下创建Git仓库，选择一个已经有东西的目录也是可以的。不过，不建议你使用自己正在开发的公司项目来学习Git，否则造成的一切后果概不负责。

把文件添加到版本库
首先这里再明确一下，所有的版本控制系统，其实只能跟踪文本文件的改动，比如TXT文件，网页，所有的程序代码等等，Git也不例外。版本控制系统可以告诉你每次的改动，比如在第5行加了一个单词“Linux”，在第8行删了一个单词“Windows”。而图片、视频这些二进制文件，虽然也能由版本控制系统管理，但没法跟踪文件的变化，只能把二进制文件每次改动串起来，也就是只知道图片从100KB改成了120KB，但到底改了啥，版本控制系统不知道，也没法知道。

不幸的是，Microsoft的Word格式是二进制格式，因此，版本控制系统是没法跟踪Word文件的改动的，前面我们举的例子只是为了演示，如果要真正使用版本控制系统，就要以纯文本方式编写文件。

因为文本是有编码的，比如中文有常用的GBK编码，日文有Shift_JIS编码，如果没有历史遗留问题，强烈建议使用标准的UTF-8编码，所有语言使用同一种编码，既没有冲突，又被所有平台所支持。

使用Windows的童鞋要特别注意：

千万不要使用Windows自带的记事本编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载Notepad++代替记事本，不但功能强大，而且免费！记得把Notepad++的默认编码设置为UTF-8 without BOM即可：

![set-utf8-notepad++](https://www.liaoxuefeng.com/files/attachments/919018919808256/0)

言归正传，现在我们编写一个readme.txt文件，内容如下：
```
Git is a version control system.
Git is free software.
```

一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。

和把大象放到冰箱需要3步相比，把一个文件放到Git仓库只需要两步。

第一步，用命令git add告诉Git，把文件添加到仓库：
```
$ git add readme.txt
```
执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

第二步，用命令git commit告诉Git，把文件提交到仓库：
```
$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```
简单解释一下git commit命令，-m后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

嫌麻烦不想输入-m "xxx"行不行？确实有办法可以这么干，但是强烈不建议你这么干，因为输入说明对自己对别人阅读都很重要。实在不想输入说明的童鞋请自行Google，我不告诉你这个参数。

git commit命令执行成功后会告诉你，1 file changed：1个文件被改动（我们新添加的readme.txt文件）；2 insertions：插入了两行内容（readme.txt有两行内容）。

[点击前往观看相关视频](https://www.bilibili.com/video/av51215739?zw)

为什么Git添加文件需要add，commit一共两步呢？因为commit可以一次提交很多文件，所以你可以多次add不同的文件，比如：
```
$ git add file1.txt
$ git add file2.txt file3.txt
$ git commit -m "add 3 files."
```
小结  
现在总结一下今天学的两点内容：

初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

使用命令git add <file>，注意，可反复多次使用，添加多个文件；
使用命令git commit -m <message>，完成。

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='6'>时光机穿梭</a>

我们已经成功地添加并提交了一个readme.txt文件，现在，是时候继续工作了，于是，我们继续修改readme.txt文件，改成如下内容：
```
Git is a distributed version control system.
Git is free software.
```
现在，运行git status命令看看结果：
```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
git status命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，readme.txt被修改过了，但还没有准备提交的修改。

虽然Git告诉我们readme.txt被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的readme.txt，所以，需要用git diff这个命令看看：
```
$ git diff readme.txt 
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
 ```
git diff顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个distributed单词。

知道了对readme.txt作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是git add：
```
$ git add readme.txt
```
同样没有任何输出。在执行第二步git commit之前，我们再运行git status看看当前仓库的状态：
```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   readme.txt
```
git status告诉我们，将要被提交的修改包括readme.txt，下一步，就可以放心地提交了：
```
$ git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
 ```
提交后，我们再用git status命令看看仓库的当前状态：
```
$ git status
On branch master
nothing to commit, working tree clean
```
Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working tree clean）的。  
[点击前往观看相关视频](https://www.bilibili.com/video/av51227082?zw)  
小结  
要随时掌握工作区的状态，使用git status命令。  
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。  

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='7'>版本回退</a>

<div class="x-wiki-content x-main-content"><p>现在，你已经学会了修改文件，然后把修改提交到Git版本库，现在，再练习一次，修改readme.txt文件如下：</p>
<pre><code class="python">Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
</code></pre>
<p>然后尝试提交：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt
<span class="variable">$ </span>git commit -m <span class="string">"append GPL"</span>
[master <span class="number">1094</span>adb] append <span class="constant">GPL</span>
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</code></pre>
<p>像这样，你不断对文件进行修改，然后不断提交修改到版本库里，就好比玩RPG游戏时，每通过一关就会自动把游戏状态存盘，如果某一关没过去，你还可以选择读取前一关的状态。有些时候，在打Boss之前，你会手动存盘，以便万一打Boss失败了，可以从最近的地方重新开始。Git也是一样，每当你觉得文件修改到一定程度的时候，就可以“保存一个快照”，这个快照在Git中被称为<code>commit</code>。一旦你把文件改乱了，或者误删了文件，还可以从最近的一个<code>commit</code>恢复，然后继续工作，而不是把几个月的工作成果全部丢失。</p>
<p>现在，我们回顾一下<code>readme.txt</code>文件一共有几个版本被提交到Git仓库里了：</p>
<p>版本1：wrote a readme file</p>
<pre><code class="python">Git <span class="keyword">is</span> a version control system.
Git <span class="keyword">is</span> free software.
</code></pre>
<p>版本2：add distributed</p>
<pre><code class="python">Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software.
</code></pre>
<p>版本3：append GPL</p>
<pre><code class="python">Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
</code></pre>
<p>当然了，在实际工作中，我们脑子里怎么可能记得一个几千行的文件每次都改了什么内容，不然要版本控制系统干什么。版本控制系统肯定有某个命令可以告诉我们历史记录，在Git中，我们用<code>git log</code>命令查看：</p>
<pre><code class="xml">$ git log
commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -&gt; master)
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

commit e475afc93c209a690c39c13a46716e8fa000c366
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
</code></pre>
<p><code>git log</code>命令显示从最近到最远的提交日志，我们可以看到3次提交，最近的一次是<code>append GPL</code>，上一次是<code>add distributed</code>，最早的一次是<code>wrote a readme file</code>。</p>
<p>如果嫌输出信息太多，看得眼花缭乱的，可以试试加上<code>--pretty=oneline</code>参数：</p>
<pre><code class="ruby"><span class="variable">$ </span>git log --pretty=oneline
<span class="number">1094</span>adb7b9b3807259d8cb349e7df1d4d6477073 (<span class="constant">HEAD</span> -&gt; master) append <span class="constant">GPL</span>
e475afc93c209a690c39c13a46716e8fa000c366 add distributed
eaadf4e385e865d25c48e7ca9c8395c3f7dfaef<span class="number">0</span> wrote a readme file
</code></pre>
<p>需要友情提示的是，你看到的一大串类似<code>1094adb...</code>的是<code>commit id</code>（版本号），和SVN不一样，Git的<code>commit id</code>不是1，2，3……递增的数字，而是一个SHA1计算出来的一个非常大的数字，用十六进制表示，而且你看到的<code>commit id</code>和我的肯定不一样，以你自己的为准。为什么<code>commit id</code>需要用这么一大串数字表示呢？因为Git是分布式的版本控制系统，后面我们还要研究多人在同一个版本库里工作，如果大家都用1，2，3……作为版本号，那肯定就冲突了。</p>
<p>每提交一个新版本，实际上Git就会把它们自动串成一条时间线。如果使用可视化工具查看Git历史，就可以更清楚地看到提交历史的时间线：</p>

![](https://www.liaoxuefeng.com/files/attachments/919019707114272/0)

<p>好了，现在我们启动时光穿梭机，准备把<code>readme.txt</code>回退到上一个版本，也就是<code>add distributed</code>的那个版本，怎么做呢？</p>
<p>首先，Git必须知道当前版本是哪个版本，在Git中，用<code>HEAD</code>表示当前版本，也就是最新的提交<code>1094adb...</code>（注意我的提交ID和你的肯定不一样），上一个版本就是<code>HEAD^</code>，上上一个版本就是<code>HEAD^^</code>，当然往上100个版本写100个<code>^</code>比较容易数不过来，所以写成<code>HEAD~100</code>。</p>
<p>现在，我们要把当前版本<code>append GPL</code>回退到上一个版本<code>add distributed</code>，就可以使用<code>git reset</code>命令：</p>
<pre><code class="sql">$ git re<span class="operator"><span class="keyword">set</span> --hard HEAD^
HEAD <span class="keyword">is</span> now <span class="keyword">at</span> e475afc <span class="keyword">add</span> distributed
</span></code></pre>
<p><code>--hard</code>参数有啥意义？这个后面再讲，现在你先放心使用。</p>
<p>看看<code>readme.txt</code>的内容是不是版本<code>add distributed</code>：</p>
<pre><code class="python">$ cat readme.txt
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software.
</code></pre>
<p>果然被还原了。</p>
<p>还可以继续回退到上一个版本<code>wrote a readme file</code>，不过且慢，然我们用<code>git log</code>再看看现在版本库的状态：</p>
<pre><code class="xml">$ git log
commit e475afc93c209a690c39c13a46716e8fa000c366 (HEAD -&gt; master)
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
</code></pre>
<p>最新的那个版本<code>append GPL</code>已经看不到了！好比你从21世纪坐时光穿梭机来到了19世纪，想再回去已经回不去了，肿么办？</p>
<p>办法其实还是有的，只要上面的命令行窗口还没有被关掉，你就可以顺着往上找啊找啊，找到那个<code>append GPL</code>的<code>commit id</code>是<code>1094adb...</code>，于是就可以指定回到未来的某个版本：</p>
<pre><code class="sql">$ git re<span class="operator"><span class="keyword">set</span> --hard <span class="number">1094</span>a
HEAD <span class="keyword">is</span> now <span class="keyword">at</span> <span class="number">83</span>b0afe append GPL
</span></code></pre>
<p>版本号没必要写全，前几位就可以了，Git会自动去找。当然也不能只写前一两位，因为Git可能会找到多个版本号，就无法确定是哪一个了。</p>
<p>再小心翼翼地看看<code>readme.txt</code>的内容：</p>
<pre><code class="python">$ cat readme.txt
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
</code></pre>
<p>果然，我胡汉三又回来了。</p>
<p>Git的版本回退速度非常快，因为Git在内部有个指向当前版本的<code>HEAD</code>指针，当你回退版本的时候，Git仅仅是把HEAD从指向<code>append GPL</code>：</p>
<pre style="font-size: 12px; line-height: 12px; border: none; white-space: pre; background-color: transparent;"><code class="language-ascii" style="font-family: &quot;Courier New&quot;, Consolas, monospace;">┌────┐
│HEAD│
└────┘
   │
   └──&gt; ○ append GPL
        │
        ○ add distributed
        │
        ○ wrote a readme file
</code></pre>
<p>改为指向<code>add distributed</code>：</p>
<pre style="font-size: 12px; line-height: 12px; border: none; white-space: pre; background-color: transparent;"><code class="language-ascii" style="font-family: &quot;Courier New&quot;, Consolas, monospace;">┌────┐
│HEAD│
└────┘
   │
   │    ○ append GPL
   │    │
   └──&gt; ○ add distributed
        │
        ○ wrote a readme file
</code></pre>
<p>然后顺便把工作区的文件更新了。所以你让<code>HEAD</code>指向哪个版本号，你就把当前版本定位在哪。</p>
<p>现在，你回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本怎么办？找不到新版本的<code>commit id</code>怎么办？</p>
<p>在Git中，总是有后悔药可以吃的。当你用<code>$ git reset --hard HEAD^</code>回退到<code>add distributed</code>版本时，再想恢复到<code>append GPL</code>，就必须找到<code>append GPL</code>的commit id。Git提供了一个命令<code>git reflog</code>用来记录你的每一次命令：</p>
<pre><code class="css">$ <span class="tag">git</span> <span class="tag">reflog</span>
<span class="tag">e475afc</span> <span class="tag">HEAD</span><span class="at_rule">@</span>{1}: <span class="tag">reset</span>: <span class="tag">moving</span> <span class="tag">to</span> <span class="tag">HEAD</span>^
1094<span class="tag">adb</span> (<span class="tag">HEAD</span> -&gt; <span class="tag">master</span>) <span class="tag">HEAD</span><span class="at_rule">@</span>{2}: <span class="tag">commit</span>: <span class="tag">append</span> <span class="tag">GPL</span>
<span class="tag">e475afc</span> <span class="tag">HEAD</span><span class="at_rule">@</span>{3}: <span class="tag">commit</span>: <span class="tag">add</span> <span class="tag">distributed</span>
<span class="tag">eaadf4e</span> <span class="tag">HEAD</span><span class="at_rule">@</span>{4}: <span class="tag">commit</span> (<span class="tag">initial</span>): <span class="tag">wrote</span> <span class="tag">a</span> <span class="tag">readme</span> <span class="tag">file</span>
</code></pre>
<p>终于舒了口气，从输出可知，<code>append GPL</code>的commit id是<code>1094adb</code>，现在，你又可以乘坐时光机回到未来了。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51227163" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<p>现在总结一下：</p>
<ul>
<li>
<p><code>HEAD</code>指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令<code>git reset --hard commit_id</code>。</p>
</li>
<li>
<p>穿梭前，用<code>git log</code>可以查看提交历史，以便确定要回退到哪个版本。</p>
</li>
<li>
<p>要重返未来，用<code>git reflog</code>查看命令历史，以便确定要回到未来的哪个版本。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='8'>工作区和暂存区</a>

<div class="x-wiki-content x-main-content"><p>Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念。</p>
<p>先来看名词解释。</p>
<h4>工作区（Working Directory）</h4>
<p>就是你在电脑里能看到的目录，比如我的<code>learngit</code>文件夹就是一个工作区：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021113952544/0)

<h4>版本库（Repository）</h4>
<p>工作区有一个隐藏目录<code>.git</code>，这个不算工作区，而是Git的版本库。</p>
<p>Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支<code>master</code>，以及指向<code>master</code>的一个指针叫<code>HEAD</code>。</p>

![](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

<p>分支和<code>HEAD</code>的概念我们以后再讲。</p>
<p>前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：</p>
<p>第一步是用<code>git add</code>把文件添加进去，实际上就是把文件修改添加到暂存区；</p>
<p>第二步是用<code>git commit</code>提交更改，实际上就是把暂存区的所有内容提交到当前分支。</p>
<p>因为我们创建Git版本库时，Git自动为我们创建了唯一一个<code>master</code>分支，所以，现在，<code>git commit</code>就是往<code>master</code>分支上提交更改。</p>
<p>你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。</p>
<p>俗话说，实践出真知。现在，我们再练习一遍，先对<code>readme.txt</code>做个修改，比如加上一行内容：</p>
<pre><code class="python">Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
Git has a mutable index called stage.
</code></pre>
<p>然后，在工作区新增一个<code>LICENSE</code>文本文件（内容随便写）。</p>
<p>先用<code>git status</code>查看一下状态：</p>
<pre><code class="sql">$ git status
On branch master
Changes not staged for commit:
  (use "git add &lt;file&gt;..." to <span class="operator"><span class="keyword">update</span> what will be committed)
  (use <span class="string">"git checkout -- &lt;file&gt;..."</span> <span class="keyword">to</span> discard changes <span class="keyword">in</span> working directory)

	modified:   readme.txt

Untracked files:
  (use <span class="string">"git add &lt;file&gt;..."</span> <span class="keyword">to</span> include <span class="keyword">in</span> what will be committed)

	LICENSE

<span class="keyword">no</span> changes added <span class="keyword">to</span> <span class="keyword">commit</span> (use <span class="string">"git add"</span> <span class="keyword">and</span>/<span class="keyword">or</span> <span class="string">"git commit -a"</span>)
</span></code></pre>
<p>Git非常清楚地告诉我们，<code>readme.txt</code>被修改了，而<code>LICENSE</code>还从来没有被添加过，所以它的状态是<code>Untracked</code>。</p>
<p>现在，使用两次命令<code>git add</code>，把<code>readme.txt</code>和<code>LICENSE</code>都添加后，用<code>git status</code>再查看一下：</p>
<pre><code class="xml">$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to unstage)

	new file:   LICENSE
	modified:   readme.txt
</code></pre>
<p>现在，暂存区的状态就变成这样了：</p>

![](https://www.liaoxuefeng.com/files/attachments/919020074026336/0)

<p>所以，<code>git add</code>命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行<code>git commit</code>就可以一次性把暂存区的所有修改提交到分支。</p>
<pre><code class="sql">$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"understand how stage works"</span>
[master e43a48b] understand how stage works
 <span class="number">2</span> files changed, <span class="number">2</span> insertions(+)
 <span class="keyword">create</span> mode <span class="number">100644</span> LICENSE
</span></code></pre>
<p>一旦提交后，如果你又没有对工作区做任何修改，那么工作区就是“干净”的：</p>
<pre><code class="sql">$ git status
On branch master
nothing to <span class="operator"><span class="keyword">commit</span>, working tree clean
</span></code></pre>
<p>现在版本库变成了这样，暂存区就没有任何内容了：</p>

![](https://www.liaoxuefeng.com/files/attachments/919020100829536/0)

<p><iframe src="//player.bilibili.com/player.html?aid=51227250" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<p>暂存区是Git非常重要的概念，弄明白了暂存区，就弄明白了Git的很多操作到底干了什么。</p>
<p>没弄明白暂存区是怎么回事的童鞋，请向上滚动页面，再看一次。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='9'>管理修改</a>

<div class="x-wiki-content x-main-content"><p>现在，假定你已经完全掌握了暂存区的概念。下面，我们要讨论的就是，为什么Git比其他版本控制系统设计得优秀，因为Git跟踪并管理的是修改，而非文件。</p>
<p>你会问，什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。</p>
<p>为什么说Git管理的是修改，而不是文件呢？我们还是做实验。第一步，对readme.txt做一个修改，比如加一行内容：</p>
<pre><code class="python">$ cat readme.txt
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.
</code></pre>
<p>然后，添加：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt
<span class="variable">$ </span>git status
<span class="comment"># On branch master</span>
<span class="comment"># Changes to be committed:</span>
<span class="comment">#   (use "git reset HEAD &lt;file&gt;..." to unstage)</span>
<span class="comment">#</span>
<span class="comment">#       modified:   readme.txt</span>
<span class="comment">#</span>
</code></pre>
<p>然后，再修改readme.txt：</p>
<pre><code class="python">$ cat readme.txt 
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
</code></pre>
<p>提交：</p>
<pre><code class="sql">$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"git tracks changes"</span>
[master <span class="number">519219</span>b] git tracks changes
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</span></code></pre>
<p>提交后，再看看状态：</p>
<pre><code class="sql">$ git status
On branch master
Changes not staged for commit:
  (use "git add &lt;file&gt;..." to <span class="operator"><span class="keyword">update</span> what will be committed)
  (use <span class="string">"git checkout -- &lt;file&gt;..."</span> <span class="keyword">to</span> discard changes <span class="keyword">in</span> working directory)

	modified:   readme.txt

<span class="keyword">no</span> changes added <span class="keyword">to</span> <span class="keyword">commit</span> (use <span class="string">"git add"</span> <span class="keyword">and</span>/<span class="keyword">or</span> <span class="string">"git commit -a"</span>)
</span></code></pre>
<p>咦，怎么第二次的修改没有被提交？</p>
<p>别激动，我们回顾一下操作过程：</p>
<p>第一次修改 -&gt; <code>git add</code> -&gt; 第二次修改 -&gt; <code>git commit</code></p>
<p>你看，我们前面讲了，Git管理的是修改，当你用<code>git add</code>命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，<code>git commit</code>只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。</p>
<p>提交后，用<code>git diff HEAD -- readme.txt</code>命令可以查看工作区和版本库里面最新版本的区别：</p>
<pre><code class="python">$ git diff HEAD -- readme.txt 
diff --git a/readme.txt b/readme.txt
index <span class="number">76</span>d770f..a9c5755 <span class="number">100644</span>
--- a/readme.txt
+++ b/readme.txt
<span class="decorator">@@ -1,4 +1,4 @@</span>
 Git <span class="keyword">is</span> a distributed version control system.
 Git <span class="keyword">is</span> free software distributed under the GPL.
 Git has a mutable index called stage.
-Git tracks changes.
+Git tracks changes of files.
</code></pre>
<p>可见，第二次修改确实没有被提交。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51227357" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>那怎么提交第二次修改呢？你可以继续<code>git add</code>再<code>git commit</code>，也可以别着急提交第一次修改，先<code>git add</code>第二次修改，再<code>git commit</code>，就相当于把两次修改合并后一块提交了：</p>
<p>第一次修改 -&gt; <code>git add</code> -&gt; 第二次修改 -&gt; <code>git add</code> -&gt; <code>git commit</code></p>
<p>好，现在，把第二次修改提交了，然后开始小结。</p>
<h3>小结</h3>
<p>现在，你又理解了Git是如何跟踪修改的，每次修改，如果不用<code>git add</code>到暂存区，那就不会加入到<code>commit</code>中。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='10'>撤销修改</a>

<div class="x-wiki-content x-main-content"><p>自然，你是不会犯错的。不过现在是凌晨两点，你正在赶一份工作报告，你在<code>readme.txt</code>中添加了一行：</p>
<pre><code class="python">$ cat readme.txt
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
My stupid boss still prefers SVN.
</code></pre>
<p>在你准备提交前，一杯咖啡起了作用，你猛然发现了<code>stupid boss</code>可能会让你丢掉这个月的奖金！</p>
<p>既然错误发现得很及时，就可以很容易地纠正它。你可以删掉最后一行，手动把文件恢复到上一个版本的状态。如果用<code>git status</code>查看一下：</p>
<pre><code class="sql">$ git status
On branch master
Changes not staged for commit:
  (use "git add &lt;file&gt;..." to <span class="operator"><span class="keyword">update</span> what will be committed)
  (use <span class="string">"git checkout -- &lt;file&gt;..."</span> <span class="keyword">to</span> discard changes <span class="keyword">in</span> working directory)

	modified:   readme.txt

<span class="keyword">no</span> changes added <span class="keyword">to</span> <span class="keyword">commit</span> (use <span class="string">"git add"</span> <span class="keyword">and</span>/<span class="keyword">or</span> <span class="string">"git commit -a"</span>)
</span></code></pre>
<p>你可以发现，Git会告诉你，<code>git checkout -- file</code>可以丢弃工作区的修改：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -- readme.txt
</code></pre>
<p>命令<code>git checkout -- readme.txt</code>意思就是，把<code>readme.txt</code>文件在工作区的修改全部撤销，这里有两种情况：</p>
<p>一种是<code>readme.txt</code>自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；</p>
<p>一种是<code>readme.txt</code>已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。</p>
<p>总之，就是让这个文件回到最近一次<code>git commit</code>或<code>git add</code>时的状态。</p>
<p>现在，看看<code>readme.txt</code>的文件内容：</p>
<pre><code class="python">$ cat readme.txt
Git <span class="keyword">is</span> a distributed version control system.
Git <span class="keyword">is</span> free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
</code></pre>
<p>文件内容果然复原了。</p>
<p><code>git checkout -- file</code>命令中的<code>--</code>很重要，没有<code>--</code>，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到<code>git checkout</code>命令。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51227817" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>现在假定是凌晨3点，你不但写了一些胡话，还<code>git add</code>到暂存区了：</p>
<pre><code class="ruby"><span class="variable">$ </span>cat readme.txt
<span class="constant">Git</span> is a distributed version control system.
<span class="constant">Git</span> is free software distributed under the <span class="constant">GPL</span>.
<span class="constant">Git</span> has a mutable index called stage.
<span class="constant">Git</span> tracks changes of files.
<span class="constant">My</span> stupid boss still prefers <span class="constant">SVN</span>.

<span class="variable">$ </span>git add readme.txt
</code></pre>
<p>庆幸的是，在<code>commit</code>之前，你发现了这个问题。用<code>git status</code>查看一下，修改只是添加到了暂存区，还没有提交：</p>
<pre><code class="xml">$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to unstage)

	modified:   readme.txt
</code></pre>
<p>Git同样告诉我们，用命令<code>git reset HEAD &lt;file&gt;</code>可以把暂存区的修改撤销掉（unstage），重新放回工作区：</p>
<pre><code class="sql">$ git re<span class="operator"><span class="keyword">set</span> HEAD readme.txt
Unstaged changes after reset:
M	readme.txt
</span></code></pre>
<p><code>git reset</code>命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用<code>HEAD</code>时，表示最新的版本。</p>
<p>再用<code>git status</code>查看一下，现在暂存区是干净的，工作区有修改：</p>
<pre><code class="xml">$ git status
On branch master
Changes not staged for commit:
  (use "git add <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to update what will be committed)
  (use "git checkout -- <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to discard changes in working directory)

	modified:   readme.txt
</code></pre>
<p>还记得如何丢弃工作区的修改吗？</p>
<pre><code class="sql">$ git checkout <span class="comment">-- readme.txt</span>

$ git status
On branch master
nothing to <span class="operator"><span class="keyword">commit</span>, working tree clean
</span></code></pre>
<p>整个世界终于清静了！</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51227959" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>现在，假设你不但改错了东西，还从暂存区提交到了版本库，怎么办呢？还记得<a href="/wiki/896043488029600/897013573512192">版本回退</a>一节吗？可以回退到上一个版本。不过，这是有条件的，就是你还没有把自己的本地版本库推送到远程。还记得Git是分布式版本控制系统吗？我们后面会讲到远程版本库，一旦你把<code>stupid boss</code>提交推送到远程版本库，你就真的惨了……</p>
<h3>小结</h3>
<p>又到了小结时间。</p>
<p>场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令<code>git checkout -- file</code>。</p>
<p>场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令<code>git reset HEAD &lt;file&gt;</code>，就回到了场景1，第二步按场景1操作。</p>
<p>场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考<a href="/wiki/896043488029600/897013573512192">版本回退</a>一节，不过前提是没有推送到远程库。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='11'>删除文件</a>

<div class="x-wiki-content x-main-content"><p>在Git中，删除也是一个修改操作，我们实战一下，先添加一个新文件<code>test.txt</code>到Git并且提交：</p>
<pre><code class="sql">$ git add test.txt

$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"add test.txt"</span>
[master b84166e] <span class="keyword">add</span> test.txt
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
 <span class="keyword">create</span> mode <span class="number">100644</span> test.txt
</span></code></pre>
<p>一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用<code>rm</code>命令删了：</p>
<pre><code class="ruby"><span class="variable">$ </span>rm test.txt
</code></pre>
<p>这个时候，Git知道你删除了文件，因此，工作区和版本库就不一致了，<code>git status</code>命令会立刻告诉你哪些文件被删除了：</p>
<pre><code class="sql">$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm &lt;file&gt;..." to <span class="operator"><span class="keyword">update</span> what will be committed)
  (use <span class="string">"git checkout -- &lt;file&gt;..."</span> <span class="keyword">to</span> discard changes <span class="keyword">in</span> working directory)

	deleted:    test.txt

<span class="keyword">no</span> changes added <span class="keyword">to</span> <span class="keyword">commit</span> (use <span class="string">"git add"</span> <span class="keyword">and</span>/<span class="keyword">or</span> <span class="string">"git commit -a"</span>)
</span></code></pre>
<p>现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令<code>git rm</code>删掉，并且<code>git commit</code>：</p>
<pre><code class="sql">$ git rm test.txt
rm 'test.txt'

$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"remove test.txt"</span>
[master d46f35e] remove test.txt
 <span class="number">1</span> file changed, <span class="number">1</span> deletion(-)
 <span class="keyword">delete</span> mode <span class="number">100644</span> test.txt
</span></code></pre>
<p>现在，文件就从版本库中被删除了。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51228086" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<div class="uk-alert "><i class="uk-icon-info-circle"></i> 小提示：先手动删除文件，然后使用git rm &lt;file&gt;和git add&lt;file&gt;效果是一样的。
</div>
<p>另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -- test.txt
</code></pre>
<p><code>git checkout</code>其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。</p>
<div class="uk-alert uk-alert-danger"><i class="uk-icon-warning"></i> 注意：从来没有被添加到版本库就被删除的文件，是无法恢复的！
</div>
<h3>小结</h3>
<p>命令<code>git rm</code>用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失<strong>最近一次提交后你修改的内容</strong>。</p>
</div>  

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='12'>远程仓库</a>

<div class="x-wiki-content x-main-content"><p>到目前为止，我们已经掌握了如何在Git仓库里对一个文件进行时光穿梭，你再也不用担心文件备份或者丢失的问题了。</p>
<p>可是有用过集中式版本控制系统SVN的童鞋会站出来说，这些功能在SVN里早就有了，没看出Git有什么特别的地方。</p>
<p>没错，如果只是在一个仓库里管理文件历史，Git和SVN真没啥区别。为了保证你现在所学的Git物超所值，将来绝对不会后悔，同时为了打击已经不幸学了SVN的童鞋，本章开始介绍Git的杀手级功能之一（注意是之一，也就是后面还有之二，之三……）：远程仓库。</p>
<p>Git是分布式版本控制系统，同一个Git仓库，可以分布到不同的机器上。怎么分布呢？最早，肯定只有一台机器有一个原始版本库，此后，别的机器可以“克隆”这个原始版本库，而且每台机器的版本库其实都是一样的，并没有主次之分。</p>
<p>你肯定会想，至少需要两台机器才能玩远程库不是？但是我只有一台电脑，怎么玩？</p>
<p>其实一台电脑上也是可以克隆多个版本库的，只要不在同一个目录下。不过，现实生活中是不会有人这么傻的在一台电脑上搞几个远程库玩，因为一台电脑上搞几个远程库完全没有意义，而且硬盘挂了会导致所有库都挂掉，所以我也不告诉你在一台电脑上怎么克隆多个仓库。</p>
<p>实际情况往往是这样，找一台电脑充当服务器的角色，每天24小时开机，其他每个人都从这个“服务器”仓库克隆一份到自己的电脑上，并且各自把各自的提交推送到服务器仓库里，也从服务器仓库中拉取别人的提交。</p>
<p>完全可以自己搭建一台运行Git的服务器，不过现阶段，为了学Git先搭个服务器绝对是小题大作。好在这个世界上有个叫<a href="https://github.com/" target="_blank">GitHub</a>的神奇的网站，从名字就可以看出，这个网站就是提供Git仓库托管服务的，所以，只要注册一个GitHub账号，就可以免费获得Git远程仓库。</p>
<p>在继续阅读后续内容前，请自行注册GitHub账号。由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置：</p>
<p>第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有<code>id_rsa</code>和<code>id_rsa.pub</code>这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：</p>
<pre><code class="ruby"><span class="variable">$ </span>ssh-keygen -t rsa -<span class="constant">C</span> <span class="string">"youremail@example.com"</span>
</code></pre>
<p></p><div class="html5-video" data-type="video" data-width="648" data-height="434" data-src="http://liaoxuefeng-liaoxuefeng.stor.sinaapp.com/learngit/video/ssh-keygen.mp4"></div><p></p>
<p>你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。</p>
<p>如果一切顺利的话，可以在用户主目录里找到<code>.ssh</code>目录，里面有<code>id_rsa</code>和<code>id_rsa.pub</code>两个文件，这两个就是SSH Key的秘钥对，<code>id_rsa</code>是私钥，不能泄露出去，<code>id_rsa.pub</code>是公钥，可以放心地告诉任何人。</p>
<p>第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：</p>
<p>然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴<code>id_rsa.pub</code>文件的内容：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021379029408/0)

<p>点“Add Key”，你就应该看到已经添加的Key：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021395420160/0)

<p>为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。</p>
<p>当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。</p>
<p>最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。</p>
<p>如果你不想让别人看到Git库，有两个办法，一个是交点保护费，让GitHub把公开的仓库变成私有的，这样别人就看不见了（不可读更不可写）。另一个办法是自己动手，搭一个Git服务器，因为是你自己的Git服务器，所以别人也是看不见的。这个方法我们后面会讲到的，相当简单，公司内部开发必备。</p>
<p>确保你拥有一个GitHub账号后，我们就即将开始远程仓库的学习。</p>
<h3>小结</h3>
<p>“有了远程仓库，妈妈再也不用担心我的硬盘了。”——Git点读机</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='13'>添加远程仓库</a>

<div class="x-wiki-content x-main-content"><p>现在的情景是，你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。</p>
<p>首先，登陆GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021631860000/0)

<p>在Repository name填入<code>learngit</code>，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021652277920/0)

<p>目前，在GitHub上的这个<code>learngit</code>仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。</p>
<p>现在，我们根据GitHub的提示，在本地的<code>learngit</code>仓库下运行命令：</p>
<pre><code class="ruby"><span class="variable">$ </span>git remote add origin git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/learngit.git
</code></pre>
<p>请千万注意，把上面的<code>michaelliao</code>替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。</p>
<p>添加后，远程库的名字就是<code>origin</code>，这是Git默认的叫法，也可以改成别的，但是<code>origin</code>这个名字一看就知道是远程库。</p>
<p>下一步，就可以把本地库的所有内容推送到远程库上：</p>
<pre><code class="sql">$ git push -u origin master
Counting objects: 20, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (15/15), done.
Writing objects: 100% (20/20), 1.64 KiB | 560.00 KiB/s, done.
Total 20 (delta 5), reused 0 (delta 0)
remote: Resolving deltas: 100% (5/5), done.
To github.com:michaelliao/learngit.git
 * [new branch]      master -&gt; master
Branch 'master' <span class="operator"><span class="keyword">set</span> up <span class="keyword">to</span> track remote branch <span class="string">'master'</span> <span class="keyword">from</span> <span class="string">'origin'</span>.
</span></code></pre>
<p>把本地库的内容推送到远程，用<code>git push</code>命令，实际上是把当前分支<code>master</code>推送到远程。</p>
<p>由于远程库是空的，我们第一次推送<code>master</code>分支时，加上了<code>-u</code>参数，Git不但会把本地的<code>master</code>分支内容推送的远程新的<code>master</code>分支，还会把本地的<code>master</code>分支和远程的<code>master</code>分支关联起来，在以后的推送或者拉取时就可以简化命令。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51228184" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>推送成功后，可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021675995552/0)

<p>从现在起，只要本地作了提交，就可以通过命令：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin master
</code></pre>
<p>把本地<code>master</code>分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！</p>
<h3>SSH警告</h3>
<p>当你第一次使用Git的<code>clone</code>或者<code>push</code>命令连接GitHub时，会得到一个警告：</p>
<pre><code class="undefined">The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
</code></pre>
<p>这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入<code>yes</code>回车即可。</p>
<p>Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：</p>
<pre><code class="php">Warning: Permanently added <span class="string">'github.com'</span> (RSA) to the <span class="keyword">list</span> of known hosts.
</code></pre>
<p>这个警告只会出现一次，后面的操作就不会有任何警告了。</p>
<p>如果你实在担心有人冒充GitHub服务器，输入<code>yes</code>前可以对照<a href="https://help.github.com/articles/what-are-github-s-ssh-key-fingerprints/" target="_blank">GitHub的RSA Key的指纹信息</a>是否与SSH连接给出的一致。</p>
<h3>小结</h3>
<p>要关联一个远程库，使用命令<code>git remote add origin git@server-name:path/repo-name.git</code>；</p>
<p>关联后，使用命令<code>git push -u origin master</code>第一次推送master分支的所有内容；</p>
<p>此后，每次本地提交后，只要有必要，就可以使用命令<code>git push origin master</code>推送最新修改；</p>
<p>分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程库的存在，也就是有没有联网都可以正常工作，而SVN在没有联网的时候是拒绝干活的！当有网络的时候，再把本地提交推送一下就完成了同步，真是太方便了！</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='14'>从远程仓库克隆</a>

<div class="x-wiki-content x-main-content"><p>上次我们讲了先有本地库，后有远程库的时候，如何关联远程库。</p>
<p>现在，假设我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。</p>
<p>首先，登陆GitHub，创建一个新的仓库，名字叫<code>gitskills</code>：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021808263616/0)

<p>我们勾选<code>Initialize this repository with a README</code>，这样GitHub会自动为我们创建一个<code>README.md</code>文件。创建完毕后，可以看到<code>README.md</code>文件：</p>

![](https://www.liaoxuefeng.com/files/attachments/919021836828288/0)

<p>现在，远程库已经准备好了，下一步是用命令<code>git clone</code>克隆一个本地库：</p>
<pre><code class="ruby"><span class="variable">$ </span>git clone git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/gitskills.git
<span class="constant">Cloning</span> into <span class="string">'gitskills'</span>...
<span class="symbol">remote:</span> <span class="constant">Counting</span> <span class="symbol">objects:</span> <span class="number">3</span>, done.
<span class="symbol">remote:</span> <span class="constant">Total</span> <span class="number">3</span> (delta <span class="number">0</span>), reused <span class="number">0</span> (delta <span class="number">0</span>), pack-reused <span class="number">3</span>
<span class="constant">Receiving</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">3</span>/<span class="number">3</span>), done.
</code></pre>
<p>注意把Git库的地址换成你自己的，然后进入<code>gitskills</code>目录看看，已经有<code>README.md</code>文件了：</p>
<pre><code class="ruby"><span class="variable">$ </span>cd gitskills
<span class="variable">$ </span>ls
<span class="constant">README</span>.md
</code></pre>
<p><iframe src="//player.bilibili.com/player.html?aid=51228298" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>如果有多个人协作开发，那么每个人各自从远程克隆一份就可以了。</p>
<p>你也许还注意到，GitHub给出的地址不止一个，还可以用<code>https://github.com/VisualDust/GWidgets.git</code>这样的地址。实际上，Git支持多种协议，默认的<code>git://</code>使用ssh，但也可以使用<code>https</code>等其他协议。</p>
<p>使用<code>https</code>除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用<code>ssh</code>协议而只能用<code>https</code>。</p>
<h3>小结</h3>
<p>要克隆一个仓库，首先必须知道仓库的地址，然后使用<code>git clone</code>命令克隆。</p>
<p>Git支持多种协议，包括<code>https</code>，但通过<code>ssh</code>支持的原生<code>git</code>协议速度最快。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='15'>分支管理</a>

<div class="x-wiki-content x-main-content"><p>分支就是科幻电影里面的平行宇宙，当你正在电脑前努力学习Git的时候，另一个你正在另一个平行宇宙里努力学习SVN。</p>
<p>如果两个平行宇宙互不干扰，那对现在的你也没啥影响。不过，在某个时间点，两个平行宇宙合并了，结果，你既学会了Git又学会了SVN！</p>

![](https://www.liaoxuefeng.com/files/attachments/919021987875136/0)

<p>分支在实际中有什么用呢？假设你准备开发一个新功能，但是需要两周才能完成，第一周你写了50%的代码，如果立刻提交，由于代码还没写完，不完整的代码库会导致别人不能干活了。如果等代码全部写完再一次提交，又存在丢失每天进度的巨大风险。</p>
<p>现在有了分支，就不用怕了。你创建了一个属于你自己的分支，别人看不到，还继续在原来的分支上正常工作，而你在自己的分支上干活，想提交就提交，直到开发完毕后，再一次性合并到原来的分支上，这样，既安全，又不影响别人工作。</p>
<p>其他版本控制系统如SVN等都有分支管理，但是用过之后你会发现，这些版本控制系统创建和切换分支比蜗牛还慢，简直让人无法忍受，结果分支功能成了摆设，大家都不去用。</p>
<p>但Git的分支是与众不同的，无论创建、切换和删除分支，Git在1秒钟之内就能完成！无论你的版本库是1个文件还是1万个文件。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='16'>创建与合并分支</a>

<div class="x-wiki-content x-main-content"><p>在版本回退里，你已经知道，每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。截止到目前，只有一条时间线，在Git里，这个分支叫主分支，即<code>master</code>分支。<code>HEAD</code>严格来说不是指向提交，而是指向<code>master</code>，<code>master</code>才是指向提交的，所以，<code>HEAD</code>指向的就是当前分支。</p>
<p>一开始的时候，<code>master</code>分支是一条线，Git用<code>master</code>指向最新的提交，再用<code>HEAD</code>指向<code>master</code>，就能确定当前分支，以及当前分支的提交点：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022325462368/0)

<p>每次提交，<code>master</code>分支都会向前移动一步，这样，随着你不断提交，<code>master</code>分支的线也越来越长。</p>
<p>当我们创建新的分支，例如<code>dev</code>时，Git新建了一个指针叫<code>dev</code>，指向<code>master</code>相同的提交，再把<code>HEAD</code>指向<code>dev</code>，就表示当前分支在<code>dev</code>上：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022363210080/0)

<p>你看，Git创建一个分支很快，因为除了增加一个<code>dev</code>指针，改改<code>HEAD</code>的指向，工作区的文件都没有任何变化！</p>
<p>不过，从现在开始，对工作区的修改和提交就是针对<code>dev</code>分支了，比如新提交一次后，<code>dev</code>指针往前移动一步，而<code>master</code>指针不变：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022387118368/0)

<p>假如我们在<code>dev</code>上的工作完成了，就可以把<code>dev</code>合并到<code>master</code>上。Git怎么合并呢？最简单的方法，就是直接把<code>master</code>指向<code>dev</code>的当前提交，就完成了合并：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022412005504/0)

<p>所以Git合并分支也很快！就改改指针，工作区内容也不变！</p>
<p>合并完分支后，甚至可以删除<code>dev</code>分支。删除<code>dev</code>分支就是把<code>dev</code>指针给删掉，删掉后，我们就剩下了一条<code>master</code>分支：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022479428512/0)

<p>真是太神奇了，你看得出来有些提交是通过分支完成的吗？</p>
<p>下面开始实战。</p>
<p>首先，我们创建<code>dev</code>分支，然后切换到<code>dev</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -b dev
<span class="constant">Switched</span> to a new branch <span class="string">'dev'</span>
</code></pre>
<p><code>git checkout</code>命令加上<code>-b</code>参数表示创建并切换，相当于以下两条命令：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch dev
<span class="variable">$ </span>git checkout dev
<span class="constant">Switched</span> to branch <span class="string">'dev'</span>
</code></pre>
<p>然后，用<code>git branch</code>命令查看当前分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch
* dev
  master
</code></pre>
<p><code>git branch</code>命令会列出所有分支，当前分支前面会标一个<code>*</code>号。</p>
<p>然后，我们就可以在<code>dev</code>分支上正常提交，比如对<code>readme.txt</code>做个修改，加上一行：</p>
<pre><code class="javascript">Creating a <span class="keyword">new</span> branch is quick.
</code></pre>
<p>然后提交：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt 
<span class="variable">$ </span>git commit -m <span class="string">"branch test"</span>
[dev b17d20e] branch test
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</code></pre>
<p>现在，<code>dev</code>分支的工作完成，我们就可以切换回<code>master</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout master
<span class="constant">Switched</span> to branch <span class="string">'master'</span>
</code></pre>
<p>切换回<code>master</code>分支后，再查看一个<code>readme.txt</code>文件，刚才添加的内容不见了！因为那个提交是在<code>dev</code>分支上，而<code>master</code>分支此刻的提交点并没有变：</p>

![](https://www.liaoxuefeng.com/files/attachments/919022533080576/0)

<p>现在，我们把<code>dev</code>分支的工作成果合并到<code>master</code>分支上：</p>
<pre><code class="ruby"><span class="variable">$ </span>git merge dev
<span class="constant">Updating</span> d46f35e..b17d20e
<span class="constant">Fast</span>-forward
 readme.txt | <span class="number">1</span> +
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</code></pre>
<p><code>git merge</code>命令用于合并指定分支到当前分支。合并后，再查看<code>readme.txt</code>的内容，就可以看到，和<code>dev</code>分支的最新提交是完全一样的。</p>
<p>注意到上面的<code>Fast-forward</code>信息，Git告诉我们，这次合并是“快进模式”，也就是直接把<code>master</code>指向<code>dev</code>的当前提交，所以合并速度非常快。</p>
<p>当然，也不是每次合并都能<code>Fast-forward</code>，我们后面会讲其他方式的合并。</p>
<p>合并完成后，就可以放心地删除<code>dev</code>分支了：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch -d dev
<span class="constant">Deleted</span> branch dev (was b17d20e).
</code></pre>
<p>删除后，查看<code>branch</code>，就只剩下<code>master</code>分支了：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch
* master
</code></pre>
<p>因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在<code>master</code>分支上工作效果是一样的，但过程更安全。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51228618" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>我们注意到切换分支使用<code>git checkout &lt;branch&gt;</code>，而前面讲过的撤销修改则是<code>git checkout -- &lt;file&gt;</code>，同一个命令，有两种作用，确实有点令人迷惑。</p>
<p>实际上，切换分支这个动作，用<code>switch</code>更科学。因此，最新版本的Git提供了新的<code>git switch</code>命令来切换分支：</p>
<p>创建并切换到新的<code>dev</code>分支，可以使用：</p>
<pre><code class="ruby"><span class="variable">$ </span>git switch -c dev
</code></pre>
<p>直接切换到已有的<code>master</code>分支，可以使用：</p>
<pre><code class="ruby"><span class="variable">$ </span>git switch master
</code></pre>
<p>使用新的<code>git switch</code>命令，比<code>git checkout</code>要更容易理解。</p>
<h3>小结</h3>
<p>Git鼓励大量使用分支：</p>
<p>查看分支：<code>git branch</code></p>
<p>创建分支：<code>git branch &lt;name&gt;</code></p>
<p>切换分支：<code>git checkout &lt;name&gt;</code>或者<code>git switch &lt;name&gt;</code></p>
<p>创建+切换分支：<code>git checkout -b &lt;name&gt;</code>或者<code>git switch -c &lt;name&gt;</code></p>
<p>合并某分支到当前分支：<code>git merge &lt;name&gt;</code></p>
<p>删除分支：<code>git branch -d &lt;name&gt;</code></p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='17'>解决冲突</a>

<div class="x-wiki-content x-main-content"><p>人生不如意之事十之八九，合并分支往往也不是一帆风顺的。</p>
<p>准备新的<code>feature1</code>分支，继续我们的新分支开发：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -b feature1
<span class="constant">Switched</span> to a new branch <span class="string">'feature1'</span>
</code></pre>
<p>修改<code>readme.txt</code>最后一行，改为：</p>
<pre><code class="php">Creating a <span class="keyword">new</span> branch is quick <span class="keyword">AND</span> simple.
</code></pre>
<p>在<code>feature1</code>分支上提交：</p>
<pre><code class="sql">$ git add readme.txt

$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"AND simple"</span>
[feature1 <span class="number">14096</span>d0] <span class="keyword">AND</span> simple
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</span></code></pre>
<p>切换到<code>master</code>分支：</p>
<pre><code class="sql">$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 1 <span class="operator"><span class="keyword">commit</span>.
  (use <span class="string">"git push"</span> <span class="keyword">to</span> publish your <span class="keyword">local</span> commits)
</span></code></pre>
<p>Git还会自动提示我们当前<code>master</code>分支比远程的<code>master</code>分支要超前1个提交。</p>
<p>在<code>master</code>分支上把<code>readme.txt</code>文件的最后一行改为：</p>
<pre><code class="javascript">Creating a <span class="keyword">new</span> branch is quick &amp; simple.
</code></pre>
<p>提交：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt 
<span class="variable">$ </span>git commit -m <span class="string">"&amp; simple"</span>
[master <span class="number">5</span>dc6824] &amp; simple
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</code></pre>
<p>现在，<code>master</code>分支和<code>feature1</code>分支各自都分别有新的提交，变成了这样：</p>
<p><img src="/static/img/loading.svg" data-src="/files/attachments/919023000423040/0" alt="git-br-feature1"></p>
<p>这种情况下，Git无法执行“快速合并”，只能试图把各自的修改合并起来，但这种合并就可能会有冲突，我们试试看：</p>
<pre><code class="ruby"><span class="variable">$ </span>git merge feature1
<span class="constant">Auto</span>-merging readme.txt
<span class="constant">CONFLICT</span> (content)<span class="symbol">:</span> <span class="constant">Merge</span> conflict <span class="keyword">in</span> readme.txt
<span class="constant">Automatic</span> merge failed; fix conflicts <span class="keyword">and</span> <span class="keyword">then</span> commit the result.
</code></pre>
<p>果然冲突了！Git告诉我们，<code>readme.txt</code>文件存在冲突，必须手动解决冲突后再提交。<code>git status</code>也可以告诉我们冲突的文件：</p>
<pre><code class="php">$ git status
On branch master
Your branch is ahead of <span class="string">'origin/master'</span> by <span class="number">2</span> commits.
  (<span class="keyword">use</span> <span class="string">"git push"</span> to publish your local commits)

You have unmerged paths.
  (fix conflicts <span class="keyword">and</span> run <span class="string">"git commit"</span>)
  (<span class="keyword">use</span> <span class="string">"git merge --abort"</span> to abort the merge)

Unmerged paths:
  (<span class="keyword">use</span> <span class="string">"git add &lt;file&gt;..."</span> to mark resolution)

	both modified:   readme.txt

no changes added to commit (<span class="keyword">use</span> <span class="string">"git add"</span> <span class="keyword">and</span>/<span class="keyword">or</span> <span class="string">"git commit -a"</span>)
</code></pre>
<p>我们可以直接查看readme.txt的内容：</p>
<pre><code class="javascript">Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
<span class="xml"><span class="tag">&lt;<span class="title">&lt;&lt;&lt;&lt;&lt;&lt;</span> <span class="attribute">HEAD</span>
<span class="attribute">Creating</span> <span class="attribute">a</span> <span class="attribute">new</span> <span class="attribute">branch</span> <span class="attribute">is</span> <span class="attribute">quick</span> &amp; <span class="attribute">simple.</span>
=<span class="value">======</span>
<span class="attribute">Creating</span> <span class="attribute">a</span> <span class="attribute">new</span> <span class="attribute">branch</span> <span class="attribute">is</span> <span class="attribute">quick</span> <span class="attribute">AND</span> <span class="attribute">simple.</span>
&gt;</span>&gt;&gt;&gt;&gt;&gt;&gt; feature1
</span></code></pre>
<p>Git用<code>&lt;&lt;&lt;&lt;&lt;&lt;&lt;</code>，<code>=======</code>，<code>&gt;&gt;&gt;&gt;&gt;&gt;&gt;</code>标记出不同分支的内容，我们修改如下后保存：</p>
<pre><code class="php">Creating a <span class="keyword">new</span> branch is quick <span class="keyword">and</span> simple.
</code></pre>
<p>再提交：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt 
<span class="variable">$ </span>git commit -m <span class="string">"conflict fixed"</span>
[master cf810e4] conflict fixed
</code></pre>
<p>现在，<code>master</code>分支和<code>feature1</code>分支变成了下图所示：</p>

![](https://www.liaoxuefeng.com/files/attachments/919023031831104/0)

<p>用带参数的<code>git log</code>也可以看到分支的合并情况：</p>
<pre><code class="php">$ git log --graph --pretty=oneline --abbrev-commit
*   cf810e4 (HEAD -&gt; master) conflict fixed
|\  
| * <span class="number">14096</span>d0 (feature1) <span class="keyword">AND</span> simple
* | <span class="number">5</span>dc6824 &amp; simple
|/  
* b17d20e branch test
* d46f35e (origin/master) remove test.txt
* b84166e add test.txt
* <span class="number">519219</span>b git tracks changes
* e43a48b understand how stage works
* <span class="number">1094</span>adb append GPL
* e475afc add distributed
* eaadf4e wrote a readme file
</code></pre>
<p>最后，删除<code>feature1</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch -d feature1
<span class="constant">Deleted</span> branch feature1 (was <span class="number">14096</span>d<span class="number">0</span>).
</code></pre>
<p>工作完成。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51228780" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<p>当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。</p>
<p>解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。</p>
<p>用<code>git log --graph</code>命令可以看到分支合并图。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='18'>分支管理策略</a>

<div class="x-wiki-content x-main-content"><p>通常，合并分支时，如果可能，Git会用<code>Fast forward</code>模式，但这种模式下，删除分支后，会丢掉分支信息。</p>
<p>如果要强制禁用<code>Fast forward</code>模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。</p>
<p>下面我们实战一下<code>--no-ff</code>方式的<code>git merge</code>：</p>
<p>首先，仍然创建并切换<code>dev</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -b dev
<span class="constant">Switched</span> to a new branch <span class="string">'dev'</span>
</code></pre>
<p>修改readme.txt文件，并提交一个新的commit：</p>
<pre><code class="sql">$ git add readme.txt 
$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"add merge"</span>
[dev f52c633] <span class="keyword">add</span> merge
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</span></code></pre>
<p>现在，我们切换回<code>master</code>：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout master
<span class="constant">Switched</span> to branch <span class="string">'master'</span>
</code></pre>
<p>准备合并<code>dev</code>分支，请注意<code>--no-ff</code>参数，表示禁用<code>Fast forward</code>：</p>
<pre><code class="ruby"><span class="variable">$ </span>git merge --no-ff -m <span class="string">"merge with no-ff"</span> dev
<span class="constant">Merge</span> made by the <span class="string">'recursive'</span> strategy.
 readme.txt | <span class="number">1</span> +
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</code></pre>
<p>因为本次合并要创建一个新的commit，所以加上<code>-m</code>参数，把commit描述写进去。</p>
<p>合并后，我们用<code>git log</code>看看分支历史：</p>
<pre><code class="sql">$ git log <span class="comment">--graph --pretty=oneline --abbrev-commit</span>
*   e1e9c68 (HEAD -&gt; master) merge with no-ff
|\  
| * f52c633 (dev) add merge
|/  
*   cf810e4 conflict fixed
...
</code></pre>
<p>可以看到，不使用<code>Fast forward</code>模式，merge后就像这样：</p>

![](https://www.liaoxuefeng.com/files/attachments/919023225142304/0)

<p><iframe src="//player.bilibili.com/player.html?aid=51229040" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>分支策略</h3>
<p>在实际开发中，我们应该按照几个基本原则进行分支管理：</p>
<p>首先，<code>master</code>分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；</p>
<p>那在哪干活呢？干活都在<code>dev</code>分支上，也就是说，<code>dev</code>分支是不稳定的，到某个时候，比如1.0版本发布时，再把<code>dev</code>分支合并到<code>master</code>上，在<code>master</code>分支发布1.0版本；</p>
<p>你和你的小伙伴们每个人都在<code>dev</code>分支上干活，每个人都有自己的分支，时不时地往<code>dev</code>分支上合并就可以了。</p>
<p>所以，团队合作的分支看起来就像这样：</p>

![](https://www.liaoxuefeng.com/files/attachments/919023260793600/0)

<h3>小结</h3>
<p>Git分支十分强大，在团队开发中应该充分应用。</p>
<p>合并分支时，加上<code>--no-ff</code>参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而<code>fast forward</code>合并就看不出来曾经做过合并。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='19'>Bug分支</a>

<div class="x-wiki-content x-main-content"><p>软件开发中，bug就像家常便饭一样。有了bug就需要修复，在Git中，由于分支是如此的强大，所以，每个bug都可以通过一个新的临时分支来修复，修复后，合并分支，然后将临时分支删除。</p>
<p>当你接到一个修复一个代号101的bug的任务时，很自然地，你想创建一个分支<code>issue-101</code>来修复它，但是，等等，当前正在<code>dev</code>上进行的工作还没有提交：</p>
<pre><code class="xml">$ git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to unstage)

	new file:   hello.py

Changes not staged for commit:
  (use "git add <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to update what will be committed)
  (use "git checkout -- <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to discard changes in working directory)

	modified:   readme.txt
</code></pre>
<p>并不是你不想提交，而是工作只进行到一半，还没法提交，预计完成还需1天时间。但是，必须在两个小时内修复该bug，怎么办？</p>
<p>幸好，Git还提供了一个<code>stash</code>功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：</p>
<pre><code class="ruby"><span class="variable">$ </span>git stash
<span class="constant">Saved</span> working directory <span class="keyword">and</span> index state <span class="constant">WIP</span> on <span class="symbol">dev:</span> f52c633 add merge
</code></pre>
<p>现在，用<code>git status</code>查看工作区，就是干净的（除非有没有被Git管理的文件），因此可以放心地创建分支来修复bug。</p>
<p>首先确定要在哪个分支上修复bug，假定需要在<code>master</code>分支上修复，就从<code>master</code>创建临时分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout master
<span class="constant">Switched</span> to branch <span class="string">'master'</span>
<span class="constant">Your</span> branch is ahead of <span class="string">'origin/master'</span> by <span class="number">6</span> commits.
  (use <span class="string">"git push"</span> to publish your local commits)

<span class="variable">$ </span>git checkout -b issue-<span class="number">101</span>
<span class="constant">Switched</span> to a new branch <span class="string">'issue-101'</span>
</code></pre>
<p>现在修复bug，需要把“Git is free software ...”改为“Git is a free software ...”，然后提交：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add readme.txt 
<span class="variable">$ </span>git commit -m <span class="string">"fix bug 101"</span>
[issue-<span class="number">101</span> <span class="number">4</span>c805e2] fix bug <span class="number">101</span>
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</code></pre>
<p>修复完成后，切换到<code>master</code>分支，并完成合并，最后删除<code>issue-101</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout master
<span class="constant">Switched</span> to branch <span class="string">'master'</span>
<span class="constant">Your</span> branch is ahead of <span class="string">'origin/master'</span> by <span class="number">6</span> commits.
  (use <span class="string">"git push"</span> to publish your local commits)

<span class="variable">$ </span>git merge --no-ff -m <span class="string">"merged bug fix 101"</span> issue-<span class="number">101</span>
<span class="constant">Merge</span> made by the <span class="string">'recursive'</span> strategy.
 readme.txt | <span class="number">2</span> +-
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</code></pre>
<p>太棒了，原计划两个小时的bug修复只花了5分钟！现在，是时候接着回到<code>dev</code>分支干活了！</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout dev
<span class="constant">Switched</span> to branch <span class="string">'dev'</span>

<span class="variable">$ </span>git status
<span class="constant">On</span> branch dev
nothing to commit, working tree clean
</code></pre>
<p>工作区是干净的，刚才的工作现场存到哪去了？用<code>git stash list</code>命令看看：</p>
<pre><code class="ruby"><span class="variable">$ </span>git stash list
stash@{<span class="number">0</span>}<span class="symbol">:</span> <span class="constant">WIP</span> on <span class="symbol">dev:</span> f52c633 add merge
</code></pre>
<p>工作现场还在，Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法：</p>
<p>一是用<code>git stash apply</code>恢复，但是恢复后，stash内容并不删除，你需要用<code>git stash drop</code>来删除；</p>
<p>另一种方式是用<code>git stash pop</code>，恢复的同时把stash内容也删了：</p>
<pre><code class="xml">$ git stash pop
On branch dev
Changes to be committed:
  (use "git reset HEAD <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to unstage)

	new file:   hello.py

Changes not staged for commit:
  (use "git add <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to update what will be committed)
  (use "git checkout -- <span class="tag">&lt;<span class="title">file</span>&gt;</span>..." to discard changes in working directory)

	modified:   readme.txt

Dropped refs/stash@{0} (5d677e2ee266f39ea296182fb2354265b91b3b2a)
</code></pre>
<p>再用<code>git stash list</code>查看，就看不到任何stash内容了：</p>
<pre><code class="ruby"><span class="variable">$ </span>git stash list
</code></pre>
<p>你可以多次stash，恢复的时候，先用<code>git stash list</code>查看，然后恢复指定的stash，用命令：</p>
<pre><code class="ruby"><span class="variable">$ </span>git stash apply stash@{<span class="number">0</span>}
</code></pre>
<p><iframe src="//player.bilibili.com/player.html?aid=51229109" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>在master分支上修复了bug后，我们要想一想，dev分支是早期从master分支分出来的，所以，这个bug其实在当前dev分支上也存在。</p>
<p>那怎么在dev分支上修复同样的bug？重复操作一次，提交不就行了？</p>
<p>有木有更简单的方法？</p>
<p>有！</p>
<p>同样的bug，要在dev上修复，我们只需要把<code>4c805e2 fix bug 101</code>这个提交所做的修改“复制”到dev分支。注意：我们只想复制<code>4c805e2 fix bug 101</code>这个提交所做的修改，并不是把整个master分支merge过来。</p>
<p>为了方便操作，Git专门提供了一个<code>cherry-pick</code>命令，让我们能复制一个特定的提交到当前分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch
* dev
  master
<span class="variable">$ </span>git cherry-pick <span class="number">4</span>c805e2
[master <span class="number">1</span>d4b803] fix bug <span class="number">101</span>
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+), <span class="number">1</span> deletion(-)
</code></pre>
<p>Git自动给dev分支做了一次提交，注意这次提交的commit是<code>1d4b803</code>，它并不同于master的<code>4c805e2</code>，因为这两个commit只是改动相同，但确实是两个不同的commit。用<code>git cherry-pick</code>，我们就不需要在dev分支上手动再把修bug的过程重复一遍。</p>
<p>有些聪明的童鞋会想了，既然可以在master分支上修复bug后，在dev分支上可以“重放”这个修复过程，那么直接在dev分支上修复bug，然后在master分支上“重放”行不行？当然可以，不过你仍然需要<code>git stash</code>命令保存现场，才能从dev分支切换到master分支。</p>
<h3>小结</h3>
<p>修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；</p>
<p>当手头工作没有完成时，先把工作现场<code>git stash</code>一下，然后去修复bug，修复后，再<code>git stash pop</code>，回到工作现场；</p>
<p>在master分支上修复的bug，想要合并到当前dev分支，可以用<code>git cherry-pick &lt;commit&gt;</code>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='20'>Feature分支</a>

<div class="x-wiki-content x-main-content"><p>软件开发中，总有无穷无尽的新的功能要不断添加进来。</p>
<p>添加一个新功能时，你肯定不希望因为一些实验性质的代码，把主分支搞乱了，所以，每添加一个新功能，最好新建一个feature分支，在上面开发，完成后，合并，最后，删除该feature分支。</p>
<p>现在，你终于接到了一个新任务：开发代号为Vulcan的新功能，该功能计划用于下一代星际飞船。</p>
<p>于是准备开发：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -b feature-vulcan
<span class="constant">Switched</span> to a new branch <span class="string">'feature-vulcan'</span>
</code></pre>
<p>5分钟后，开发完毕：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add vulcan.py

<span class="variable">$ </span>git status
<span class="constant">On</span> branch feature-vulcan
<span class="constant">Changes</span> to be <span class="symbol">committed:</span>
  (use <span class="string">"git reset HEAD &lt;file&gt;..."</span> to unstage)

	new <span class="symbol">file:</span>   vulcan.py

<span class="variable">$ </span>git commit -m <span class="string">"add feature vulcan"</span>
[feature-vulcan <span class="number">287773</span>e] add feature vulcan
 <span class="number">1</span> file changed, <span class="number">2</span> insertions(+)
 create mode <span class="number">100644</span> vulcan.py
</code></pre>
<p>切回<code>dev</code>，准备合并：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout dev
</code></pre>
<p>一切顺利的话，feature分支和bug分支是类似的，合并，然后删除。</p>
<p>但是！</p>
<p>就在此时，接到上级命令，因经费不足，新功能必须取消！</p>
<p>虽然白干了，但是这个包含机密资料的分支还是必须就地销毁：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch -d feature-vulcan
<span class="symbol">error:</span> <span class="constant">The</span> branch <span class="string">'feature-vulcan'</span> is <span class="keyword">not</span> fully merged.
<span class="constant">If</span> you are sure you want to delete it, run <span class="string">'git branch -D feature-vulcan'</span>.
</code></pre>
<p>销毁失败。Git友情提醒，<code>feature-vulcan</code>分支还没有被合并，如果删除，将丢失掉修改，如果要强行删除，需要使用大写的<code>-D</code>参数。。</p>
<p>现在我们强行删除：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch -<span class="constant">D</span> feature-vulcan
<span class="constant">Deleted</span> branch feature-vulcan (was <span class="number">287773</span>e).
</code></pre>
<p>终于删除成功！</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51229185" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<p>开发一个新feature，最好新建一个分支；</p>
<p>如果要丢弃一个没有被合并过的分支，可以通过<code>git branch -D &lt;name&gt;</code>强行删除。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='21'>多人协作</a>

<div class="x-wiki-content x-main-content"><p>当你从远程仓库克隆时，实际上Git自动把本地的<code>master</code>分支和远程的<code>master</code>分支对应起来了，并且，远程仓库的默认名称是<code>origin</code>。</p>
<p>要查看远程库的信息，用<code>git remote</code>：</p>
<pre><code class="ruby"><span class="variable">$ </span>git remote
origin
</code></pre>
<p>或者，用<code>git remote -v</code>显示更详细的信息：</p>
<pre><code class="ruby"><span class="variable">$ </span>git remote -v
origin  git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/learngit.git (fetch)
origin  git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/learngit.git (push)
</code></pre>
<p>上面显示了可以抓取和推送的<code>origin</code>的地址。如果没有推送权限，就看不到push的地址。</p>
<h3>推送分支</h3>
<p>推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin master
</code></pre>
<p>如果要推送其他分支，比如<code>dev</code>，就改成：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin dev
</code></pre>
<p>但是，并不是一定要把本地分支往远程推送，那么，哪些分支需要推送，哪些不需要呢？</p>
<ul>
<li>
<p><code>master</code>分支是主分支，因此要时刻与远程同步；</p>
</li>
<li>
<p><code>dev</code>分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；</p>
</li>
<li>
<p>bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；</p>
</li>
<li>
<p>feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。</p>
</li>
</ul>
<p>总之，就是在Git中，分支完全可以在本地自己藏着玩，是否推送，视你的心情而定！</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51229249" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>抓取分支</h3>
<p>多人协作时，大家都会往<code>master</code>和<code>dev</code>分支上推送各自的修改。</p>
<p>现在，模拟一个你的小伙伴，可以在另一台电脑（注意要把SSH Key添加到GitHub）或者同一台电脑的另一个目录下克隆：</p>
<pre><code class="ruby"><span class="variable">$ </span>git clone git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/learngit.git
<span class="constant">Cloning</span> into <span class="string">'learngit'</span>...
<span class="symbol">remote:</span> <span class="constant">Counting</span> <span class="symbol">objects:</span> <span class="number">40</span>, done.
<span class="symbol">remote:</span> <span class="constant">Compressing</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">21</span>/<span class="number">21</span>), done.
<span class="symbol">remote:</span> <span class="constant">Total</span> <span class="number">40</span> (delta <span class="number">14</span>), reused <span class="number">40</span> (delta <span class="number">14</span>), pack-reused <span class="number">0</span>
<span class="constant">Receiving</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">40</span>/<span class="number">40</span>), done.
<span class="constant">Resolving</span> <span class="symbol">deltas:</span> <span class="number">100</span>% (<span class="number">14</span>/<span class="number">14</span>), done.
</code></pre>
<p>当你的小伙伴从远程库clone时，默认情况下，你的小伙伴只能看到本地的<code>master</code>分支。不信可以用<code>git branch</code>命令看看：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch
* master
</code></pre>
<p>现在，你的小伙伴要在<code>dev</code>分支上开发，就必须创建远程<code>origin</code>的<code>dev</code>分支到本地，于是他用这个命令创建本地<code>dev</code>分支：</p>
<pre><code class="ruby"><span class="variable">$ </span>git checkout -b dev origin/dev
</code></pre>
<p>现在，他就可以在<code>dev</code>上继续修改，然后，时不时地把<code>dev</code>分支<code>push</code>到远程：</p>
<pre><code class="sql">$ git add env.txt

$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"add env"</span>
[dev <span class="number">7</span>a5e5dd] <span class="keyword">add</span> env
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
 <span class="keyword">create</span> mode <span class="number">100644</span> env.txt

$ git push origin dev
Counting objects: <span class="number">3</span>, done.
Delta compression <span class="keyword">using</span> up <span class="keyword">to</span> <span class="number">4</span> threads.
Compressing objects: <span class="number">100</span>% (<span class="number">2</span>/<span class="number">2</span>), done.
Writing objects: <span class="number">100</span>% (<span class="number">3</span>/<span class="number">3</span>), <span class="number">308</span> bytes | <span class="number">308.00</span> KiB/s, done.
Total <span class="number">3</span> (delta <span class="number">0</span>), reused <span class="number">0</span> (delta <span class="number">0</span>)
<span class="keyword">To</span> github.com:michaelliao/learngit.git
   f52c633.<span class="number">.7</span>a5e5dd  dev -&gt; dev
</span></code></pre>
<p><iframe src="//player.bilibili.com/player.html?aid=51229311" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>你的小伙伴已经向<code>origin/dev</code>分支推送了他的提交，而碰巧你也对同样的文件作了修改，并试图推送：</p>
<pre><code class="sql">$ cat env.txt
env

$ git add env.txt

$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"add new env"</span>
[dev <span class="number">7</span>bd91f1] <span class="keyword">add</span> new env
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
 <span class="keyword">create</span> mode <span class="number">100644</span> env.txt

$ git push origin dev
<span class="keyword">To</span> github.com:michaelliao/learngit.git
 ! [rejected]        dev -&gt; dev (non-fast-forward)
error: failed <span class="keyword">to</span> push <span class="keyword">some</span> refs <span class="keyword">to</span> <span class="string">'git@github.com:michaelliao/learngit.git'</span>
hint: Updates were rejected because the tip <span class="keyword">of</span> your <span class="keyword">current</span> branch <span class="keyword">is</span> behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: <span class="string">'git pull ...'</span>) before pushing again.
hint: See the <span class="string">'Note about fast-forwards'</span> <span class="keyword">in</span> <span class="string">'git push --help'</span> <span class="keyword">for</span> details.
</span></code></pre>
<p>推送失败，因为你的小伙伴的最新提交和你试图推送的提交有冲突，解决办法也很简单，Git已经提示我们，先用<code>git pull</code>把最新的提交从<code>origin/dev</code>抓下来，然后，在本地合并，解决冲突，再推送：</p>
<pre><code class="javascript">$ git pull
There is no tracking information <span class="keyword">for</span> the current branch.
Please specify which branch you want to merge <span class="keyword">with</span>.
See git-pull(<span class="number">1</span>) <span class="keyword">for</span> details.

    git pull &lt;remote&gt; <span class="xml"><span class="tag">&lt;<span class="title">branch</span>&gt;</span>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<span class="tag">&lt;<span class="title">branch</span>&gt;</span> dev
</span></code></pre>
<p><code>git pull</code>也失败了，原因是没有指定本地<code>dev</code>分支与远程<code>origin/dev</code>分支的链接，根据提示，设置<code>dev</code>和<code>origin/dev</code>的链接：</p>
<pre><code class="sql">$ git branch <span class="comment">--set-upstream-to=origin/dev dev</span>
Branch 'dev' <span class="operator"><span class="keyword">set</span> up <span class="keyword">to</span> track remote branch <span class="string">'dev'</span> <span class="keyword">from</span> <span class="string">'origin'</span>.
</span></code></pre>
<p>再pull：</p>
<pre><code class="ruby"><span class="variable">$ </span>git pull
<span class="constant">Auto</span>-merging env.txt
<span class="constant">CONFLICT</span> (add/add)<span class="symbol">:</span> <span class="constant">Merge</span> conflict <span class="keyword">in</span> env.txt
<span class="constant">Automatic</span> merge failed; fix conflicts <span class="keyword">and</span> <span class="keyword">then</span> commit the result.
</code></pre>
<p>这回<code>git pull</code>成功，但是合并有冲突，需要手动解决，解决的方法和分支管理中的<a href="http://www.liaoxuefeng.com/wiki/896043488029600/900004111093344" target="_blank">解决冲突</a>完全一样。解决后，提交，再push：</p>
<pre><code class="sql">$ git <span class="operator"><span class="keyword">commit</span> -m <span class="string">"fix env conflict"</span>
[dev <span class="number">57</span>c53ab] fix env conflict

$ git push origin dev
Counting objects: <span class="number">6</span>, done.
Delta compression <span class="keyword">using</span> up <span class="keyword">to</span> <span class="number">4</span> threads.
Compressing objects: <span class="number">100</span>% (<span class="number">4</span>/<span class="number">4</span>), done.
Writing objects: <span class="number">100</span>% (<span class="number">6</span>/<span class="number">6</span>), <span class="number">621</span> bytes | <span class="number">621.00</span> KiB/s, done.
Total <span class="number">6</span> (delta <span class="number">0</span>), reused <span class="number">0</span> (delta <span class="number">0</span>)
<span class="keyword">To</span> github.com:michaelliao/learngit.git
   <span class="number">7</span>a5e5dd.<span class="number">.57</span>c53ab  dev -&gt; dev
</span></code></pre>
<p><iframe src="//player.bilibili.com/player.html?aid=51229396" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<p>因此，多人协作的工作模式通常是这样：</p>
<ol>
<li>
<p>首先，可以试图用<code>git push origin &lt;branch-name&gt;</code>推送自己的修改；</p>
</li>
<li>
<p>如果推送失败，则因为远程分支比你的本地更新，需要先用<code>git pull</code>试图合并；</p>
</li>
<li>
<p>如果合并有冲突，则解决冲突，并在本地提交；</p>
</li>
<li>
<p>没有冲突或者解决掉冲突后，再用<code>git push origin &lt;branch-name&gt;</code>推送就能成功！</p>
</li>
</ol>
<p>如果<code>git pull</code>提示<code>no tracking information</code>，则说明本地分支和远程分支的链接关系没有创建，用命令<code>git branch --set-upstream-to &lt;branch-name&gt; origin/&lt;branch-name&gt;</code>。</p>
<p>这就是多人协作的工作模式，一旦熟悉了，就非常简单。</p>
<h3>推荐</h3>
<p>当你在准备进行使用 <code>多人协作</code>功能之前，为了更好的向其他的仓库管理以及代码编写者表达更加清楚的代码变动关系，以及创建一个项目的结构化的提交历史记录，推荐阅读：<a href='https://www.conventionalcommits.org/zh-hans/'>约定式提交</a>部分，并且根据其相关要求，对自己的提交记录进行相关规范。</p>
<h4>它的好处</h4>
<ul>
<li>自动化生成 CHANGELOG。</li>
<li>基于提交的类型，自动决定语义化的版本变更。</li>
<li>向同事、公众与其他利益关系者传达变化的性质。</li>
<li>触发构建和部署流程。</li>
<li>让人们探索一个更加结构化的提交历史，以便降低对你的项目做出贡献的难度。</li>

</ul>
<p>&nbsp;</p>

<h3>小结</h3>
<ul>
<li>
<p>查看远程库信息，使用<code>git remote -v</code>；</p>
</li>
<li>
<p>本地新建的分支如果不推送到远程，对其他人就是不可见的；</p>
</li>
<li>
<p>从本地推送分支，使用<code>git push origin branch-name</code>，如果推送失败，先用<code>git pull</code>抓取远程的新提交；</p>
</li>
<li>
<p>在本地创建和远程分支对应的分支，使用<code>git checkout -b branch-name origin/branch-name</code>，本地和远程分支的名称最好一致；</p>
</li>
<li>
<p>建立本地分支和远程分支的关联，使用<code>git branch --set-upstream branch-name origin/branch-name</code>；</p>
</li>
<li>
<p>从远程抓取分支，使用<code>git pull</code>，如果有冲突，要先处理冲突。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='22'>变基</a>

<div class="x-wiki-content x-main-content"><p>在上一节我们看到了，多人在同一个分支上协作时，很容易出现冲突。即使没有冲突，后push的童鞋不得不先pull，在本地合并，然后才能push成功。</p>
<p>每次合并再push后，分支变成了这样：</p>
<pre><code class="java">$ git log --graph --pretty=oneline --abbrev-commit
* d1be385 (HEAD -&gt; master, origin/master) init hello
*   e5e69f1 Merge branch <span class="string">'dev'</span>
|\  
| *   <span class="number">57</span>c53ab (origin/dev, dev) fix env conflict
| |\  
| | * <span class="number">7</span>a5e5dd add env
| * | <span class="number">7</span>bd91f1 add <span class="keyword">new</span> env
| |/  
* |   <span class="number">12</span>a631b merged bug fix <span class="number">101</span>
|\ \  
| * | <span class="number">4</span>c805e2 fix bug <span class="number">101</span>
|/ /  
* |   e1e9c68 merge with no-ff
|\ \  
| |/  
| * f52c633 add merge
|/  
*   cf810e4 conflict fixed
</code></pre>
<p>总之看上去很乱，有强迫症的童鞋会问：为什么Git的提交历史不能是一条干净的直线？</p>
<p>其实是可以做到的！</p>
<p>Git有一种称为rebase的操作，有人把它翻译成“变基”。</p>

![](https://www.liaoxuefeng.com/files/attachments/1216294032394112/l)

<p>先不要随意展开想象。我们还是从实际问题出发，看看怎么把分叉的提交变成直线。</p>
<p>在和远程分支同步后，我们对<code>hello.py</code>这个文件做了两次提交。用<code>git log</code>命令看看：</p>
<pre><code class="ruby"><span class="variable">$ </span>git log --graph --pretty=oneline --abbrev-commit
* <span class="number">582</span>d922 (<span class="constant">HEAD</span> -&gt; master) add author
* <span class="number">8875536</span> add comment
* d1be385 (origin/master) init hello
*   e5e69f1 <span class="constant">Merge</span> branch <span class="string">'dev'</span>
|\  
| *   <span class="number">57</span>c53ab (origin/dev, dev) fix env conflict
| |\  
| | * <span class="number">7</span>a5e5dd add env
| * | <span class="number">7</span>bd91f1 add new env
...
</code></pre>
<p>注意到Git用<code>(HEAD -&gt; master)</code>和<code>(origin/master)</code>标识出当前分支的HEAD和远程origin的位置分别是<code>582d922 add author</code>和<code>d1be385 init hello</code>，本地分支比远程分支快两个提交。</p>
<p>现在我们尝试推送本地分支：</p>
<pre><code class="sql">$ git push origin master
To github.com:michaelliao/learngit.git
 ! [rejected]        master -&gt; master (fetch first)
error: failed to push some refs to 'git@github.com:michaelliao/learngit.git'
hint: Updates were rejected because the remote contains work that you <span class="operator"><span class="keyword">do</span>
hint: <span class="keyword">not</span> have locally. This <span class="keyword">is</span> usually caused <span class="keyword">by</span> another repository pushing
hint: <span class="keyword">to</span> the same ref. You may want <span class="keyword">to</span> <span class="keyword">first</span> integrate the remote changes
hint: (e.g., <span class="string">'git pull ...'</span>) before pushing again.
hint: See the <span class="string">'Note about fast-forwards'</span> <span class="keyword">in</span> <span class="string">'git push --help'</span> <span class="keyword">for</span> details.
</span></code></pre>
<p>很不幸，失败了，这说明有人先于我们推送了远程分支。按照经验，先pull一下：</p>
<pre><code class="ruby"><span class="variable">$ </span>git pull
<span class="symbol">remote:</span> <span class="constant">Counting</span> <span class="symbol">objects:</span> <span class="number">3</span>, done.
<span class="symbol">remote:</span> <span class="constant">Compressing</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">1</span>/<span class="number">1</span>), done.
<span class="symbol">remote:</span> <span class="constant">Total</span> <span class="number">3</span> (delta <span class="number">1</span>), reused <span class="number">3</span> (delta <span class="number">1</span>), pack-reused <span class="number">0</span>
<span class="constant">Unpacking</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">3</span>/<span class="number">3</span>), done.
<span class="constant">From</span> github.<span class="symbol">com:</span>michaelliao/learngit
   d1be385..f005ed4  master     -&gt; origin/master
 * [new tag]         v1.<span class="number">0</span>       -&gt; v1.<span class="number">0</span>
<span class="constant">Auto</span>-merging hello.py
<span class="constant">Merge</span> made by the <span class="string">'recursive'</span> strategy.
 hello.py | <span class="number">1</span> +
 <span class="number">1</span> file changed, <span class="number">1</span> insertion(+)
</code></pre>
<p>再用<code>git status</code>看看状态：</p>
<pre><code class="sql">$ git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

nothing to <span class="operator"><span class="keyword">commit</span>, working tree clean
</span></code></pre>
<p>加上刚才合并的提交，现在我们本地分支比远程分支超前3个提交。</p>
<p>用<code>git log</code>看看：</p>
<pre><code class="sql">$ git log <span class="comment">--graph --pretty=oneline --abbrev-commit</span>
*   e0ea545 (HEAD -&gt; master) Merge branch 'master' of github.com:michaelliao/learngit
|\  
| * f005ed4 (origin/master) <span class="operator"><span class="keyword">set</span> exit=<span class="number">1</span>
* | <span class="number">582</span>d922 <span class="keyword">add</span> author
* | <span class="number">8875536</span> <span class="keyword">add</span> comment
|/  
* d1be385 init hello
...
</span></code></pre>
<p>对强迫症童鞋来说，现在事情有点不对头，提交历史分叉了。如果现在把本地分支push到远程，有没有问题？</p>
<p>有！</p>
<p>什么问题？</p>
<p>不好看！</p>
<p>有没有解决方法？</p>
<p>有！</p>
<p>这个时候，rebase就派上了用场。我们输入命令<code>git rebase</code>试试：</p>
<pre><code class="ruby"><span class="variable">$ </span>git rebase
<span class="constant">First</span>, rewinding head to replay your work on top of it...
<span class="constant">Applying</span><span class="symbol">:</span> add comment
<span class="constant">Using</span> index info to reconstruct a base tree...
<span class="constant">M</span>	hello.py
<span class="constant">Falling</span> back to patching base <span class="keyword">and</span> <span class="number">3</span>-way merge...
<span class="constant">Auto</span>-merging hello.py
<span class="constant">Applying</span><span class="symbol">:</span> add author
<span class="constant">Using</span> index info to reconstruct a base tree...
<span class="constant">M</span>	hello.py
<span class="constant">Falling</span> back to patching base <span class="keyword">and</span> <span class="number">3</span>-way merge...
<span class="constant">Auto</span>-merging hello.py
</code></pre>
<p>输出了一大堆操作，到底是啥效果？再用<code>git log</code>看看：</p>
<pre><code class="sql">$ git log <span class="comment">--graph --pretty=oneline --abbrev-commit</span>
* 7e61ed4 (HEAD -&gt; master) add author
* 3611cfe add comment
* f005ed4 (origin/master) <span class="operator"><span class="keyword">set</span> exit=<span class="number">1</span>
* d1be385 init hello
...
</span></code></pre>
<p>原本分叉的提交现在变成一条直线了！这种神奇的操作是怎么实现的？其实原理非常简单。我们注意观察，发现Git把我们本地的提交“挪动”了位置，放到了<code>f005ed4 (origin/master) set exit=1</code>之后，这样，整个提交历史就成了一条直线。rebase操作前后，最终的提交内容是一致的，但是，我们本地的commit修改内容已经变化了，它们的修改不再基于<code>d1be385 init hello</code>，而是基于<code>f005ed4 (origin/master) set exit=1</code>，但最后的提交<code>7e61ed4</code>内容是一致的。</p>
<p>这就是rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。</p>
<p>最后，通过push操作把本地分支推送到远程：</p>
<pre><code class="ruby"><span class="constant">Mac</span><span class="symbol">:~/learngit</span> michael<span class="variable">$ </span>git push origin master
<span class="constant">Counting</span> <span class="symbol">objects:</span> <span class="number">6</span>, done.
<span class="constant">Delta</span> compression using up to <span class="number">4</span> threads.
<span class="constant">Compressing</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">5</span>/<span class="number">5</span>), done.
<span class="constant">Writing</span> <span class="symbol">objects:</span> <span class="number">100</span>% (<span class="number">6</span>/<span class="number">6</span>), <span class="number">576</span> bytes | <span class="number">576.00</span> <span class="constant">KiB</span>/s, done.
<span class="constant">Total</span> <span class="number">6</span> (delta <span class="number">2</span>), reused <span class="number">0</span> (delta <span class="number">0</span>)
<span class="symbol">remote:</span> <span class="constant">Resolving</span> <span class="symbol">deltas:</span> <span class="number">100</span>% (<span class="number">2</span>/<span class="number">2</span>), completed with <span class="number">1</span> local object.
<span class="constant">To</span> github.<span class="symbol">com:</span>michaelliao/learngit.git
   f005ed4..<span class="number">7</span>e61ed4  master -&gt; master
</code></pre>
<p>再用<code>git log</code>看看效果：</p>
<pre><code class="sql">$ git log <span class="comment">--graph --pretty=oneline --abbrev-commit</span>
* 7e61ed4 (HEAD -&gt; master, origin/master) add author
* 3611cfe add comment
* f005ed4 <span class="operator"><span class="keyword">set</span> exit=<span class="number">1</span>
* d1be385 init hello
...
</span></code></pre>
<p>远程分支的提交历史也是一条直线。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51229455" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<ul>
<li>
<p>rebase操作可以把本地未push的分叉提交历史整理成直线；</p>
</li>
<li>
<p>rebase的目的是使得我们在查看历史提交的变化时更容易，因为分叉的提交需要三方对比。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='23'>标签管理</a>

<div class="x-wiki-content x-main-content"><p>发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。</p>
<p>Git的标签虽然是版本库的快照，但其实它就是指向某个commit的指针（跟分支很像对不对？但是分支可以移动，标签不能移动），所以，创建和删除标签都是瞬间完成的。</p>
<p>Git有commit，为什么还要引入tag？</p>
<p>“请把上周一的那个版本打包发布，commit号是6a5819e...”</p>
<p>“一串乱七八糟的数字不好找！”</p>
<p>如果换一个办法：</p>
<p>“请把上周一的那个版本打包发布，版本号是v1.2”</p>
<p>“好的，按照tag v1.2查找commit就行！”</p>
<p>所以，tag就是一个让人容易记住的有意义的名字，它跟某个commit绑在一起。</p>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='24'>创建标签</a>

<div class="x-wiki-content x-main-content"><p>在Git中打标签非常简单，首先，切换到需要打标签的分支上：</p>
<pre><code class="ruby"><span class="variable">$ </span>git branch
* dev
  master
<span class="variable">$ </span>git checkout master
<span class="constant">Switched</span> to branch <span class="string">'master'</span>
</code></pre>
<p>然后，敲命令<code>git tag &lt;name&gt;</code>就可以打一个新标签：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag v1.<span class="number">0</span>
</code></pre>
<p>可以用命令<code>git tag</code>查看所有标签：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag
v1.<span class="number">0</span>
</code></pre>
<p>默认标签是打在最新提交的commit上的。有时候，如果忘了打标签，比如，现在已经是周五了，但应该在周一打的标签没有打，怎么办？</p>
<p>方法是找到历史提交的commit id，然后打上就可以了：</p>
<pre><code class="ruby"><span class="variable">$ </span>git log --pretty=oneline --abbrev-commit
<span class="number">12</span>a631b (<span class="constant">HEAD</span> -&gt; master, <span class="symbol">tag:</span> v1.<span class="number">0</span>, origin/master) merged bug fix <span class="number">101</span>
<span class="number">4</span>c805e2 fix bug <span class="number">101</span>
e1e9c68 merge with no-ff
f52c633 add merge
cf810e4 conflict fixed
<span class="number">5</span>dc6824 &amp; simple
<span class="number">14096</span>d<span class="number">0</span> <span class="constant">AND</span> simple
b17d20e branch test
d46f35e remove test.txt
b84166e add test.txt
<span class="number">519219</span>b git tracks changes
e43a48b understand how stage works
<span class="number">1094</span>adb append <span class="constant">GPL</span>
e475afc add distributed
eaadf4e wrote a readme file
</code></pre>
<p>比方说要对<code>add merge</code>这次提交打标签，它对应的commit id是<code>f52c633</code>，敲入命令：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag v<span class="number">0</span>.<span class="number">9</span> f52c633
</code></pre>
<p>再用命令<code>git tag</code>查看标签：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag
v<span class="number">0</span>.<span class="number">9</span>
v1.<span class="number">0</span>
</code></pre>
<p>注意，标签不是按时间顺序列出，而是按字母排序的。可以用<code>git show &lt;tagname&gt;</code>查看标签信息：</p>
<pre><code class="sql">$ git <span class="operator"><span class="keyword">show</span> v0<span class="number">.9</span>
<span class="keyword">commit</span> f52c63349bc3c1593499807e5c8e972b82c8f286 (tag: v0<span class="number">.9</span>)
Author: Michael Liao &lt;askxuefeng@gmail.com&gt;
<span class="keyword">Date</span>:   Fri May <span class="number">18</span> <span class="number">21</span>:<span class="number">56</span>:<span class="number">54</span> <span class="number">2018</span> +<span class="number">0800</span>

    <span class="keyword">add</span> merge

diff --git a/readme.txt b/readme.txt
...
</span></code></pre>
<p>可以看到，<code>v0.9</code>确实打在<code>add merge</code>这次提交上。</p>
<p>还可以创建带有说明的标签，用<code>-a</code>指定标签名，<code>-m</code>指定说明文字：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag -a v<span class="number">0</span>.<span class="number">1</span> -m <span class="string">"version 0.1 released"</span> <span class="number">1094</span>adb
</code></pre>
<p>用命令<code>git show &lt;tagname&gt;</code>可以看到说明文字：</p>
<pre><code class="xml">$ git show v0.1
tag v0.1
Tagger: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 22:48:43 2018 +0800

version 0.1 released

commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (tag: v0.1)
Author: Michael Liao <span class="tag">&lt;<span class="title">askxuefeng@gmail.com</span>&gt;</span>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

diff --git a/readme.txt b/readme.txt
...
</code></pre>
<div class="uk-alert uk-alert-danger"><i class="uk-icon-warning"></i> 注意：标签总是和某个commit挂钩。如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。
</div>
<p><iframe src="//player.bilibili.com/player.html?aid=51229543" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<ul>
<li>
<p>命令<code>git tag &lt;tagname&gt;</code>用于新建一个标签，默认为<code>HEAD</code>，也可以指定一个commit id；</p>
</li>
<li>
<p>命令<code>git tag -a &lt;tagname&gt; -m "blablabla..."</code>可以指定标签信息；</p>
</li>
<li>
<p>命令<code>git tag</code>可以查看所有标签。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='25'>操作标签</a>

<div class="x-wiki-content x-main-content"><p>如果标签打错了，也可以删除：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag -d v<span class="number">0</span>.<span class="number">1</span>
<span class="constant">Deleted</span> tag <span class="string">'v0.1'</span> (was f15b0dd)
</code></pre>
<p>因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。</p>
<p>如果要推送某个标签到远程，使用命令<code>git push origin &lt;tagname&gt;</code>：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin v1.<span class="number">0</span>
<span class="constant">Total</span> <span class="number">0</span> (delta <span class="number">0</span>), reused <span class="number">0</span> (delta <span class="number">0</span>)
<span class="constant">To</span> github.<span class="symbol">com:</span>michaelliao/learngit.git
 * [new tag]         v1.<span class="number">0</span> -&gt; v1.<span class="number">0</span>
</code></pre>
<p>或者，一次性推送全部尚未推送到远程的本地标签：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin --tags
<span class="constant">Total</span> <span class="number">0</span> (delta <span class="number">0</span>), reused <span class="number">0</span> (delta <span class="number">0</span>)
<span class="constant">To</span> github.<span class="symbol">com:</span>michaelliao/learngit.git
 * [new tag]         v<span class="number">0</span>.<span class="number">9</span> -&gt; v<span class="number">0</span>.<span class="number">9</span>
</code></pre>
<p>如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除：</p>
<pre><code class="ruby"><span class="variable">$ </span>git tag -d v<span class="number">0</span>.<span class="number">9</span>
<span class="constant">Deleted</span> tag <span class="string">'v0.9'</span> (was f52c633)
</code></pre>
<p>然后，从远程删除。删除命令也是push，但是格式如下：</p>
<pre><code class="ruby"><span class="variable">$ </span>git push origin <span class="symbol">:refs/tags/v0</span>.<span class="number">9</span>
<span class="constant">To</span> github.<span class="symbol">com:</span>michaelliao/learngit.git
 - [deleted]         v<span class="number">0</span>.<span class="number">9</span>
</code></pre>
<p>要看看是否真的从远程库删除了标签，可以登陆GitHub查看。</p>
<p><iframe src="//player.bilibili.com/player.html?aid=51229695" style="width:100%;height:480px" scrolling="no" border="0" frameborder="no" framespacing="0"></iframe></p>
<h3>小结</h3>
<ul>
<li>
<p>命令<code>git push origin &lt;tagname&gt;</code>可以推送一个本地标签；</p>
</li>
<li>
<p>命令<code>git push origin --tags</code>可以推送全部未推送过的本地标签；</p>
</li>
<li>
<p>命令<code>git tag -d &lt;tagname&gt;</code>可以删除一个本地标签；</p>
</li>
<li>
<p>命令<code>git push origin :refs/tags/&lt;tagname&gt;</code>可以删除一个远程标签。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='26'>使用Github</a>

<div class="x-wiki-content x-main-content"><p>我们一直用GitHub作为免费的远程仓库，如果是个人的开源项目，放到GitHub上是完全没有问题的。其实GitHub还是一个开源协作社区，通过GitHub，既可以让别人参与你的开源项目，也可以参与别人的开源项目。</p>
<p>在GitHub出现以前，开源项目开源容易，但让广大人民群众参与进来比较困难，因为要参与，就要提交代码，而给每个想提交代码的群众都开一个账号那是不现实的，因此，群众也仅限于报个bug，即使能改掉bug，也只能把diff文件用邮件发过去，很不方便。</p>
<p>但是在GitHub上，利用Git极其强大的克隆和分支功能，广大人民群众真正可以第一次自由参与各种开源项目了。</p>
<p>如何参与一个开源项目呢？比如人气极高的bootstrap项目，这是一个非常强大的CSS框架，你可以访问它的项目主页<a href="https://github.com/twbs/bootstrap" target="_blank">https://github.com/twbs/bootstrap</a>，点“Fork”就在自己的账号下克隆了一个bootstrap仓库，然后，从自己的账号下clone：</p>
<pre><code class="ruby">git clone git<span class="variable">@github</span>.<span class="symbol">com:</span>michaelliao/bootstrap.git
</code></pre>
<p>一定要从自己的账号下clone仓库，这样你才能推送修改。如果从bootstrap的作者的仓库地址<code>git@github.com:twbs/bootstrap.git</code>克隆，因为没有权限，你将不能推送修改。</p>
<p>Bootstrap的官方仓库<code>twbs/bootstrap</code>、你在GitHub上克隆的仓库<code>my/bootstrap</code>，以及你自己克隆到本地电脑的仓库，他们的关系就像下图显示的那样：</p>
<pre style="font-size: 12px; line-height: 12px; border: none; white-space: pre; background-color: transparent;"><code class="language-ascii" style="font-family: &quot;Courier New&quot;, Consolas, monospace;">┌─ GitHub ────────────────────────────────────┐
│                                             │
│ ┌─────────────────┐     ┌─────────────────┐ │
│ │ twbs/bootstrap  │────&gt;│  my/bootstrap   │ │
│ └─────────────────┘     └─────────────────┘ │
│                                  ▲          │
└──────────────────────────────────┼──────────┘
                                   ▼
                          ┌─────────────────┐
                          │ local/bootstrap │
                          └─────────────────┘
</code></pre>
<p>如果你想修复bootstrap的一个bug，或者新增一个功能，立刻就可以开始干活，干完后，往自己的仓库推送。</p>
<p>如果你希望bootstrap的官方库能接受你的修改，你就可以在GitHub上发起一个pull request。当然，对方是否接受你的pull request就不一定了。</p>
<p>如果你没能力修改bootstrap，但又想要试一把pull request，那就Fork一下我的仓库：<a href="https://github.com/michaelliao/learngit" target="_blank">https://github.com/michaelliao/learngit</a>，创建一个<code>your-github-id.txt</code>的文本文件，写点自己学习Git的心得，然后推送一个pull request给我，我会视心情而定是否接受。</p>
<h3>小结</h3>
<ul>
<li>
<p>在GitHub上，可以任意Fork开源仓库；</p>
</li>
<li>
<p>自己拥有Fork后的仓库的读写权限；</p>
</li>
<li>
<p>可以推送pull request给官方仓库来贡献代码。</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='27'>自定义Git</a>

<div class="x-wiki-content x-main-content"><p>在<a href="/wiki/896043488029600/896067074338496">安装Git</a>一节中，我们已经配置了<code>user.name</code>和<code>user.email</code>，实际上，Git还有很多可配置项。</p>
<p>比如，让Git显示颜色，会让命令输出看起来更醒目：</p>
<pre><code class="ruby"><span class="variable">$ </span>git config --global color.ui <span class="keyword">true</span>
</code></pre>
<p>这样，Git会适当地显示不同的颜色，比如<code>git status</code>命令：</p>

![](https://www.liaoxuefeng.com/files/attachments/919059629641312/0)

<p>文件名就会标上颜色。</p>
<p>我们在后面还会介绍如何更好地配置Git，以便让你的工作更高效。</p>
</div>  

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

---

## <a id='28'>忽略特殊文件</a>

<div class="x-wiki-content x-main-content"><p>有些时候，你必须把某些文件放到Git工作目录中，但又不能提交它们，比如保存了数据库密码的配置文件啦，等等，每次<code>git status</code>都会显示<code>Untracked files ...</code>，有强迫症的童鞋心里肯定不爽。</p>
<p>好在Git考虑到了大家的感受，这个问题解决起来也很简单，在Git工作区的根目录下创建一个特殊的<code>.gitignore</code>文件，然后把要忽略的文件名填进去，Git就会自动忽略这些文件。</p>
<p>不需要从头写<code>.gitignore</code>文件，GitHub已经为我们准备了各种配置文件，只需要组合一下就可以使用了。所有配置文件可以直接在线浏览：<a href="https://github.com/github/gitignore" target="_blank">https://github.com/github/gitignore</a></p>
<p>忽略文件的原则是：</p>
<ol>
<li>忽略操作系统自动生成的文件，比如缩略图等；</li>
<li>忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如Java编译产生的<code>.class</code>文件；</li>
<li>忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件。</li>
</ol>
<p>举个例子：</p>
<p>假设你在Windows下进行Python开发，Windows会自动在有图片的目录下生成隐藏的缩略图文件，如果有自定义目录，目录下就会有<code>Desktop.ini</code>文件，因此你需要忽略Windows自动生成的垃圾文件：</p>
<pre><code class="ruby"><span class="comment"># Windows:</span>
<span class="constant">Thumbs</span>.db
ehthumbs.db
<span class="constant">Desktop</span>.ini
</code></pre>
<p>然后，继续忽略Python编译产生的<code>.pyc</code>、<code>.pyo</code>、<code>dist</code>等文件或目录：</p>
<pre><code class="ruby"><span class="comment"># Python:</span>
*.py[cod]
*.so
*.egg
*.egg-info
dist
build
</code></pre>
<p>加上你自己定义的文件，最终得到一个完整的<code>.gitignore</code>文件，内容如下：</p>
<pre><code class="ruby"><span class="comment"># Windows:</span>
<span class="constant">Thumbs</span>.db
ehthumbs.db
<span class="constant">Desktop</span>.ini

<span class="comment"># Python:</span>
*.py[cod]
*.so
*.egg
*.egg-info
dist
build

<span class="comment"># My configurations:</span>
db.ini
deploy_key_rsa
</code></pre>
<p>最后一步就是把<code>.gitignore</code>也提交到Git，就完成了！当然检验<code>.gitignore</code>的标准是<code>git status</code>命令是不是说<code>working directory clean</code>。</p>
<p>使用Windows的童鞋注意了，如果你在资源管理器里新建一个<code>.gitignore</code>文件，它会非常弱智地提示你必须输入文件名，但是在文本编辑器里“保存”或者“另存为”就可以把文件保存为<code>.gitignore</code>了。</p>
<p>有些时候，你想添加一个文件到Git，但发现添加不了，原因是这个文件被<code>.gitignore</code>忽略了：</p>
<pre><code class="ruby"><span class="variable">$ </span>git add <span class="constant">App</span>.<span class="class"><span class="keyword">class</span>
<span class="title">The</span> <span class="title">following</span> <span class="title">paths</span> <span class="title">are</span> <span class="title">ignored</span> <span class="title">by</span> <span class="title">one</span> <span class="title">of</span> <span class="title">your</span> .<span class="title">gitignore</span> <span class="title">files</span>:</span>
<span class="constant">App</span>.<span class="class"><span class="keyword">class</span>
<span class="title">Use</span> -<span class="title">f</span> <span class="title">if</span> <span class="title">you</span> <span class="title">really</span> <span class="title">want</span> <span class="title">to</span> <span class="title">add</span> <span class="title">them</span>.</span>
</code></pre>
<p>如果你确实想添加该文件，可以用<code>-f</code>强制添加到Git：</p>
<pre><code class="python">$ git add -f App.<span class="class"><span class="keyword">class</span>
</span></code></pre>
<p>或者你发现，可能是<code>.gitignore</code>写得有问题，需要找出来到底哪个规则写错了，可以用<code>git check-ignore</code>命令检查：</p>
<pre><code class="ruby"><span class="variable">$ </span>git check-ignore -v <span class="constant">App</span>.<span class="class"><span class="keyword">class</span>
.<span class="title">gitignore</span>:3:*.<span class="title">class</span>	<span class="title">App</span>.<span class="title">class</span></span>
</code></pre>
<p>Git会告诉我们，<code>.gitignore</code>的第3行规则忽略了该文件，于是我们就可以知道应该修订哪个规则。</p>
<h3>小结</h3>
<ul>
<li>
<p>忽略某些文件时，需要编写<code>.gitignore</code>；</p>
</li>
<li>
<p><code>.gitignore</code>文件本身要放到版本库里，并且可以对<code>.gitignore</code>做版本管理！</p>
</li>
</ul>
</div>

[![返回目录](https://s2.ax1x.com/2019/10/30/K4XDhT.png)](#0)

* 部分内容引用自[liaoxuefeng.com](https://www.liaoxuefeng.com/)

---

## <a id='29'>提问-答疑区</a>

[![](https://s2.ax1x.com/2019/10/30/K4aRPJ.png)](https://github.com/GUET-CSSTA-GC/ORG-POLICY/issues/1)

---

</font>
