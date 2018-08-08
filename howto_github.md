## 1. 安装git工具,注册github帐号

Git工具的安装在Windows或Mac都相当简单, [建议参考这份指南](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)即可。装完git请到本地打开terminal，用"git --version"来测试是否正确运行，本例显示了版本2.18.0。 git版本号有些差异无妨，版本不要太旧即可。

<img src="/public/n6t0M9n16MlG76C6OnA_img_0.png" width="640">

git安装完成后，再到 [github官方网站](https://github.com/) 注册个人帐号，官网如下图。

<img src="/public/n6t0M9n16MlG76C6OnA_img_1.png" width="640">

## 2. 如何建立repo

若顺利注册与登入帐号，可如下图红圈处前往自己的 Profile

<img src="/public/n6t0M9n16MlG76C6OnA_img_2.png" width="640">

个人 Profile 画面如下，可从绿格子图观察到自己近期的活动与提交频率，但此时我们先到右上角的+号选取"New repository"来帮自己创建一个新的repo。

<img src="/public/n6t0M9n16MlG76C6OnA_img_3.png" width="640">

新的repository需填入几项信息，如下图红色箭头处，填写完成后按"Create repository"即可

<img src="/public/n6t0M9n16MlG76C6OnA_img_4.png" width="640">

如一切顺利，网页会自动转到这个repo的画面，可以看到下图当中，有项目名称和自动产生的README.md，代表在github那端repo已经创建完成。

然后我们准备下载这个项目，先去点击右方"Clone or download"，并把红圈处的网址copy起来。

<img src="/public/n6t0M9n16MlG76C6OnA_img_5.png" width="640">

然后打开本地的terminal，输入命令"git clone 刚刚复制的网址"，git就会自动下载项目档案，并看到类似下图的信息。进度 100% 下载完成后，应该可以用 ls 或 dir 看到它帮你建了一个目录，项目的档案都放在那个目录里。
```
git clone <your link>
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_6.png" width="640">

到这一步，自己的git repository就下载完成了，往后直接在目录内变更内容，就可以提交出去。

补充说明

Git工具会记住这个目录与github有联系，因为它在里面加了个隐藏的".git"目录，用来放相关信息。我们不用理会这个子目录，留着别碰就好。

<img src="/public/n6t0M9n16MlG76C6OnA_img_7.png" width="640">

## 3. 如何本地编辑

可以在项目的目录里，直接新增/修改/删除自己的文档，在提交以前，本地的变更都不会存到 github 上。

本例中，我在目录里用 vscode 写了一个python程序 test.py。当然，你也可以用 markdown 编辑器去编写 README.md 或建立任何文档。

<img src="/public/n6t0M9n16MlG76C6OnA_img_8.png" width="640">

## 4. 如何提交作业

#### * add 新档案

写好自己的程序或作业之后，本地应该多了很多档案和目录，首先我们要把让git知道有这个档案或子目录的存在，用命令 git add。
```
git add <filename>
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_9.png" width="640">

因为 test.py 在此是第一次出现的档案，我们才用 git add 告知 git 工具。新档案被 add 过后，未来修改它都不需要再 add。

#### * 提交作业

提交动作分成 commit 和 push 两个 terminal 命令。

commit 的意思是将整个目录内所有内容的变动，都融入 git 的储存结构里面，但此时所有数据都还在本地端。完成 commit 之后才用 push 命令，把本地的一切都上传到 github。

所以若没有 commit，所有档案更新都不会纪录。若没有 push，所有更新都不会上到 github。务实上我们可能在本地 commit 很多次，才用一次 push 送到github。

写好作业之后，首先打开 terminal，进入自己的 github 项目目录内，然后用 "git commit -a" 来commit。
```
git commit -a
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_10.png" width="640">

git commit 会先自动打开系统内的文字编辑器，要我们输入这次 commit 的说明。通常有必要帮每次 commit 写点简短的说明，未来查找历史记录才知道这次更新的目的是什么。

本例是 Mac 的 vim 被自动叫出来写说明。

<img src="/public/n6t0M9n16MlG76C6OnA_img_11.png" width="640">

把说明写好，储存并且退出编辑器之后，git 就会自动融合所有变更，并看到类似下图信息，它说我有 1 个 file 改变了，总共多加了 2 lines。

<img src="/public/n6t0M9n16MlG76C6OnA_img_12.png" width="640">

这样就 commit 完成了。

然后再用 "git push"，把本地累积的 commits 都 push 到 github上。如下图，它会问你的 github username 和 password，输入完成后就会自动上传。
```
git push
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_13.png" width="640">

看到画面出现 100% done，没有报错的话，提交作业就全部完成了。

<img src="/public/n6t0M9n16MlG76C6OnA_img_14.png" width="640">

然后 reload 或着回去自己 repo 的浏览器画面，应该能看见新东西。如下图，多了刚刚加入的 test.py，旁边有刚刚写的 commit 说明 "this is my first…."，还能把档案点开来看。

<img src="/public/n6t0M9n16MlG76C6OnA_img_15.png" width="640">

Ok，大功告成，接着把 repo 网址给出去，TA 或老师就能自己下载这份作业了。

以后还想修改自己作业，只要在本地反覆 commit + push 就行了，当然如果有全新的档案或子目录，要记得先 add 它们一次。

## 5. 如何下载老师的code

分成第一次下载以及后续更新两种情形。

#### * 第一次下载

第一次下载老师的code跟下载自己或任何人的code方法相同

先前往班主任给的项目repo网址，在下图红圈处copy repo的网址

<kbd>
  <img src="/public/n6t0M9n16MlG76C6OnA_img_16.png" width="640">
</kbd>

然后回 terminal，git clone 它就成了，例如 

```
git clone <your link>
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_17.png" width="640">

记得把上图的 repo 网址换成刚刚 copy 的。

#### * 后续更新

如果做过一次 clone，老师后来又更新了code，我们就不需要 clone 而是用 pull 来更新。

首先进去本地端老师code的目录，再用 git pull 命令。当画面出现 100% done 就更新完成了，下图红色箭头的意思是老师后来把 README.me 改了，里面增加两行字。
```
git pull
```
<img src="/public/n6t0M9n16MlG76C6OnA_img_18.png" width="640">

Ok，到此就下载老师code了，任何时候或着收到通知，git pull 一下就能让本地有老师最新的版本。

## 6. 操作建议

我们先按照 "6.如何下载老师的code" 将档案都下载成为目录。

然后再按照 "2.如何建立repo" 去开一个自己的 repo，项目名称取跟老师code不同的名称，并且下载下来(虽然此时只有一个 README.me)。

然后手动将老师的code档案 copy 到自己的目录，并用 git add 将档案加入自己的 repo。

这样本地端就能同时保持着老师code的目录，以及自己 repo 的目录，各自更新。

