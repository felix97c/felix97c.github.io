+++
title = "GCC4.8.5不支持正则"
author = ["felix97ch"]
date = 2024-12-06
lastmod = 2024-12-06T17:29:57+08:00
tags = ["cpp", "gcc"]
categories = ["cpp"]
draft = false
+++

## 问题记录 {#问题记录}

GCC4.8.5 版本并未实现 regex 的功能，只实现了 regex 的接口，实际上对接口的调用会抛出 regex_error 异常。这里有几个问题：

-   什么版本的 GCC 完整支持了正则？

    GCC 4.9.4 的版本上 regex 已经基本支持了
-   GCC 的功能特性说明是在哪个文档上看？

    以 GCC4.8.5 的版本为例，其地址是：<https://gcc.gnu.org/onlinedocs/gcc-4.8.5/libstdc++/manual/manual/status.html>，可以在这上面看到其实不止是 regex 不支持，很多边边角角的地方都有缺失
-   不换 GCC 的话哪些库能替代使用？
    -   Boost.regex，这个库支持 standalone 模式，不需要引入整个 boost 依赖，而且接口基本和 STL 一致，最推荐这个，文档在这里：<https://www.boost.org/doc/libs/1_85_0/libs/regex/doc/html/index.html>
    -   PCRE2，这个是 C 语言的 正则三方库，个人没用过，但是很多的开源项目上都用了，想来差不到哪去，文档在这里：<https://www.pcre.org/current/doc/html/>
