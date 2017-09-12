# For windows
## Install Anaconda and Dependencies
1. 安装Anaconda，记得两个选项都要勾选，第一个选项的功能是将安装路径加入到环境变量
Note：如果没有勾选，可以手动加入环境变量（如若不知道如何添加环境变量，百度一下吧）
需要添加的变量：(C:\ProgramData\Anaconda3 将该路径替换成你本机上Anaconda的路径)
```
C:\ProgramData\Anaconda3
C:\ProgramData\Anaconda3\Library\mingw-w64\bin
C:\ProgramData\Anaconda3\Library\usr\bin
C:\ProgramData\Anaconda3\Library\bin
C:\ProgramData\Anaconda3\Scripts
```
2. 安装依赖（包）
首先，cd到提供的vector文件夹（假设该文件夹在D盘下）
```
// 以下命令都在cmd命令行执行
cd /d d:\vector
pip install -r requirements.txt
```

## How To Use it
在确认一切都安装完毕并能正常运行之后，
1. 首先在source文件夹下新建一个文件夹，该文件夹对应我们将要进行的项目。将raw文件夹（source/cooperation文件夹下）复制到项目文件夹内。新建一个文件夹，命名tagged，将导出的数据复制到该文件夹下。至此，数据准备工作完毕。
2. 直接进行进行model训练（这里没有必要进行前处理，模型在没有找到数据的时候会自动加载数据并进行处理。  
在命令行输入python，进入Python shell（光标最左侧会有>>>）
```
>>> from vector import Model
>>> m = Model()
>>> m.set_std_words(['word1', 'word2', 'word3'])
>>> m.set_storage_dir('first', 'cooperation')
>>> 
```
