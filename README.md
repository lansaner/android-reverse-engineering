# Android 逆向工程

My notes for android reverse engineering learning.

## 目录

* [前言](#前言)
* [工具准备](#工具准备)
	* [我使用的工具](#我使用的工具)
	* [其它工具](#其它工具)
* [基础知识准备](#基础知识准备)
	* [Smali](#smali)

## 前言

一直想写点关于 Android 逆向工程的东西，却迟迟不能开始。先挖个坑放在这里吧，有现成的坑才更容易产生填的欲望。

我要写的不是一份全面且详细的工具介绍，也不是一份完整的技术原理说明，重点在记录与分享我在实践过程中的经验。如果我提到某一个工具，将只介绍我所使用到的功能与命令，想了解工具完整的功能与使用方法可以参考工具的官网。

## 工具准备

### 我使用的工具

本节罗列的是我使用到的工具集。

* [7-zip][0]

    好用的压缩/解压缩软件，APK 文件基于 ZIP 文件格式，有时候我们需要将其直接解压来分析里面的内容。

* [apktool][1]

    Android 逆向工程的主要工具之一，用于：
    1. 将 APK 文件里的可执行文件和资源解包成我们能看懂的格式。
    2. 将解包后的文件重新打包成 APK。
    3. 将 APK 里的 dex 文件反编译成调试版的 Smali 文件。

    *注：根据 apktool 官网的声明，反编译成调试版 Smali 文件的功能将在 2.0.3 版被废弃，到 2.1 版完全移除，因为有了 IdeaSmali。*

* [dex2jar][2]

    用于将 dex 文件转化成 jar 文件。

* [jd-gui][3]

    用于直接打开 jar 文件阅读 Java 代码，支持搜索，还有一定程度上的类间跳转。

* [Android Studio][4]

    用于动态调试。

* [IDA Pro][5]

    最强大的静态逆向分析工具，没有之一。

* [Smali 语法高亮与 Tag 支持][6]

    Vim 里的 Smali 语法支持。

### 其它工具

* [smalidea][7]

    用于支持 Android Studio 和 IntelliJ IDEA 高亮显示和动态调试 Smali 文件的插件。

## 基础知识准备

### Smali

我对 Smali 的认识是它是 Android 使用的 Java 虚拟机能理解的一种字节码。

这部分我是看《Android软件安全与逆向分析》一书的「第 3 章 进入 Android Dalvik 虚拟机」入门。

以下链接可作为手册备查：

* [Dalvik opcodes][8]
* [Dalvik bytecode][9]

[0]: http://www.7-zip.org/
[1]: https://github.com/iBotPeaches/Apktool
[2]: https://github.com/pxb1988/dex2jar
[3]: https://github.com/java-decompiler/jd-gui
[4]: https://developer.android.com/sdk/index.html
[5]: https://www.hex-rays.com/products/ida/index.shtml
[6]: http://mazhuang.org/2015/06/23/vim-taglist-smali/
[7]: https://github.com/JesusFreke/smali/wiki/smalidea
[8]: http://pallergabor.uw.hu/androidblog/dalvik_opcodes.html
[9]: https://source.android.com/devices/tech/dalvik/dalvik-bytecode.html
