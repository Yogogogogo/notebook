## Part 1 软件系统安装及综合设置

### 1.Orcad常用菜单介绍与推荐设置

![image-20260104231822596](./assets/image-20260104231822596.png)

## 2.Allegro常用菜单介绍与推荐设置

一般使用Allegro X Designer Layout这个组件，功能比较强大

![image-20260112233216606](./assets/image-20260112233216606.png)

在菜单栏中有小图标的命令会在下面的快捷命令那一栏显示

当某些窗口不小心取消后，可以在View–>UI Settings–>Reset UI to Default,重置窗口

主要选项是在View—>Windows中勾选，不用重置的

![image-20260112235124659](./assets/image-20260112235124659.png)

上图为推荐页面设置

## 3.系统常用设置参数的保存与调用 

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

## 拓展插件skill的设置与安装方法

