---
title: howto_github
layout: post
author: yusen.bittiger
permalink: /howto_github/
source-id: 1m9QkBFsUkeU2HYShFZ6_3_cAluIe9aJtoUHpll6mZ1w
published: true
---
1. 安装git工具,注册github帐号

Git工具的安装在Windows或Mac都相当简单, [建议参考这份指南](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)即可。装完git请到本地打开terminal，用"git --version"来测试是否正确运行，本例显示了版本2.18.0。 git版本号有些差异无妨，版本不要太旧即可。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_0.png)

git安装完成后，再到 [github官方网站](https://github.com/) 注册个人帐号，官网如下图。

## ![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_1.png)

2. 如何建立repo

若顺利注册与登入帐号，可如下图红圈处前往自己的Profile

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_2.png)

个人Profile画面如下，可从绿格子图观察到自己近期的活动与提交频率，但此时我们先到右上角的+号选取"New repository"来帮自己创建一个新的repo。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_3.png)

新的repository需填入几项信息，如下图红色箭头处，填写完成后按"Create repository"即可

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_4.png)

如一切顺利，网页会自动转到这个repo的画面，可以看到下图当中，有项目名称和自动产生的README.md，代表在github那端repo已经创建完成。

然后我们准备下载这个项目，先去点击右方"Clone or download"，并把红圈处的网址copy起来。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_5.png)

然后打开本地的terminal，输入命令"git clone刚刚复制的网址"，git就会自动下载项目档案，并看到类似下图的信息。进度100%下载完成后，应该可以用ls或dir看到它帮你建了一个目录，项目的档案都放在那个目录里。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_6.png)

到这一步，自己的git repository就下载完成了，往后直接在目录内变更内容，就可以提交出去。

补充说明

Git工具会记住这个目录与github有联系，因为它在里面加了个隐藏的".git"目录，用来放相关信息。我们不用理会这个子目录，留着别碰就好。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_7.png)

3. 如何本地编辑

可以在项目的目录里，直接新增/修改/删除自己的文档，在提交以前，本地的变更都不会存到github上。

本例中，我在目录里用vscode写了一个python程序test.py。当然，你也可以用markdown编辑器去编写README.md或建立任何文档。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_8.png)

4. 如何提交作业

* add新档案

写好自己的程序或作业之后，本地应该多了很多档案和目录，首先我们要把让git知道有这个档案或子目录的存在，用命令git add。

"git add test.py"

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_9.png)

因为test.py在此是第一次出现的档案，我们才用git add告知git工具。新档案被add过后，未来修改它都不需要再add。

* 提交作业

提交动作分成commit和push两个terminal命令。

commit的意思是将整个目录内所有内容的变动，都融入git的储存结构里面，但此时所有数据都还在本地端。完成commit之后才用push命令，把本地的一切都上传到github。

所以若没有commit，所有档案更新都不会纪录。若没有push，所有更新都不会上到github。务实上我们可能在本地commit很多次，才用一次push送到github。

写好作业之后，首先打开terminal，进入自己的github项目目录内，然后用"git commit -a"来commit。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_10.png)

git commit会先自动打开系统内的文字编辑器，要我们输入这次commit的说明。通常有必要帮每次commit写点简短的说明，未来查找历史记录才知道这次更新的目的是什么。

本例是Mac的vim被自动叫出来写说明。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_11.png)

把说明写好，储存并且退出编辑器之后，git就会自动融合所有变更，并看到类似下图信息，它说我有1个file改变了，总共多加了2 lines。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_12.png)

这样就commit完成了。

然后再用"git push"，把本地累积的commits都push到github上。如下图，它会问你的github username和password，输入完成后就会自动上传。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_13.png)

看到画面出现100% done，没有报错的话，提交作业就全部完成了。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_14.png)

然后reload或着回去自己repo的浏览器画面，应该能看见新东西。如下图，多了刚刚加入的test.py，旁边有刚刚写的commit说明"this is my first…."，还能把档案点开来看。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_15.png)

Ok，大功告成，接着把repo网址给出去，TA或老师就能自己下载这份作业了。

以后还想修改自己作业，只要在本地反覆commit + push就行了，当然如果有全新的档案或子目录，要记得先add它们一次。

5. 如何下载老师的code

分成第一次下载以及后续更新两种情形。

* 第一次下载

第一次下载老师的code跟下载自己或任何人的code方法相同

先前往班主任给的项目repo网址，在下图红圈处copy repo的网址

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_16.png)

然后回terminal，git clone它就成了，例如 

git clone [https://github.com/yusenbittiger/ds_001_assignment_1.git](https://github.com/yusenbittiger/ds_001_assignment_1.git)

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_17.png)

记得把上图的repo网址换成刚刚copy的。

* 后续更新

如果做过一次clone，老师后来又更新了code，我们就不需要clone而是用pull来更新。

首先进去本地端老师code的目录，再用git pull命令。当画面出现100% done就更新完成了，下图红色箭头的意思是老师后来把README.me改了，里面增加两行字。

![image alt text]({{ site.url }}/public/IbHkxL54XgqXD78vHGA_img_18.png)

Ok，到此就下载老师code了，任何时候或着收到通知，git pull一下都能让本地有老师最新的版本。

6. 操作建议

我们先按照"6.如何下载老师的code"将档案都下载成为目录。

然后再按照"2.如何建立repo"去开一个自己的repo，项目名称取跟老师code不同的名称，并且下载下来(虽然此时只有一个README.me)。

然后手动将老师的code档案copy到自己的目录，并用git add将档案加入自己的repo。

这样本地端就能同时保持着老师code的目录，以及自己repo的目录，各自更新。

