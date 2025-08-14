---
title: "CEMU模拟器入门教程"
description: "CEMU模拟器入门教程"
pubDate: "2025-08-14"
---

<!-- toc -->

### CEMU介绍
cemu模拟器只能模拟wiiu游戏，理论上所有wiiu游戏都可以模拟运行，同时官方给了一个[兼容列表][1]，这很重要，检查自己的游戏是否兼容比你到处问人来的更加有效，借助pc强大的配置（当然你得有钱），让wiiu游戏支持4k，60fps+不在话下，比如热门游戏塞尔达传说：荒野之息就已经很完美的运行在4k，60fps，hdr模式下，游戏体验直线上升。

本篇cemu只关注windows平台，[官网][2]，linux，mac用户就应该好好学习，工作。

使用cemu建议3点：

 1. 时刻保持cemu最新，当然会牺牲稳定性，但相信我，更新到最新版本才能保证最好性价比，你那点稳定性人家会帮你解决的
 2. 时刻查看cemu官网wiki，那里有最好的文档和说明，可以解决你很多问题
 3. 保持好奇心，问问题之前多动动脑筋，这样你玩一款模拟器也能体会它的原理，通过玩游戏可能真的有学习到知识

### 系统要求
**Windows 7 (x64) or above**
最好是windows10以上，当然11也可以，感觉没太大差别
**OpenGL 4.5 or Vulkan 1.2**
pc硬件能跟得上那么推荐vulkan，总之更厉害
**RAM: 4 GB minimum, 8 GB or more recommended**
内存最小4g，玩游戏还是需要下点本钱的，所以推荐8g以上
**Microsoft Visual C++ 2017 X64 Redistributable: vc_redist.x64.exe**
这个要注意了，低版本系统要运行cemu，应该安装它的必要依赖[vc_redist.x64.exe][3]
windows10以上系统已包含，但也推荐安装。

### 显卡兼容
**NVIDIA GPU：** 更新驱动到最新。
**AMD GPU：** 更新驱动到最新。由于性能不佳，避免在旧显卡上使用 OpenGL。
**Intel GPU：** 支持有限。建议使用 Vulkan。
如果显卡内存小于 2GB，建议使用 OpenGL。其他情况下，Vulkan 更佳。

### 手柄支持
目前已模拟 GamePad、Pro Controller 和 Classic Controller。Wiimotes 已部分模拟。支持键盘输入 + USB 控制器作为输入设备。GamePad 触控输入可通过鼠标左键控制。如果控制器支持陀螺仪功能，则可模拟陀螺仪功能；或者，也可以通过拖动鼠标右键进行控制。
个人测试支持：xbox one，ps5，switch pro等手柄
即使不支持也可以使用软件模拟手柄
自然键盘也是支持的，cemnu支持90%常见手柄，当然也支持模拟陀螺仪。

### 下载安装
**我当前cemu版本是：2.6**
途径：
 1. [官网下载][4]，当然你需要魔法，因为它在github，或者你靠运气多刷新有几率打开
 2. [网盘下载][5]，文件夹WiiU里面都是cemu相关，按需下载，密码:`cemu1234`

cemu为绿色软件，一个压缩包，解压出来
**cemu.exe** 主程序
**gameprofiles** 游戏profile文件，包含支持的所有wiiu，按照Title ID命名的配置信息
**resources** cemu依赖的多语言包和字体

好的软件就是这样，文件干净，目录简单
![cemu01.png][6]

### 配置
#### 初见
直接运行 **cemu.exe** 出现弹窗，有2个注意点：

 1. 选择游戏本体，补丁，dlc目录，意思就是选个目录存放游戏，建议目录放在cemu目录同级，当然可以是任何你能找到的地方，不过不要出现路径有**中文**的情况
 2. 安装图形包，因为在外网，大概率不是很好下载下来，图形包是所有cemu支持游戏的全部图形文件，不过不是很大，当然我也提供了，网盘wiiu目录下的graphicPacks包，解压丢到C:\Users\你的用户名\AppData\Roaming\Cemu内，这个包是干净的原始包，直接外网下载的，完美！丢好的目录应该是C:\Users\你的用户名\AppData\Roaming\Cemu\graphicPacks\downloadedGraphicPacks
![cemu02.png][7]

下一步会出现另外一个窗口
![cemu03.png][8]

 1. 手柄设置暂时不操作，后面会详细介绍配置
 2. 其他保持默认就行，截图我也标示出来含义了

同时会在C:\Users\你的用户名\AppData\Roaming\Cemu创建文件，当然你也可以通过cemu点击“文件”进去这个目录，只关注几个文件夹就好

 - controllerProfiles 配置手柄的配置文件存放处
 - dump cemu调试日记，你不用管
 - graphicPacks 图形包下载存放处，**如果你因为网络问题下载不了，那么请下载我的图形包丢在该目录下**
 - memorySearcher 内存查找目录，不用管
 - mlc01 很重要的目录，因为存放的是游戏存档，后面需要修改配置将该目录放在自定义目录，你的财产应该自己管保好
 - shaderCache 着色器缓存，有时候需要重新生成游戏缓存可以删除让游戏重新渲染着色器
 - settings.xml cemu配置文件，不用管

![cemu06.png][9]

#### 切换中文
Options -> General settings -> 选择中文!
cemu需要重新启动，你熟悉的语言来了！
![cemu04.png][10]

### 功能说明
#### 功能全貌
首先看个思维导图吧，这张图展现了cemu所有功能
![cemu.jpg][11]
下面将一些需要关注的功能做解释：

	工具
		内存搜索器
		档案管理器
		下载搜索器
		模拟 USB 设备
	CPU
		时钟速度
	选项
		全屏
		图形插件
		单独 GamePad 窗口
		通用设置
		输入设置
		当前账户
		主机语言
	文件
		载入
		安装档案，升级档或DLC
		打开 Cemu 文件夹 - 打开用户名下面的cemu创建文件C:\Users\你的用户名\AppData\Roaming\Cemu
		打开 MLC 文件夹 - 打开游戏存档目录
		退出
	NFC
		载入 NFC 文件
	调试
		别管它
	帮助
		升级

#### 通用设置

  [1]: http://compat.cemu.info/
  [2]: http://cemu.info/
  [3]: https://aka.ms/vs/16/release/vc_redist.x64.exe
  [4]: https://github.com/cemu-project/Cemu/releases
  [5]: http://caicaiying.ysepan.com/
  [6]: /img/4258147865.png
  [7]: /img/2329152915.png
  [8]: /img/232416089.png
  [9]: /img/3544918457.png
  [10]: /img/3114733970.png
  [11]: /img/1966315949.jpg