---
title: 白话云计算
layout: post
category: 技术文章
date: 2010-03-13 11:55:00
---

![cloudcomputing](http://images.cnblogs.com/cnblogs_com/coderzh/WindowsLiveWriter/4c0229025c1c_8900/cloudcomputing_thumb.jpg "cloudcomputing")

&nbsp;

凭着我对云计算的一知半解，用大白话表达一下对云计算的见解，如有不对的地方，也希望能够指出。首先，我们都知道，云计算现在很热，很多大公司，像Google，IBM，微软，都在风风火火的搞云计算。那，<span style="color: red;">到底什么是云计算呢？所谓&#8220;云&#8221;，大白话就是成千上万的计算机资源，&#8220;云计算&#8221;就是让这堆&#8220;云&#8221;为你工作，而你不需要知道哪台计算机为你工作。</span>

&#8220;云计算&#8221;的最终受益者是我们最终用户，我举几个例子：

#### 1. Google文档

你只需要一个浏览器，就可以享受Google为你提供的云存储服务。你不需要占用自己的硬盘空间，同时，你更不需要关心你的文档存储到哪台计算机上去了，你只需要知道，文档存储在&#8220;云&#8221;里。而这堆&#8220;云&#8221;中的计算机的存储能力远远超过了自己电脑的存储能力，同时，还提供了良好的备份机制，确保你的文档不会丢失。所以，使用Google文档，你需要做的只是向云中存储文档，以及向云索要文档，其他事情你都不需要关心。

#### 2. 手机

移动互联网是未来发展的趋势，越来越多的人开始使用手机上网。在购买手机的时候，通常我们都比较在意手机的硬件配置，比如，内存大小，处理能力，支持SD最大容量等等。可以想象，随着&#8220;云计算&#8221;的全面到来，我们不再那么关心手机本身的硬件配置，而手机只需要非常基础的配置，就能成为一个超级终端，每一个手机都相当于一个超级计算机。因为我们把手机所需要进行的计算、存储，全部交给了&#8220;云&#8221;来处理。

其实关于个人电脑也是一样的，IBM的创立者托马斯&#183;沃森曾表示，全世界只需要5台电脑就足够了。比尔&#183;盖茨则在一次演讲中称，个人用户的内存只需640K足矣(比尔的640K言论饱受评论质疑，的确，这个例子在这里是不适合的。见评论[韦恩卑鄙 v-zhewg @waynebaby](http://www.cnblogs.com/coderzh/archive/2010/03/13/talk-cloudcomputing.html#1779045))。由此可见，&#8220;云计算&#8221;所带来的变革是相当的大的。

#### 3. 无锡云计算中心

IBM与无锡市政府合作，在无锡建立中国第一个云计算中心。&#8220;中国第一个云计算中心&#8221;作何用途？原来，无锡市有一个建立软件园的经济开发项目。在该项目启动时所面临的一个难题是相当高昂的 IT 基础架构前期投资，而这笔资金必须在开始接受企业客户业务之前投入。&#8220;云计算中心&#8221;正好解决了这一难题。软件园的租户可以使用该数据中心以租赁软件开发和测试环境。

这样，一个新入住软件园的企业，不必再花费巨资购买大量的计算机硬件设备，不需要雇佣专业的机器维护人员（对于一个非IT企业确实不是必须的），而只需要简单的在一个Web页面上提交申请，比如，需要多少台服务器，CPU、硬盘有什么要求，需要部署哪些软件，通过租赁的方式，在提交表单之后1小时左右，你所需要的硬件设备全部以虚拟机的形式自动部署好，通过远程桌面或者SSH方式就可以开始操作。

对于一个创业型的公司，初期只需要租赁少量的IT资源，随着业务的扩大，随时都可以很快的增加IT资源。在业务萎缩时，可以减少IT资源的租赁，这些资源回收到&#8220;云计算中心&#8221;又可被其他公司重新利用。所以，这给软件园的公司提供了一个非常灵活的机制，同时，&#8220;云计算中心&#8221;的资源得到了充分的利用。

#### 4. Google App Engine

从程序员的角度来看云计算，自然我就想到了GAE。GAE是一个WEB开发平台，不仅提供了编程所需的SDK，还提供了应用需要部署的服务器环境。GAE和传统的Web服务有什么区别呢？传统的Web应用程序，我们都是部署到一台特定的服务器主机上。比如ASP.NET程序，我们需要在这台服务器上装IIS，把ASP.NET程序上传到服务器，然后设置Web站点。这台服务器硬件配置的好坏，一定程度决定了Web网站的性能。

而使用GAE，你只需要调用

<pre>appcfg.py update 你的应用名称</pre>

就完成了所有的程序的上传，部署。关键的是，你根本不知道你的程序上传到了哪里，部署在哪台服务器上。甚至，你都不知道服务器上保存的是哪些文件。你只需要知道，你的应用上传到了&#8220;云&#8221;上，你的应用部署到了&#8220;云&#8221;上，你的应用运行在&#8220;云&#8220;中。你享受的是高质量的服务器运算和存储能力。

#### 5. 云安全（云查杀）

说到云计算，不得不说到现在很多杀毒软件厂商提到的云安全技术，比如：金山毒霸、瑞星。

金山毒霸技术总监陈勇表示,&#8220;基于云安全，每个用户都是金山毒霸云安全庞大的安全网络的节点，都能受益于金山毒霸可信认证的庞大知识库及强大的后台样本分析服务。&#8221;

通过上面的话，其实我们已经明白了，每一个装有金山毒霸客户端的用户，其实都是&#8220;云&#8221;中的一个节点。用户通过扫描病毒，或者主动上报，将可疑的文件样本上传到了金山毒霸的后台样本分析服务器进行分析。样本分析服务享受广大用户（云）提供的样本，我们普通用户本身属于&#8220;云&#8221;中的一个节点，同时又享受着&#8220;云&#8221;所带来的病毒分析的服务。

### 云计算的好处

关于云计算，我理解的，具备以下好处：

#### 1. 降低成本

对于个人用户和企业来说，都不需要投入过多的资源在硬件设备上。

#### 2. 简单易用

不再需要关注某些不必要的细节，比如文档保存到哪里，哪个盘。就想我们家里使用电一样，我们不需要每家都自己发电，不需要知道发电的原理，而只需要向电力公司（云计算中心）购买电力就可以。程序设计中需要&#8220;封装&#8221;，生活中其实也需要&#8220;封装&#8221;。

#### 3. 安全

这里说的安全是指防止数据丢失。对于某些敏感数据，是不宜使用云计算的。我们使用自己的电脑保存文件，哪天电脑硬盘坏了，文件就丢失了。如果使用云计算的存储功能，我们不必担心文件丢失了，因为云计算中心有一套完备的自动备份和恢复机制，确保数据的完整。

#### 4. 资源利用

通过云计算，能够最大限度的合理利用资源。和现在的节能减排的理念是一致的。传统的方式下，会出现有的人资源紧缺，花费巨资引入硬件设备，而有的人的资源却处于闲置的状态。通过云计算，人们都按需使用资源，在不需要的时候将资源释放供他人使用。

#### 5. 良好的扩展性

&#8220;云&#8221;中的资源是可以进行扩展的。开始可能只是一朵小云，提供的服务也有限，随着业务扩大，随时都可以对云进行扩展。最终用户根本不需要关心这些扩展，对他们来说，可能的感觉就是云的存储能力变大了，计算能力变强了。

&nbsp;

关于&#8220;云计算&#8221;，你有什么不同的看法呢？愿闻其详。
