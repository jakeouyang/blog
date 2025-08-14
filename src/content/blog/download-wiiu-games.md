---
title: "如何下载WiiU官网纯净游戏并转换Cemu支持的游戏包"
description: "如何下载WiiU官网纯净游戏并转换Cemu支持的游戏包"
pubDate: "2025-08-14"
heroImage: "/blog-placeholder-3.jpg"
---

### 所用工具
[FunKiiU][1]
[CDecrypt][2]
[WiiU Title Key DB][3]

### 下载游戏
FunKiiU是python脚本，兼容Python 2.7 - 3，[这篇文章][4]介绍了怎么安装python，那么你应该有python3.9

只需要执行下面命令就会在当前目录下创建install文件夹，这里面就是所有下载的游戏包

    python FunKiiU.py -title 0005000e101c9300 -key c607006fc382226a002659db5fa33e8d

开始下载
![key05.png][5]
title key 从这网站[WiiU Title Key DB][6]进去查找，按需找到替换想要的游戏title和key
![key03.png][7]
注意区分本体和补丁，dlc，都有着自己的title和key
![key01.png][8]
![key02.png][9]
![key04.png][10]
FunKiiU 更多使用方法请自己看文档，目前上面那个命令足够了，很多人会在执行命令后出现下载不了的问题，主要有2方面：

 1. 命令与title，key不对，仔细检查
 2. 网络不稳定，毕竟是外网官方cdn，可以换个时间重试，比如深夜，我自己测试直接下载没问题

下载之后会在install文件夹下面用title命名的文件夹，里面就是游戏本体，如下载补丁，dlc有title+update/dlc文件夹，很好区分。
![key06.png][11]
当然这下载下来的游戏还是加密的，需要用到解密才可使用。

### 解密游戏
解密非常简单，只需要将下载的游戏文件夹，拖动到CDecrypt.exe后等命令跑完，在游戏文件夹下面就会出现解密游戏包，目录是：
code
content
![key07.png][12]
这些文件夹需要放置cemu设置的游戏目录，cemu会自动识别，具体操作参考[这篇文章][13]


  [1]: https://github.com/llakssz/FunKiiU
  [2]: https://github.com/VitaSmith/cdecrypt
  [3]: https://www.wiiuemulator.com/Game-Key-Database.htm
  [4]: https://caicaiying.com/archives/BCML.html
  [5]: https://caicaiying.com/usr/uploads/2025/05/1308899700.png
  [6]: https://www.wiiuemulator.com/Game-Key-Database.htm
  [7]: https://caicaiying.com/usr/uploads/2025/05/1240419938.png
  [8]: https://caicaiying.com/usr/uploads/2025/05/3138530599.png
  [9]: https://caicaiying.com/usr/uploads/2025/05/13435778.png
  [10]: https://caicaiying.com/usr/uploads/2025/05/1936986271.png
  [11]: https://caicaiying.com/usr/uploads/2025/05/3304025844.png
  [12]: https://caicaiying.com/usr/uploads/2025/05/3674555083.png
  [13]: https://caicaiying.com/archives/The_Legend_of_Zelda_Breath_of_the_Wild_cemu_pc.html