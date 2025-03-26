## 安装Jre

安装时显示脚本错误，经过多次尝试，下载了8u281版本，并且断网安装之后成功。

## Keil MDK高版本不再预装ARM Compiler Version5
解决办法：https://zhuanlan.zhihu.com/p/561047339

目前这个办法比较简洁高效，还有其他的方式但是没有这个方便。

主要就是复制一个安装ACC文件，然后再复制到Arm的文件夹中，再添加一下

以下是正文：

### 1、Keil MDK5.37不再预装ARM Compiler Version5

**Keil MDK5.37预装的是最新的ARM Compiler Version6**

先右击查看工程属性

![img](E:\Typora\assets\v2-1fa174e04964816ec13541afe14ec370_1440w.jpg)

在Target标签下，可以看到**Compiler Version5**就是丢失的

![img](E:\Typora\assets\v2-4e37c623e8c7e388468a503f5bf9be40_1440w.jpg)

### 2、以[固件库](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=固件库&zhida_source=entity)方式编程，编译之后全是错误

我是按照【[野火](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=野火&zhida_source=entity)】的单片机教程一步一步从最基础开始学习的。刚开始用**寄存器方式**编程的时候使用**Compiler Version6**进行编译没有任何问题。但是一旦使用ST官方的固件库，一编译就提示由344多个错误，如下图所示：

![动图封面](E:\Typora\assets\v2-ffe37589e0d133147a24bfdfbe583493_b.jpg)



我在网上搜索了产生这个编译错误的原因，原来学习STM32都会买[开发板](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=开发板&zhida_source=entity)，不管是野火，正点还是普中，给的资料例程都是好几年前，在keil5.37编译出错，因为没有[compiler version5](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=compiler+version5&zhida_source=entity)。

### 3、解决问题历程

#### **遇到问题之初**

起先我自己想了一下，既然我的**Keil MDK**安装的是最新版，那我把STM32的固件库也更新到最新版不就行了么！？软件和固件库都是最新的这总没问题了吧！？（事实证明我还是太天真了）于是我迅速进入ST官网下载了最新的STM32F10x[固件库Rev](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=固件库Rev&zhida_source=entity)3.6.0

