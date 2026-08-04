## Part 1 软件系统安装及综合设置

### 1.Orcad常用菜单介绍与推荐设置

![image-20260104231822596](./assets/image-20260104231822596.png)

### 2.Allegro常用菜单介绍与推荐设置

一般使用Allegro X Designer Layout这个组件，功能比较强大

![image-20260112233216606](./assets/image-20260112233216606.png)

在菜单栏中有小图标的命令会在下面的快捷命令那一栏显示

当某些窗口不小心取消后，可以在View–>UI Settings–>Reset UI to Default,重置窗口

主要选项是在View—>Windows中勾选，不用重置的

![image-20260112235124659](./assets/image-20260112235124659.png)

上图为推荐页面设置

### 3.系统常用设置参数的保存与调用 

Orcad的设置不需要每次都更改保存，这点我感觉和AD很像，原理图不需要过多设置，每个工程的原理图设置都是一样的，但是每个PCB都有自己的规则设置

Allegro参数的导出File–>Export–>parameters,然后勾选需要导出的内容，空文件(即打开allegro之后的默认unname的文件)的话是没有那么多选项的

![image-20260129234700395](./assets/image-20260129234700395.png)

  ![image-20260420234817514](./assets/image-20260420234817514.png)

design setting的内容就是如上图所示的

![image-20260420235005869](./assets/image-20260420235005869.png)

Artwork的内容是Manufacture->Artwork中的内容，是光绘文件，可以复用的

![image-20260420235243345](./assets/image-20260420235243345-1776700364969-1.png)

层叠颜色和调色板就是上图箭头所指地方的参数，包括每层的走线铜皮是什么颜色的

字体颜色大小可以导出：Setup->Deesign parameter->Text

视频中的示例网络颜色和应用或命令参数没有勾选，导出后是一个后缀为prm的文件

导入参数：File->Import–>parameters

### 拓展插件skill的设置与安装方法

比较新的版本不支持使用bat文件安装

![image-20260428225719880](./assets/image-20260428225719880.png)

![image-20260428225857632](./assets/image-20260428225857632.png)

![image-20260428225954565](./assets/image-20260428225954565.png)

注释符号是英文;



![image-20260428230227154](./assets/image-20260428230227154.png)

### 各类文件后缀介绍以及文件归档

>  **Orcad文件后缀**
>
> .dsn：原理图文件
> .opj：项目管理文件    这个打开原理图后会自动生成
> .olb：原理图库文件
> .net：网络表文件
> .lib：仿真模型描述库文件
> .log：记录说明文件

> **Allegro文件后缀**
>
> ![image-20260511232945808](./assets/image-20260511232945808.png)
>
> .dra是封装编辑文件，生成的调用文件就像是.fsm这样的文件
>
> 我的理解就是dra是封装创建和编辑使用的，..sm是在allegro被调用的文件
>
> 

### 项目工程为文件创建以及项目文件管理

![image-20260521232747761](./assets/image-20260521232747761.png)

一般都是File–>New–>project,allegro的内容会 多一点（应该是指下图中的TYPE会比orcad多一点）

![image-20260521233335608](./assets/image-20260521233335608.png)

课件资料里面有一个bat文件，双击就可以创建项目规范的那些文件夹

## Part 2 原件库（原理图库）的创建

###  元件的绘制创建实例

新建库：File-->New-->Library，之后选中文件右击save as更改位置

![image-20260804144710773](assets/image-20260804144710773.png)



![image-20260804153835034](assets/image-20260804153835034.png)

画框的时候默认的那个虚线框是一定要沿着格点移动的，但是在放置里面重新选择画的时候那个snap gird是可以对他起作用的

![image-20260804173623263](assets/image-20260804173623263.png)

![image-20260804173640203](assets/image-20260804173640203.png)

![image-20260804173702951](assets/image-20260804173702951.png)

![image-20260804173743954](assets/image-20260804173743954.png)

pin脚的名称改成上划线使用斜杠就可以

![image-20260804175019957](assets/image-20260804175019957.png)

多part器件这里是选择了homogeneous也就是两部分器件一样，所以只用画一个就可以，但是貌似左侧不会显示两个器件，使用快捷点ctrl+B进行切换

画线的时候按住shift可以切换画线角度，封闭图形才可以进行填充

 填充的颜色需要在preferences中的part body进行选择

Text的颜色是要和part body颜色一致的

![image-20260804180133082](assets/image-20260804180133082.png)

view-->package可以预览上图这样的界面，按理说不应该使用homogenerous的，现在的情况是只有管脚号可以更改，其他的都不可以

