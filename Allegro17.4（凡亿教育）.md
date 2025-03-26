## Capture软件操作界面及常用设置

### 启动软件的更改

在File---change product中，可以更改启动的设置

<img src="E:\Typora\assets\image-20241231175001017.png" alt="image-20241231175001017" style="zoom:33%;" />

一般都是使用OrCAD capture CIS，这个的功能比较全

### 系统颜色的更改

Option---perference

<img src="E:\Typora\assets\image-20241231175206971.png" alt="image-20241231175206971" style="zoom:33%;" />

在这里可以进行系统颜色的更改

格点设置也是在preference中，有个Grid Display，可以在这里面进行更改，分为两部分，原理图和原理图库的格点

<img src="E:\Typora\assets\image-20250309224046953.png" alt="image-20250309224046953" style="zoom: 25%;" />

前面的复选框是打印的时候用的

## 自带元件库介绍

安装目录--tools--capture--library

具体每个库都是干什么的在ppt中有，需要的时候进行查阅即可

## 创建元器件库

File--New--Library，文件后缀是olb

如果路径不满意，可以Flie--Save as另存为,==不建议放在中文路径下面，会出问题。==

注意这个创建的是一个库，不是一个元器件

### 添加元器件

右击新建好的库--New Part

<img src="E:\Typora\assets\image-20250107222357025.png" alt="image-20250107222357025" style="zoom:33%;" />

页面的放大缩小快捷键O，I

<img src="E:\Typora\assets\image-20250107222953150.png" alt="image-20250107222953150" style="zoom: 25%;" />

或者Ctrl+滚轮

放置管脚的时候不用分太细

<img src="E:\Typora\assets\image-20250107223607407.png" alt="image-20250107223607407" style="zoom:50%;" />

<img src="E:\Typora\assets\image-20250107224719534.png" alt="image-20250107224719534" style="zoom:33%;" />

放置管脚可以单个放置也可以阵列放置

阵列放置的可以用负号进行递减

<img src="E:\Typora\assets\image-20250107224820120.png" alt="image-20250107224820120" style="zoom:33%;" />

例如上图左边就是递增放置，右边是递减放置

<img src="E:\Typora\assets\image-20250107225046966.png" alt="image-20250107225046966" style="zoom:33%;" />

之后进行Editor pins

<img src="E:\Typora\assets\image-20250107225234091.png" alt="image-20250107225234091" style="zoom:33%;" />

## 原理图设置

新建工程会自动出现原理图，新建原理图也会自动出现工程，OLB文件可以后续添加

旋转元器件快捷键R

镜像元器件快捷键Edit--Mirror
