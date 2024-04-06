## Visual Studio项目创建


未更新完


### 创建项目，选择新项目
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328115121.png)
### 选择空项目
因为仅仅是作为练习，还没有做项目级别的工作，先使用空项目即可
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328115153.png)
### 设置项目名称
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328115310.png)

### 点击创建
点击创建，即可成功创建项目
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328120353.png)

### 其他
以下是我个人理解，一般来说，
源文件是存放的一些比较核心的代码文件，如 `*.cpp` , ` *.c` 等类型的文件
头文件是C/C++特有的，就是 `*.h` (也许也有 `.cpp/.c` 的?)文件
资源文件是一些其他的非代码的，如一些图片文件等。



---
## Github源码上传
我们先写一些代码。
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328121315.png)
## 添加.gitignore文件
按理来说这一步不应该在这里出现，但是为了我们上传的代码的简洁性，我们还是提前在这里编辑一下这个文件。

.gitignore文件是我们自己创建的一个文本文件，这个文件会放在项目的目录下。
为什么会有这个文件? 
	当我们写一个项目时，我们会有一些不希望上传到代码仓库的文件，比如C/C++文件编译时生成的.exe文件，还有一些我们临时自己创建的一些用来测试我们自己的代码的文件。在多人合作写项目时，如果上传了一些不必要的文件，会导致项目结构非常混乱，降低合作开发的效率。
	.gitignore文件则就是为了解决这个问题。
使用方式
	它的用法其实很简单: 只需要在项目目录创建一个`.gitignore`文件(最简单的，创建一个`新建文本文件.txt` 然后把名字改为 `.gitignore` ), 然后写上你不想上传的文件路径，或者文件夹路径。这样在推送本地代码到github仓库时，就不会把这些你在 `.gitignore` 中标注的文件上传上去
### 操作流程
右键项目名字 —— 在资源管理器中打开文件夹
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328123000.png)
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328123021.png)



### 创建Github仓库
为了简化操作，我们直接使用Visual Studio来进行源代码管理，点击IDE右下角的 `添加到源代码管理` 然后选择 `Git` 
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328121445.png)
这里 `添加README.md` 最好是打上勾，不写这个貌似在创建仓库时会出现问题。
下面你们可以登陆一下自己的Github账号，仓库名称就是你这个项目在上传到Github上之后，在你的账号下生成的关于这个项目的仓库的名称。
设置好之后我们选择 `创建并推送`
![image.png](https://starain-1252568110.cos.ap-beijing.myqcloud.com/blog/20240328122011.png)

