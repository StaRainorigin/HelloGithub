## 前提条件
1. 看完了
	1. [GitHub介绍：如何找公开的软件、项目、代码等 - 开源的意义和知识的突破 opensource](https://www.bilibili.com/video/BV1jg41197Zv?vd_source=6df2f60423608555adc65c0f2594130d)
	2. [git、github 保姆级教程入门，工作和协作必备技术，github提交pr - pull request](https://www.bilibili.com/video/BV1s3411g7PS?vd_source=6df2f60423608555adc65c0f2594130d
2. 注册好了Github账号
3. 配置好了Git，最后一步是将sshkey添加到你Github的账号上。这一步是为了将你当前电脑的环境算是与你的Github账号作为一个对接，这个涉及到一个权限的问题，待会说。

## 常用基础操作
之前也发过几篇相关的文章，命令看起来很难理解。其实在做很多操作的时候，他用到的那几个命令都是很固定的，所以我就不扯那些东西了，我直接告诉你们要完成一个事情的时候需要做什么。

### Github-创建远程仓库
所谓仓库，就是专门用来放代码的仓库，其实就是你的项目文件夹。其实咱们这里牵扯到的仓库有两个， 一个是本地仓库，一个是远程仓库。本地仓库就是在你电脑上的那个项目文件夹，远程仓库就是在网站上帮你托管的项目文件夹，这里就是Github的仓库。

我们首先来到Github的页面，点击右上角的头像，选择 "your repositories"，即可来到你自己的仓库页面。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331181752.png)
我们可以new一个仓库
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331181949.png)
然后我们会来到这么一个页面
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331182302.png)

我们现在只需要注意画圈的部分就行。
- Owner: 要以什么身份创建仓库，默认是你的账户，我这边我创建了一个咱们小组的 organization，我就以小组组织的身份创建仓库了。你们可以以自己账户的身份创建。
- Repository name，就是仓库的名称，几乎可以随便起
- Description 是对项目的描述，可以不写
- 第三个框, Public, Private，意思是这个仓库是否公开，Public就是公开，所有人都能看见这个仓库，Private就是不公开，只有你自己，和你授权过的人能看见这个仓库。
- 第四个框是否添加README文件，我建议是添加上，理论上来讲不加上不应该出现什么问题，但是我自己的经验是这文件不选，创建仓库的时候就是空的，空的仓库很容易出问题，所以先勾上。
  README文件就是对项目的一个说明，你们可以看看Github上其他公开的仓库，你往下滑都会有对项目的说明，那些说明就是你卸载README文件里的内容，README也是要用Markdown语法写哟，所以Markdown建议学~
- 剩下的.gitignore待会讲，license就是开源协议，先不用管，以后再说。

之后我们点右下角创建就会成功创建这个仓库，我们可以来到这个页面看一下。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331182822.png)
之后可能会带大家认识一下这个界面，这次就先不说了。

### 克隆仓库内容到本地
我创建的仓库地址: [01Plant-Cainiao-Station/HelloGithub: 你好呀！](https://github.com/01Plant-Cainiao-Station/HelloGithub)
这个操作，不仅仅是你自己的仓库，可以用，别人的仓库也可以用这一招！
点击仓库右上角绿色按钮，我们有好几种方式，
- 最直接的你可以 Download Zip，直接下载源码，这是最简单暴力的，但是不推荐。如果你只是想单纯下载仓库的代码，那么可以这么干，如果你想和这个仓库建立起一种联系，后面还要往这个仓库上传代码，则不要用这种方式。

![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183109.png)
- 另一种方式，也是我比较推荐的方式，就是点击HTTPS或者SSH，你会发现下面有个链接，HTTPS和SSH有着不同的链接，你复制这个链接。然后回到你自己的电脑上，找一个文件夹。我们在这个文件夹里打开一个终端，或者是你打开cmd或者git bash，把位置定位到这个文件夹。
  ![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183438.png)
  然后我们输入
  ```bash
  git clone 刚刚复制的地址
```
  然后回车，就会把代码拉到你这个目录下
  ![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183703.png)
像我这样就是拉取成功，有时候HTTPS的链接不好用，你可以换成SSH的链接，反正两个换着来。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183744.png)
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183758.png)
- 还有一种方式就是直接提供了用Visual Studio的方式打开，这个因为我不怎么用VS，所以不怎么常用，你们可以尝试一下。
  ![image](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331183844.png)
最后再提醒一下，拉取代码这个操作，不仅仅是你自己的仓库可以用，别人的仓库也可以用，你们可以直接回到上方点开我发的网址，拉一下我刚创建的这个仓库。

### 推送内容到仓库
上一步我们克隆了仓库，克隆仓库就是我们最开始的远程仓库，复制一份到你的电脑上，作为本地仓库，同时它会建立好远程仓库和本地仓库的链接，这个可以省去我们创建远程链接的操作(如果你好好看了视频，你会注意到这一步)。可以节省一些精力，比较方便，如果你用Download Zip的方式，则不会自动建立链接，然后就需要手动配置，很不方便。

接着上一步，我们需要在命令行中，进入到我们刚拉取的这个仓库，因为它还不是在仓库里面，还在仓库外面
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331184403.png)
我们需要输入
```bash
cd HelloGithub
```
来进入到这个HelloGithub中
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331184517.png)
我们可以看到输入命令后，我们第二行的路径已经变成了HelloGithub内部了，只有进入内部之后我们才可以对这个仓库使用命令。

刚才我们知道，现在的文件结构是这样的
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331184627.png)
我现在将我写的文档放到这个文件夹中，这就是我对这个仓库(或者说项目)的"更改"
更改完之后像这样子
