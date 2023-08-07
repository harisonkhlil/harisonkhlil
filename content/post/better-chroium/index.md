---
image: image1.jpeg 
title: "Better Chroium"
date: 2023-08-07T19:39:49+08:00
toc: true
description: 最好的,最快的 Chroium Folk
comments: true
links:
    - title: Thorium
      description: The fastest browser on Earth
      website: https://thorium.rocks/
      image: thorium.svg
tags:
    - "Browser"
    - "Chrome"
    - "Chroium"
categories:
    - "tools"
    - "productivity"
series:
    - "Tool Recommendations"
---

## 介绍

{{< quote source="thorium offical website" url="https://thorium.rocks/">}}
**The fastest browser on Earth.**
{{< /quote >}}

## 使用体验

- 更快: [跑分](https://browserbench.org/Speedometer2.1/)超过**Chroium**, **Chrome**, **Safari** 达到了惊人的 325 分, 最直观的体验就是, 打开网页的速度更快了
- 更稳: 没有数据支撑, 但是凭借使用了 2 年的 **Chrome** 时不时就会导致卡机的体验来说, **Thorium** 几乎从未造成过卡顿
- 更高效: 在打开相同的网页的情况下, **Thorium** 更加省内存, 比如 **bilibili** 在相同的编码下 
- 更纯净: 相比与越来越臃肿的 **Edge**, **Chrome** 系的表现一直不错, 非常的纯净,简洁, 但是 **Chrome** 同样有牛皮癣, 关不掉的 `side panel`, 恶心的侧边栏搜索等, 本来可以在 `chrome://flags` 中关闭某些按扭, 但是不知道为什么就是关不掉, 现在 **Throium** 可以解决上面的一切问题.

## 值得打开的 chrome://flags

下面是一些针对 **Thorium** 的优化通过在搜索栏输入 `chrome://flags`, **en** 代表 `enable`, **ne** 代表 `never`

* Hide Side Panel Button: en, 关闭侧边栏
* Show/Hide the Avatar Button: ne, 去掉右上角头像, 保护隐私
* Show Autofill predictions: en, 自动填充预测
* Experimental QUIC protocol: en, 国内环境不适合打开
* GPU rasterization: en, 更好地显示
* Omnibox Expanded State Height: en, 新 UI
* Omnibox Expanded State Shap: en, 新 UI
* Parallel downloading: en, 多线程下载
* Back-forward cache: en, 后台缓存,更流畅的网页体验
* Chrome Labs: disable, 去掉 lab 图标
* Chrome Refresh 2023: en, 新 UI
* Chrome Refresh 2023 Mac Font Smoothing: en, 新 UI
* Search web in side panel: disable, 关闭侧边栏
* Enable download bubble: en, 下载图标, 下面同时要打开
* Enable download bubble V2: en
* Biometric authentication reauth before filling: en: 生物识别认证
* User notes side panel: en, 这个其实挺有用的

## 引用

- [15 Google Chrome Flags You Should Use](https://beebom.com/google-chrome-flags/)
- [Thorium rocks](https://thorium.rocks/)
