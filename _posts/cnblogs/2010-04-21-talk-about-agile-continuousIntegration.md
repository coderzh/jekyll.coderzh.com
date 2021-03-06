---
title: 三言两语话敏捷(2) - 持续集成
layout: post
category: 技术文章
date: 2010-04-21 01:04:00
---

这篇，我只谈&#8220;持续集成&#8221;。

有人说敏捷必须有持续集成，有人说持续集成就是敏捷。如果你还不了解持续集成，赶紧看看[《**持续集成**》第二版的中译本](http://article.yeeyan.org/view/2251/94882)。

持续集成的最大益处是<span style="color: red;">降低风险</span>，及时发现代码的缺陷，并让代码保持随时可用的状态。

如果不使用持续集成，会出现什么问题呢?

1. 到最后的集成时，会花费大量的时间，而且可能有很多BUG。

2. 开发过程会比较混乱。开发人员无法基于稳定的代码版本新增或修改代码。

<span style="color: red;">一个良好的持续集成应该包括，鼓励冲突编辑的源代码管理系统，自动构建系统，自动化测试系统，自动部署系统。</span>

构建一个持续集成环境成本非常低，通过一些开源的工具就能实现。比如，我们使用的SVN + [CruiseControl.NET](http://ccnet.thoughtworks.com/) +&nbsp; NAnt(MSBuild) + xUnit。

使用持续集成，我们需要注意什么？

#### 第一，重视持续集成的结果。

持续集成的结果有两种，不通过（红灯）和通过（绿灯）。尤其是亮红灯时，一定要让团队的所有人都看到，并且相关的人员必须重视，立即停下手头的工作去修复它。我见过有的团队使用一个大显示器，让在团队成员的中间，显示器中显眼的红灯很容易就被团队的成员看见，并且每个人看着都会不爽，直到去修复它。甚至，有的团队使用邮件进行骚扰，当编译不过时，不断的给Breaker或团队所有成员发邮件，直到解决为止。据说ThoughtWorks公司使用一种类似灯笼的东西，集成不过时，灯笼两红灯，非常的生动有趣。

另外一个简单的办法，就是要求团队成员在自己电脑开机时自动启动CCTray（如果使用CCNET的话），团队所有成员通过CCTray及时的得到集成的结果。

&#8220;谁破坏了构建，谁就要受到惩罚&#8221;，不过这里的&#8220;惩罚&#8221;并不是真正的惩罚，而是诸如请别人喝可乐之类的。每个人都有犯错误的时候，都有入库时忘记入某些文件的时候，我还记得有个同事因为破坏了构建，导致我和另外一个同事无法工作，最后解决后给我们送上的可乐。

#### 第二，入库前，先在本机集成。

这是一个好习惯。要让团队所有人都养成这个习惯，就必须让本机的集成做的越简单，比如做成一个Bat文件。Martin Fowler的文章里提到在本机集成两次，第一次在代码完成时集成，第二次更新最新的代码下来，如果有冲突，解决冲突后在集成一次。然后再入库。

本机集成通过，并不一定提交后在集成服务器就能通过。通常让构建亮红灯，都是因为本机编译没问题，到了构建服务器就出问题。最常见的原因就是漏了入库文件，以及，本机未更新最新代码进行的集成。

#### 第三，鼓励频繁的集成。

构建一般分为，日构建，实时构建，手工构建。我觉得，日构建肯定是必须的，能做实时构建就做实时构建。在完成一个小的迭代，或是功能时，就加入到构建中，让团队中的其他成员能够获得更加及时可用的代码。频繁的入库，集成，同时也能减少代码冲突产生的代价。

我见过有的团队，采用日构建加手工构建的方式，在进行手工构建时，有时还需要加入一些手工的干预，比如修改某个配置文件，替换某个文件等等。其实这是不鼓励的。应该尽量保证构建的自动执行。

#### 第四，加快集成的速度。

相信任何一个稍微大点的项目都会遇到这样的困境，完整的构建整个项目需要花费几个小时甚至更长的时间。这是难以忍受的，除非在半夜里进行的日构建。如果代码提交后，需要等待1小时才有结果，也是难以忍受的。我们之前就遇到过这样的问题。之后我找了很多办法，将实时构建的时间降了下来。比如将不同的工程区分开来、白天只编译Release，晚上Release和Debug一起编译、通过编写MSbuild插件实现入库文件的智能判断，只编译产生影响的代码工程。之前我写过一篇文章专门介绍过这个方法（[CCNET+MSBuild+SVN 实时构建的优化总结](http://www.cnblogs.com/coderzh/archive/2009/04/05/1429858.html)）。

#### 第五，自动测试。

CCNET中，有良好的扩展机制，可以在代码编译完成后自动执行单元测试案例。同时，CCNET还支持一些代码风格检查工具以及代码覆盖率工具(如NCover)。除此之外，一些集成测试案例也需要在构建完成后能够自动触发，这些案例通常会依赖一些具体环境，比如外部数据库，案例执行的时间会稍长。为了不影响自动构建的时间，需要使用单独的机器来触发和执行这些案例，甚至做成一个自动化分布式案例执行平台。比如我们自己实现的Box自动化测试平台。

&nbsp;

三言两语并非以偏概全，而是说说我心里所想的。想要了解更多关于持续集成，还是仔细看看Martin Fowler的[《**持续集成**》第二版的中译本](http://article.yeeyan.org/view/2251/94882)。如果有CCNET使用的一些问题，可以来问我。
