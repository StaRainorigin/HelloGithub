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

而且一般来说，只有**第一次**拉取代码时，才会用克隆，克隆主要是还会帮我们建立于远程仓库的链接，后面如果别人往这个仓库里面上传代码，你想在本地更新一下，就不要用克隆了，下面会讲。

#### 关于为什么是三条命令
我个人理解，而且不是很准确，只是帮助理解。感兴趣的可以去看更专业的讲解
```bash
git add .
git commit -m "提交信息"
git push
```
其实真正上传的是 `git push` , 但是为什么会有前面两句代码呢，你听我慢慢道来。
##### `git add .`
其实git的运行机制中，有一个地方叫 "暂存区"，这个区域相当于你本地进行先提交一些更改，但是不上传，你可以在本地提交多次更改，到第三步的时候，把这些所有的更改全部上传。`git add .` 的作用就是将更改的文件添加到暂存区，其中点的意思是所有文件，就是所有更改过的文件。我觉得暂存区存在的意义，应该是增加容错之类的。
我们其实现在学习一般只会向暂存区提交一次，所以说什么时候该多次提交到暂存区和怎么提交到暂存区先不用管。
##### `git commit`
然后`git commit` 则是创建一个提交，上传的提交，就是它不是提交这个事情，就是“我要上传了啊！”的意思，然后`-m "提交信息"`中的 `-m` 的意思是我后面跟着的东西你就当做提交信息处理了，后面的字符串你可以写入这次提交代码，更改了哪些内容。这样提交的时候这个信息就会伴随着提交上去，别人看到你写的内容就可以清楚的知道你提交的代码是干什么的。
同时这个提交信息其实是有一定的书写规范的，但是咱们一开始嘛，别人能看得懂就行。

##### `git push`
真正的上传其实是他


### 推送内容到远程仓库
话说在前，此操作针对的仓库，必须是你自己

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
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331184753.png)
我们已经做完了更改了，但是这样只是在我本地进行了更改，我想把这些内容发布到网络上，我该怎么做呢？
只需要用下面的命令
```bash
git add .
git commit -m "提交信息"
git push
```
这三个命令一般都是同时出现的。我给大家操作一下
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185025.png)
大家可以看到我执行了三个命令，最后一步看起来好像是进行了一些网络的传输？像是上传了一些东西。其实这样就已经把我们的内容上传上去了。我们回到github的仓库看看文件是否已经上传。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185128.png)

我们可以看到，轻松秒杀。点开文件看看内容。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185219.png)
也是有的，甚至我们可以把这个当作文档的阅读器。


### 拉取新内容到本地仓库
之前我们说到，只有第一次拉取代码才会用克隆，那么后面用什么呢？就是拉取
命令为 `git pull`

我们来看一下，首先我通过某些方式，对远程仓库的内容进行了一些更改，我添加了几个文件，如下
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185726.png)
注意，这个文件只有远程仓库(github)有，我本地是不存在这个文件的，就相当于别人往这个仓库里面上传了内容

![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185925.png)
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331185940.png)
现在我需要更新一下我本地的文件，该怎么做呢？其实很简单，只需要输入
```bash
git pull
```
就行了
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331190022.png)
看起来好像是下载了一些东西，我们看看本地文件夹
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331190051.png)
确实也存在了。



### 提交内容到不属于自己的仓库，提交Pr
前面说了，我们的提交三件套
```bash
git add .
git commit -m "信息"
git push
```
只能用于自己的仓库，或者说自己有权限的仓库，别人的仓库是没有办法提交的。
说这也是哈，别人好不容易写的代码，如果所有人都能随便提交，那完了，我传一些乱七八糟的东西上去，这个仓库就毁了。所以说这个东西还是有一些安全保护措施的。
但是我真的有好的想法，我又跟作者不认识，我怎么才能为这个仓库坐出属于我自己的贡献呢？
也有个办法，就是提交Pr(Pull Requests)。
至于他为什么叫pull requests不叫push requests我就不清楚了……，明明是提交……

我直接说如何操作吧，首先我们要先找到这个仓库，上面有一个 `Fork`
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331191537.png)
这个 `Fork` 的意思，就是将这个项目，完完整整的复制一份，然后到你自己的仓库空间里。就是复制一份当你自己的仓库。
这个就好理解了，我不能改他们的仓库，那我复制一份到我自己这里来，我改我复制的这份不就行了吗，反正我复制过来就是我的了(复制粘贴工程师)。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331191630.png)
我们点Fork就会出现类似于创建仓库的界面，其实一般默认就行了，你也可以给它改个名，都行，我们这里默认。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331191818.png)

成功之后我们可以看到，一摸一样的仓库界面。但是你还记得吗，这个仓库我们是不是在我们组的organzation中创建的，并不是我自己的账号，现在我Fork之后，我自己的账号中也有一份一摸一样的了。而且仓库名称下面还会提醒你，"Fork from ..."

ok，现在这个仓库是我们自己的了，我们想怎么改怎么改，反正我们有权限，现在我们对这个仓库进行一些修改
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331192130.png)


现在有两个新文件了，那么我们只是在自己的仓库动手动脚的，人家原来仓库的作者也看不到啊，有什么用，光自己这里变了，人家那边也没有动静啊。
别急！
有没有看到一个按钮叫 `contribute`? 你自己创建的仓库可是没有这个按钮的，只有Fork的仓库才有，这个按钮可以开启一个Pr。这个pr的意思就是，开启一个请求，请求你现在的仓库和作者原来的仓库进行合并。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331192246.png)
这一下是不是就茅塞顿开了？
我可以fork一份到我自己这里，然后我提交一个pr，告诉作者，我做了一些贡献，你看看合适不给我合并上去。
我们点击Open pull request 可以跳转到这里
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331192458.png)这里显示的是我对这个仓库进行的修改，可以看到我们之前提到过的提交请求 "Fork的!!!!!!!!!!", 这就是我在 `git commit` 这一步时写的……
点击 Create pull request 我们就可以发起一个请求，写入我们想对作者说的话
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331192740.png)
然后就会发起一个请求，这样仓库的原作者就可以看到你提交的内容，作者看完你修改的内容后，他可以选择是否要合并你写的内容。
如果作者同意了你的和并请求，那么你就成功地为这个仓库做出了自己的贡献。

以下是仓库原作者看到的画面，Merge是合并的意思
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331192918.png)

合并成功了以后，我们看一下
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240331193008.png)
文件成功的出现了。

当然我这里可能有点抽象，因为我自己就是这个仓库的原作者。但是你们不一样，你们现在是没有这个仓库的权限的，所以你们可以在你们那边向我现在这个仓库提交pr，我来给你们通过，大家都来报个到！

[01Plant-Cainiao-Station/HelloGithub: 你好呀！](https://github.com/01Plant-Cainiao-Station/HelloGithub)

![image-20240331194501938](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/image-20240331194501938.png)

在此文件夹下，写一个名字为 自己的 id 的文件，然后提交pr

![image-20240331194534634](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/image-20240331194534634.png)

## 其他
还有一些其他的高级一点的用法。
1. 你有没有考虑到，如果我在本地对一个文件进行了修改，其他人也对这个文件进行了修改，且上传到了Github的远程仓库，我再拉取代码的时候，我们都对同一个文件进行了修改，那么我们应该保留谁的文件呢，或者说怎么才能同时保留我们两个人的成果呢？思考一下，这次先不讲
2. 分支又是什么东西，分支是干什么用的？
3. github除了存代码，还能干什么用呢？
