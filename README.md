
CODEC是**CO**ding and **DEC**的缩写，是面向视频等多媒体的编解码技术。
随着视频采集设备不断发展，为人们的生活、娱乐、工作提供了大量高动态范围、宽色域的视频，据估计，互联网上有80%的数据信息都来源于视频
然而，尽管信息通信技术也在不断发展，但由于Jevons悖论的作用，视频存储和传输的压力仍然巨大，因此CODEC技术仍需不断更新和发展
研究和制定CODEC的标准组织包括ISO/IEC的MPEG和ITU的VCEG（联合专家组JVET），同时也包括中国的AVS，还有以Google等企业发起的AOM
CODEC的标准研究已有几十年，最近的标准版本是H.266/VVC，以及AVS所推出的AVS3
基于神经网络的智能算法是CODEC当下的焦点研究方向，以实现模块替换或整体替换传统基于块的方法
该Repository是采用PyTorch作为工具来进行CODEC算法实现，适合Pytorch和CODEC编程的入门

*Note: Jevons悖论：“The efficiency with which a resource is used tends to increase (rather than decrease) the rate of consumption of that resource."*

以下是Pytorch的基本介绍和安装流程

===
### 1 基本情况
PyTorch是一个开源的Python机器学习库，基于Torch，用于自然语言处理等应用程序。
2017年1月，由Facebook人工智能研究院（FAIR）基于Torch推出了PyTorch。
它是一个基于Python的可续计算包，提供两个高级功能：

1. 具有强大的GPU加速的张量计算（如NumPy）。

2. 包含自动求导系统的的深度神经网络。

官方教程中文版地址：http://www.pytorch123.com/

### 2 基于Torch开发的

要介绍PyTorch之前，不得不说一下Torch。Torch是一个有大量机器学习算法支持的科学计算框架，是一个与Numpy类似的张量（Tensor） 操作库，其特点是特别灵活，但因其采用了小众的编程语言是Lua，所以流行度不高，这也就有了PyTorch的出现。所以其实Torch是 PyTorch的前身，它们的底层语言相同，只是使用了不同的上层包装语言。

除了Facebook之外，Twitter、GMU和Salesforce等机构都采用了PyTorch。

PyTorch是一个基于Torch的Python开源机器学习库，用于自然语言处理等应用程序。它主要由Facebookd的人工智能小组开发，不仅能够 实现强大的GPU加速，同时还支持动态神经网络，这一点是现在很多主流框架如TensorFlow都不支持的。 PyTorch提供了两个高级功能： * 具有强大的GPU加速的张量计算（如Numpy） * 包含自动求导系统的深度神经网络

除了Facebook之外，Twitter、GMU和Salesforce等机构都采用了PyTorch。

### 3 与主流其他框架的区别

TensorFlow和Caffe都是命令式的编程语言，而且是静态的，首先必须构建一个神经网络，然后一次又一次使用相同的结构，如果想要改变网络的结构，就必须从头开始。但是对于PyTorch，通过反向求导技术，可以让你零延迟地任意改变神经网络的行为，而且其实现速度快。正是这一灵活性是PyTorch对比TensorFlow的最大优势。

另外，PyTorch的代码对比TensorFlow而言，更加简洁直观，底层代码也更容易看懂，这对于使用它的人来说理解底层肯定是一件令人激 动的事。

所以，总结一下PyTorch的优点： * 支持GPU * 灵活，支持动态神经网络 * 底层代码易于理解 * 命令式体验 * 自定义扩展

当然，现今任何一个深度学习框架都有其缺点，PyTorch也不例外，对比TensorFlow，其全面性处于劣势，目前PyTorch还不支持快速傅里 叶、沿维翻转张量和检查无穷与非数值张量；针对移动端、嵌入式部署以及高性能服务器端的部署其性能表现有待提升；其次因为这个框架较新，使得他的社区没有那么强大，在文档方面其C库大多数没有文档。

### 4 PyTorch安装流程
1 安装Anaconda 3.5
Anaconda是一个用于科学计算的Python发行版，支持Linux、Mac和Window系统，提供了包管理与环境管理的功能，可以很方便地解决Python并存、切换，以及各种第三方包安装的问题。

1.1 下载：¶
可以直接从Anaconda官网下载，但因为Anaconda的服务器在国外，所以下载速度会很慢，这里推荐使用清华的镜像来下载。注意选择合适的版本。

1.2 安装及配置环境变量
下载之后，点击安装即可。

安装完成后，进行Anaconda的环境变量配置，打开控制面板->高级系统设置->环境变量->系统变量找到Path，点击编辑，加入三个文件夹的存储路径（注意三个路径之间需用分号隔开）。

至此，Anaconda 3.5 windows版就安装设置好了。打开程序找到Anaconda Navigator，启动后还可以看到：Jubyter，单击打开即可。

2 Win10+Anaconda环境下安装Pytorch
安装Pytorch，在命令提示符cmd中输出指令，进行在线安装

conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
