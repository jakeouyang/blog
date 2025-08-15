---
title: "BCML塞尔达传说：荒野之息Mod管理器教程"
description: "BCML塞尔达传说：荒野之息Mod管理器教程"
pubDate: "2025-08-13"
---

### 环境安装
下面是bcml [github][1]的要求说明
> Windows 10+ (7-8 might work but are not officially supported) or basically any modern Linux distribution windows10以上系统就没问题
A legal, unpacked game dump of The Legend of Zelda: Breath of the Wild for Switch (version 1.6.0) or Wii U (version 1.5.0) 游戏文件
The latest x64 Visual C++ redistributable windows10以上系统自带，没有的自己安装，但我推荐，b站可能有人遇到，[下载][2]
Cemu (optional) 选择安装

其实最重要的是python要求：

> Python 3.7 - 3.10 (64 bit version)
很多人遇到python环境问题，导致bcml无法运行或者报错，大概率是出在python版本过低或者过高，这里我推荐 3.9版本
安装python有2个途径：

 1. windows商店直接安装python，版本号在bcml要求的版本范围内即可（在命令提示符里面输入:python 会自己跳出商店），安装自己会在环境变量创建python，这个版本有很多网友反馈能少遇到很多问题，也是我推荐的，bcml目前已经不更新了，也存在很多bug。
 2. python官网手动安装，这是我喜欢的方式：（

下载 [python3.9.0][3]
![python01.png][4]
![python02.png][5]

[网盘下载][6]，文件夹WiiU里面都是cemu相关，按需下载，密码:cemu1234

3个注意事项

 1. 不要手动选择安装路径
 2. 勾选加入环境变量
 3. 关闭路径长度限制

验证是否安装成功
打开windows的命令提示符，输入：

    python --version
    pip --version

输出版本号，说明安装成功了,同样采用windows商城安装python的也一样验证是否安装成功
![python03.png][7]

### BCML安装
执行安装命令：

    pip install bcml

但往往你安装不了，提示找不到包，主要是网络环境不问题导致，那么我们使用国内源即可

    pip install bcml -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host pypi.tuna.tsinghua.edu.cn

![python04.png][8]

安装成功之后，在命令提示符里面输入：bcml

![python05.png][9]

提示很明显了，前面的依赖没安装，那么下载安装下吧 [vc_redist.x64.exe][10]

再次运行：bcml
![bcml.png][11]
出现bcml界面了，恭喜你，安装bcml完成

### BCML配置


  [1]: https://github.com/NiceneNerd/BCML
  [2]: https://aka.ms/vs/16/release/vc_redist.x64.exe
  [3]: https://www.python.org/ftp/python/3.9.0/python-3.9.0-amd64.exe
  [4]: /img/3344116804.png
  [5]: /img/3854981726.png
  [6]: http://caicaiying.ysepan.com/
  [7]: /img/2181738746.png
  [8]: /img/1857390089.png
  [9]: /img/3867571952.png
  [10]: https://aka.ms/vs/16/release/vc_redist.x64.exe
  [11]: /img/3031515272.png