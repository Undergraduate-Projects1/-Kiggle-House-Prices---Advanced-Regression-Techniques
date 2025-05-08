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

### 配置Jupyter环境
- 首先大家需要安装Anaconda/miniconda，主要是为给我们的Jupyter创建一个虚拟环境.
- 安装完成后，打开命令提示符：Win + R，输入cmd，按下回车键打开命令提示符窗口，在命令栏输入：

```
conda --version
```
![1](https://i-blog.csdnimg.cn/direct/3d9d82458d73421894dcc4429f4aa38e.png)

显示上述结果说明安装成功。

- 接下来创建一个新的虚拟环境：
```
conda create --name czm2
```
- 查看环境是否创建成功：conda env list 如果环境列表中出现刚刚创建的环境名称，表明安装成功。
- 接下来**在该环境下**继续安装其他深度学习和机器学习常用的python库：其中torch和rensorflow需要具体确定是否安装GPU版本，不要贸然安装

```
pip install numpy pandas matplotlib seaborn scikit-learn xgboost lightgbm catboost  opencv-python  tqdm

pip install tensorflow keras torch torchvision torchaudio
```

### 安装Jupyter Notebook

- 直接使用pip下载:
```
pip install jupyter notebook
```
- 使用命令：
```
conda activate czm2
```
激活刚才创建的环境，激活之后命令行左边会出现环境名称

![2](https://i-blog.csdnimg.cn/direct/6bef789d58c6493ab1af10d55fa30e06.png)

-  下载python所需的内核:
```
pip install ipykernel
```
`ipykernel` 包允许 Jupyter Notebook 或 JupyterLab 识别和使用 Conda 环境作为内核

- 在jupyter中注册内核
```
    python -m ipykernel install --user --name=czm2 --display-name="ipykernel_1"
```
这里：
   -  `--user` 表示安装是针对当前用户的；
   -  `--name=myenv` 指定了内核的名称，应与你的 Conda 环境名称一致；
   -  `--display-name="My Environment"` 设置了在 Jupyter Notebook 或 JupyterLab 的下拉菜单中显示的内核名称。
   -  大家只需要把myenv改为刚刚创建的环境名称(czm2)，和ipykernel_name改为自己喜欢的内核名称(ipykernel_1)就好了。后续我们配置内核的时候就会使用我们刚刚创建的内核名称。

### 启动jupyter notebook
- 在终端中激活虚拟环境，cd到工作目录下，然后输入指令：
```
jupyter notebook
```
- 配置成功会出现下面的情形：

![3](https://i-blog.csdnimg.cn/direct/248624adf2774e1a9a2087b00fd7befa.png)

启动它们通常会打开一个本地服务器，并在你的默认网络浏览器中自动打开一个特定的 URL 地址。这个 URL 通常是形如 http://localhost:8888/ 或者 http://127.0.0.1:8888/ 的形式，后面跟着具体的路径。8888表示端口号，如果端口被占用就会出现8889等等。如果没有自动打开浏览器，我们可以复制上述黄色对应的浏览器网址，使用我们本地浏览器进行打开。

- 在浏览器中打开成功后，会出现以下页面：
![4](https://i-blog.csdnimg.cn/direct/8a4d404fb1234bd79f1afc463c463bbd.png)

- 将注册好的内核配置进去: 选择内核，这里用我们刚刚注册的内核
![5](https://i-blog.csdnimg.cn/direct/950a93ae093d42da8f42d6d50fce3686.png)


- 更改文件名称：
![6](https://i-blog.csdnimg.cn/direct/2e70c02630aa4669b28f168998f1f1e6.png)

下面就可以编写代码了,在Jupyter中进行的文件修改工作会同步到本地机上。

### 注意事项
- 大家还在启用jupyter后，不要着急关闭命令提示符(终端)，如果关掉的话就会显示如下：
![7](https://i-blog.csdnimg.cn/direct/9758a7d9adae4c1db3dbafe87b6863dd.png)

- 同其他编译环境操作一样，导入所需的库，导入的前提是我们所使用的虚拟环境中，必须已经下载安装好了该库。
- jupyter中的常用快捷键：
![8](https://i-blog.csdnimg.cn/direct/e270e1cd09b04c5da604f9343d73fcdf.png)


## 遇到的问题
- 报错：NotFoundError: D:\minicode\envs\czm2\lib\site-packages\tensorflow_decision_forests\tensorflow\ops\inference\inference.so not found
- 解决：TF-DF 并没有为 Windows 构建或发布 inference 相关的动态库，因此无法正常运行模型推理功能。
可以使用 Google Colab，它的环境是 Linux，且支持 TF-DF。

## Google Colab使用指南: 项目创建和环境配置
### 打开 Colab
- 👉 访问：https://colab.research.google.com
- 选择 File (文件) → New notebook（新建笔记本）。
- Colab 会为你创建一个 .ipynb 文件（Jupyter notebook 格式）。

### 安装依赖包
- Colab 自带 TensorFlow，但你需要手动安装 TensorFlow Decision Forests。在第一个代码单元格中输入以下内容并运行：
```python
!pip install -U tensorflow_decision_forests
```

### 导入库并验证安装
新建一个代码块，输入并运行：
```python
import tensorflow_decision_forests as tfdf
import pandas as pd
import numpy as np

print("TF-DF version:", tfdf.__version__)
```

输出显示版本号即为安装成功。

### 💾 保存或下载你的项目
- 点击 File → Save a copy in Drive：保存到你的 Google Drive。
- 点击 File → Download .ipynb：下载为本地 Jupyter 文件。

### 💡 Google Colab 小技巧
#### 📌 常用操作对照表

| 操作名称               | 方法说明                                                           |
|------------------------|--------------------------------------------------------------------|
| 添加代码块             | 点击页面上方的 `+ Code` 按钮                                      |
| 添加文本说明块         | 点击页面上方的 `+ Text` 按钮                                      |
| 查看/管理工作目录文件  | 点击左侧边栏中的「📁 Files」图标                                   |
| 上传本地文件           | 在「Files」面板中点击「Upload」按钮，选择文件进行上传              |
| 下载文件到本地         | 右击文件 → `Download`                                             |
| 将文件保存到 Google Drive | 点击左上角 `File → Save a copy in Drive`                        |
| 以 `.ipynb` 下载 Notebook | 点击左上角 `File → Download → Download .ipynb`                |
| 切换运行环境类型       | 点击 `Runtime → Change runtime type`，选择 `GPU` 或 `TPU`        |
| 重新启动运行环境       | 点击 `Runtime → Restart runtime`                                  |
| 安装 Python 第三方包   | 使用 `!pip install 包名`（如：`!pip install tensorflow_decision_forests`） |
| 运行 shell 命令        | 在代码块中使用 `!命令`（如：`!ls`, `!wget`, `!unzip`）             |
| 查看当前环境信息       | 使用命令 `!nvidia-smi`, `!pip list`, `!cat /etc/os-release` 等     |

#### ✅ 推荐设置

- 使用 `GPU` 训练模型：`Runtime → Change runtime type → Hardware accelerator → GPU`
- 笔记本自动保存：所有变更会自动同步到 Google Drive
- 推荐浏览器：Chrome、Firefox（支持最好）

#### 📂 文件管理提示

- 上传的文件默认存放在 `/content` 目录下
- 上传后若未保存，Colab 重启后文件会消失（建议及时保存至 Google Drive）

---

更多帮助可访问：[Colab 官方帮助文档](https://research.google.com/colaboratory/faq.html)
