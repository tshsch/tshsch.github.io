---
layout: post
title:  "中文博客报错解决"
date:   2026-03-08 20:10:26 +0800
categories: jekyll update
---

### 写中文内容出现报错test

```text
Error: could not read file FILE-NAME: invalid byte sequence in UTF-8
```

### 报错原因

The default encoding used by Jekyll is UTF-8. Jekyll expects all files to be in this format and may produce errors if they are not. Since my computer uses Chinese Windows system, GBK is the default encoding for applications such as VSCode.

### 解决方法

将文件的编码从GBK改为UTF-8.

方法1: 将VSCode界面右下角编码方式从GBK改为UTF-8.

方法2: 用记事本打开文件，在文件->另存为中编码选择UTF-8.

### UTF-8与GBK的区别

| | UTF-8 | GBK(国家标准扩展) |
| --- | ----- | ----------- |
| 范围 | 所有字符 | 中文字符 |
| 英文 | 1 Byte | 1 Byte |
| 中文 | 3 Bytes | 2 Bytes |
