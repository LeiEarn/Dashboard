---
layout: default
title: 代码规范
---

# 代码规范
{:.no_toc}

| 版本 |   日期    | 描述 |  作者   |
| :--: | :-------: | :--: | :-----: |
| v1.1 | 2019-6-24 | 小程序端代码规范 | littleGun |

## 小程序端

1. JavaScript

    * 根据[ES 2016+](http://kangax.github.io/compat-table/es2016plus/)
    * 使用ESLint进行代码风格检查
        * 基于[JavaScript Standard Style](https://github.com/standard/standard/blob/master/RULES.md#javascript-standard-style)
    * 可以使用Async/Await的地方就不使用Promise

2. CSS

    * 使用[less](http://lesscss.org/)
    * 长度使用rpx
        *  see [this](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html#尺寸单位)