【[https://www.st.com/content/st_com/en/products/embedded-software/mcu-mpu-embedded-software/stm32-embedded-software/stm32-standard-peripheral-libraries/stsw-stm32054.html](https://link.zhihu.com/?target=https%3A//www.st.com/content/st_com/en/products/embedded-software/mcu-mpu-embedded-software/stm32-embedded-software/stm32-standard-peripheral-libraries/stsw-stm32054.html)】

![img](E:\Typora\assets\v2-d91f2fbc3ccd7be39652104cbc1113e5_1440w.jpg)

野火使用的是Rev3.5.0的固件[库文件](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=库文件&zhida_source=entity)，我将Rev3.6.0里的固件库文件替换掉野火教程里老的文件，一点击编译，还是一大堆错误，看来我的思路错了，捣鼓环境什么的最头疼了。

这就是使用新版本软件的代价。经过一番网上冲浪以后，我又找到了解决办法

#### **被ARM官方耍（无法单独下载compiler version5离线包）**

在CSDN刨屎的过程中，前人留下的文章说明ARM有提供**compiler version5**的离线安装包

ARM官网，启动！！！【[https://developer.arm.com/downloads](https://link.zhihu.com/?target=https%3A//developer.arm.com/downloads)】，但是官网已取消支持

#### **问题真正解决阶段**

既然MDK5.37之前的版本有Arm Compiler 5，那就在不同盘安装一个MDK5.36，将MDK5.36[根目录](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=根目录&zhida_source=entity)下的Arm Compiler 5复制给MDK5.37实现双Compiler版本

这里提供一个快速下载ARM家软件的国内网站【[米尔科技](https://zhida.zhihu.com/search?content_id=212809851&content_type=Article&match_order=1&q=米尔科技&zhida_source=entity)】，算是代理商。

【[http://www.myir-tech.com/download.asp?anclassid=71](https://link.zhihu.com/?target=http%3A//www.myir-tech.com/download.asp%3Fanclassid%3D71)】

![img](E:\Typora\assets\v2-a2fd04094117349fc543e1717948cf80_1440w.jpg)



![img](E:\Typora\assets\v2-e46a8ba7519e1124763a4ade0329b322_1440w.jpg)

MDK5.36安装完成后，进入MDK5.36的根目录，复制一个叫【ARMCC】的文件夹，粘贴到MDK5.37的Keil_v5\ARM目录下即可

![img](E:\Typora\assets\v2-2bb688598f96cbffa745b59d3c83666d_1440w.jpg)

之后我们打开MDK5.37，点击**Manage Project Items**

![img](E:\Typora\assets\v2-f48a99fd7fae4e936fcaa1f151f64296_1440w.jpg)

在Folders/Extensions标签下，点击右侧省略号添加之前复制的ARMCC文件夹，这样子MDK5.37就有Arm Compiler 5了

![img](E:\Typora\assets\v2-8e1bdace2aae9a2cef3628be22b9567f_1440w.jpg)



![动图封面](E:\Typora\assets\v2-06157778414f279b8bcafa5dc566dc96_b.jpg)





![动图封面](E:\Typora\assets\v2-0cb80d5a6c5b10cd971e51a8e19b7712_b.jpg)



### **4、编译终于正常通过**

在工程选项中切换编译工具为**Arm Compiler 5**

**点击编译，顺利通过0 Errors，0 warnings！**

![动图封面](E:\Typora\assets\v2-f15d49ee4fc74a49f39f16d6389f537a_b.jpg)


链接：[pan.baidu.com/s/1rPaXDo](http://link.zhihu.com/?target=https%3A//pan.baidu.com/s/1rPaXDolIOwexq1Ry8h4dvg%3Fpwd%3D1111)

提取码：1111

## Keil导入纳芯微的pack失败

在导入纳芯微的1610pack的时候，使用Pack Installer一直失败，版本mdk541

在使用以前的电脑的时候可以安装成功，版本52x,认为是版本过高导致安装失败，下面是相应的解决办法及其链接

[keil5支持包无法正常导入的解决办法_keil pack包安装出现输入路径无效-CSDN博客](https://blog.csdn.net/qq_75055003/article/details/141754500)

> 1，把pack文件后缀名改成zip
>
> 2，解压到一个文件夹中
>
> 3，用Keil的Pack Installer进行安装，file-Import from Folder

![img](E:\Typora\assets\e5257efeaf664a8dafebafcfb6f27626.png)

还有另一种类似方法就是解压到一个文件夹中后手动放置到Keil的相应Pack文件夹中去

[解决Win11安装Keil芯片包失败/软件卡死/无法解压的问题_errors returned from cpackget-CSDN博客](https://blog.csdn.net/weixin_42518229/article/details/122477885)

## 链接JLink之后，总是提示版本过低，要升级

![img](E:\Typora\assets\131849yux4xdy4du4aurqa.png.thumb.jpg)

可能的解决办法，我没试过，本次的故障不知道为啥自己好了

1：升级Keil自带的J-link程序:
2：使用之前版本keil自带的J-link驱动替换掉现在的,也就是将..\Keil\ARM\Segger[文件夹](https://zhidao.baidu.com/search?word=文件夹&fr=iknow_pc_qb_highlight)替换为老版本的,这样里面的J-Link驱动也是老版本的,就不会提示J-Link更新了
3：卸载segger，下载了比较新的驱动重新安装，并将segger/jlinkarm_v440目录下的jlinkarm.dll拷贝到keil/arm/segger的目录下。再次使用MDK，提示升级，确定升级，但这次升级后，jlink确实可以识别。

### 更新

再次出现问题后，得出解决办法

<img src="E:\Typora\assets\image-20241127175542107.png" alt="image-20241127175542107" style="zoom:50%;" />

找到这个Updater程序，进行更新

但是可能需要稍等一会，之后就可以了

## Keil中有些地方申明.h头文件的会有红叉报错，但是编译不会报错

<img src="E:\Typora\assets\image-20241127175748488.png" alt="image-20241127175748488" style="zoom: 33%;" />

原因：代码路径有中文

解决办法：换成英文路径

但是目前我还没有尝试过，效果未知

## Git安装问题

首先是.gitconfig文件的放置位置，可能是我之前安装Cadence的时候工作目录被我更改了，改成了D:\Cadence_data，导致该文件会放置在这里面，他还会导致环境变量中的HOME变量变成这个位置，更改环境变量中的HOME变量位置即可，但是目前我把位置变了，后面不知道Cadence会不会出问题，更改日期2024/12/4晚上，有可能到了5号了。

Win11环境变量的位置：设置-系统-系统信息-高级系统设置

## Cadence安装问题

严格跟着教程走，在更改安装路径的时候只需要更改第一个，第二个工作目录不需要更改，更改了之后会比较麻烦，会把环境变量中的HOME变量更改为这个位置，目前不知道有没有问题。

目前HOME变量位置是在C:\user\yinqi中

另外我把D盘中的candence_data改成了cadence_data,去掉了一个c，不知道有没有影响，后面学习cadence时再说吧，不行就重装。

貌似没有影响。

## Git使用

对于我来说有两种方式

一种就是先在本地创建一个仓库，git init 初始化，之后和远程仓库关联

![image-20241206172528700](E:\Typora\assets\image-20241206172528700.png)

另一种就是直接clone下来，自己就会和远程仓库关联了

一个公钥好像是可以用于几个不同的网站的

> Git 全局设置:
>
> ```
> git config --global user.name "yog0"
> git config --global user.email "15228820+yog0@user.noreply.gitee.com"
> ```

> 创建 git 仓库:
>
> ```
> mkdir gitee
> cd gitee
> git init 
> touch README.md
> git add README.md
> git commit -m "first commit"
> git remote add origin git@gitee.com:yog0/gitee.git
> git push -u origin "master"
> ```
>
> 如果是github的话需要把master改成main,再github中还有一行命令`git branch -m main`指定当前分支为main
>
> 

> 已有仓库?
>
> ```
> cd existing_git_repo
> git remote add origin git@gitee.com:yog0/gitee.git
> git push -u origin "master"
> ```

gitee我是比较推荐clone下来再用，不要关联，这个网站有点不好用

github都可以的

后面我又生成了一个密钥，并且在.ssh文件夹中添加了config文件

> 内容如下
>
> ```
> # gitee
> Host gitee.com
> HostName gitee.com
> PreferredAuthentications publickey
> IdentityFile ~/.ssh/gitee_id_rsa
> # github
> Host github.com
> HostName github.com
> PreferredAuthentications publickey
> IdentityFile ~/.ssh/github_id_rsa
> ```
>
> 这里注意最后一行用的是私钥，不是公钥
>
> Github初始仓库:
>
> **…or create a new repository on the command line**
>
> ```
> echo "# notebook" >> README.md
> git init
> git add README.md
> git commit -m "first commit"
> git branch -M main
> git remote add origin git@github.com:Yogogogogo/notebook.git
> git push -u origin main
> ```
>
> **…or push an existing repository from the command line**
>
> ```
> git remote add origin git@github.com:Yogogogogo/notebook.git
> git branch -M main
> git push -u origin main
> ```
>
> 

## 立创EDA打不开eprj文件

日志显示：[错误] : 同步云端数据失败! SQLITE_ERROR: no such column: t1.parent_uuid

原因：epri文件变成已读文件了

解决方法：在文件属性中取消勾选已读即可。

## SoildWorks程序打不开

有两个任务不可以自动启动，可能是火绒等杀毒软件阻挡了，具体是哪两个任务我这里忘记了，到时候上网搜即可

