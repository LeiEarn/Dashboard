---
layout: default
title: 代码规范
---

# 代码规范
{:.no_toc}

* 目录
{:toc}

| 版本 |   日期    | 描述 |  作者   |
| :--: | :-------: | :--: | :-----: |
| v1.1 | 2019-6-24 | 小程序端代码规范 | littleGun |

## 小程序端

- JavaScript

    * 根据[ES 2016+](http://kangax.github.io/compat-table/es2016plus/)
    * 使用ESLint进行代码风格检查
        * 基于[JavaScript Standard Style](https://github.com/standard/standard/blob/master/RULES.md#javascript-standard-style)
        * 永远不省略分号
    * 可以使用Async/Await的地方就不使用Promise
- CSS

    * 使用[less](http://lesscss.org/)
    * 长度使用rpx
        *  see [this](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxss.html#尺寸单位)
- Python
    - 使用PyCharm进行代码编写，自动进行PEP 8规范检查
    - 参考[Google开源项目风格](https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_style_rules/)：
        - 尽量不使用反斜杠进行连接
        - 字符串考虑使用%和+号
        - ...

