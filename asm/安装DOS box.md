# MAC OS 环境下DOS BOX汇编环境的搭建
[参考](https://www.cnblogs.com/skyen/p/9721471.html)

工具：
* DOSBox（点击下载DOSBox官网）

* debug、edit、link、masm等等

步骤: 

1. 安装DOSBOX
2. 然后进行挂载 
```shell
mount C ~/Desktop/……
```
3. 然后就可以使用


续：因为这样配置后，每次启动的时候都要重复输入相同的代码，比较繁琐，以下的操作可以帮助你避免重复操作。

下载完成DosBox之后，先运行一下DosBox，然后在Users/your name/Library/Preferences目录找到 DOSBox 0.74-2 Preferences文件，如果没有找到目录的话，可以按 cmd+shift+.来显示隐藏目录。

用文本编辑器打开文件，并找到[autoexec]，然后添加如下内容并保存：

```shell
MOUNT C ~/DOSBox
C:
```