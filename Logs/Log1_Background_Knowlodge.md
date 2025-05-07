# Log1 Background Knowlodge
## Jupyter Notebook的安装与使用
[参考1 Jupyter notebook--配置与使用](https://blog.csdn.net/2301_80637569/article/details/142071630?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522f72942a7340ed9ebe74b2cf1630ab942%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=f72942a7340ed9ebe74b2cf1630ab942&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-2-142071630-null-null.142^v102^pc_search_result_base4&utm_term=jupyter%20notebook&spm=1018.2226.3001.4187)

### 初步理解Jupyter 
- Jupyter Notebook可以理解为一个类似于pycharm的编辑器，jupyter可以更好的帮助我们理解代码，
对于大型的数据处理计算，jupyter可以实时呈现结果，让我们快速知道哪里出现问题，理解代码中间过程。
- Jupyter支持多个语言，常见的编程语言Jupyter中都可以实现，对于**不同的编译环境，需要给Jupyter配置一个不同的内核（kernels）**，
所谓内核，大家可以理解为给Jupyter配置一个处理代码信息的大脑，不同的内核可以理解不同的代码。本文主要带着带着大家配置python的编译环境。

  - Python - 默认支持，通过 ipykernel 内核。
  - R - 通过 IRKernel 或 Repr 内核。
  - Julia - 通过 IJulia 内核。
  - Scala - 通过 Tino 或 ScalaKernel 内核。
  - Swift - 通过 SwiftKernel。
  - JavaScript - 通过 node-jupyter。
  - Ruby - 通过 ruby-kernel。
  - Go - 通过 go-ipython 或 gokernel。
  - C/C++ - 通过 cppkernel 或 litestella。
  - SQL - 通过 sqlkernel。

### 安装配置Jupyter环境
- 首先大家需要安装Anaconda/miniconda，主要是为给我们的Jupyter创建一个虚拟环境.
- 安装完成后，打开命令提示符：Win + R，输入cmd，按下回车键打开命令提示符窗口，在命令栏输入：

```
conda --version
```
![1](https://i-blog.csdnimg.cn/direct/3d9d82458d73421894dcc4429f4aa38e.png)
显示上述结果说明安装成功。

- 

