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

# 笔记
