# 工程配置
1. 使用 clangd 做代码提示和分析
   如 .vscode/settings.json 所示
2. 使用 bear 生成 compile_commands.json喂给clangd
   ```shell
   ./configure
   bear -- make
   bear -- make install
   ```
3. 使用vscode launch.json 来debug
   如 .vscode/launch.json 所示

# 源码学习资源
https://www.zhihu.com/question/20108410
https://ffmpeg.xianwaizhiyin.net/
https://github.com/feixiao/learn-ffmpeg
https://cloud.tencent.com/developer/article/1842251
https://blog.csdn.net/leixiaohua1020/article/details/44220151
https://lazybing.github.io/blog/categories/ffmpegyuan-ma-fen-xi/
https://blog.csdn.net/leixiaohua1020/article/details/15811977
https://juejin.cn/post/6871450709376630792

# 笔记
## 工程配置中的问题
* #include <SDL.h>找不到

报错信息 `#include <SDL.h> 找不到` 提示的是编译器在标准库搜索路径中找不到 `SDL.h` 文件，通常这意味着 SDL (Simple DirectMedia Layer) 库还未在你的系统中安装，或者安装的位置不在编译器的搜索路径中。

以下是一些解决方法：

**1. 安装 SDL**

如果你还没有安装 SDL，可以根据你的操作系统安装。对于 Ubuntu，可以使用以下命令：

```bash
sudo apt-get install libsdl2-dev
```

对于 macOS，可以使用 Homebrew：

```bash
brew install sdl2
```

对于 Windows，可以访问 SDL 的[下载页面](https://www.libsdl.org/download-2.0.php)，下载开发库，然后将它们添加到你的项目中。

**2. 检查 SDL 安装路径**

如果你已经安装了 SDL，但编译器仍不能找到 `SDL.h`，那么可能是 SDL 的头文件没有安装在编译器的默认搜索路径中。在这种情况下，你需要找出 SDL.h 的位置，然后将该路径添加到编译器的搜索路径中。

一般来说，可以使用 `-I` （大写的i）参数给 g++ 或 clang 等编译器指定头文件搜索的路径。例如：

```bash
g++ -I/path/to/SDL2 yourfile.cpp
```

在 CMake 项目中，你可以使用 `find_package(SDL2 REQUIRED)`，然后使用 `${SDL2_INCLUDE_DIRS}` （具体变量名可能根据你的系统和 SDL2 版本有所不同）获取头文件的路径。然后使用 `include_directories(${SDL2_INCLUDE_DIRS})` 添加头文件路径。

如上述建议无法解决你的问题，请给出更详细的环境和设置信息，我们可以根据这些信息提供更精准的解决方案。

* 
