# For windows
## Install Anaconda and Dependencies
1. 安装Anaconda，记得两个选项都要勾选，第一个选项的功能是将安装路径加入到环境变量.  
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
NOTE:不需要逐个安装，已经安装了一部分包的也可以运行一遍以上命令，不影响。

## How To Use it
在确认一切都安装完毕并能正常运行之后，
1. 首先在source文件夹下新建一个文件夹，该文件夹对应我们将要进行的项目。将raw文件夹（source/cooperation文件夹下）复制到项目文件夹内。新建一个文件夹，命名tagged，将导出的数据复制到该文件夹下。至此，数据准备工作完毕。
2. 直接进行进行model训练（这里没有必要进行前处理，模型在没有找到数据的时候会自动加载数据并进行处理。）
在命令行输入python，进入Python shell（光标最左侧会有>>>）
```
>>> from vector import Model
>>> m = Model()
>>> m.set_std_words(['word1', 'word2', 'word3'])
>>> m.set_storage_dir('first', 'cooperation')
>>> 
```
FAQ:
1. 如何确认电脑能顺利连接到mysql数据库？
> 运行前大家先确认下电脑是否可以连接到数据库   
> 在命令行运行
> `ping 172.16.160.168`   
> 如果结果显示类似于：`64 bytes from 172.16.160.168: icmp_seq=0 ttl=64 time=0.618 ms`
> 则表示可以连接到数据库
2. 程序运行一次大概要多久？
> 运行过程中出现程序无响应且没有报错的情况时，查看一下网络流量下行速度，如果大于1MB/s，表示程序正在从服务器取数据，安心等待一会儿（一般在十分钟以内，建议电脑通过有线联网，速度可以达到10MB/s，无线的话可能在1MB/s左右）


