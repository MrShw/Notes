# 一、Javascript 概述

## 1. JS 简介

Javascript，简称 JS， 是一种客户端脚本语言，主要用来向 HTML 网页添加各种动态效果。

```
html 骨骼
css  衣服
js   动作
```

Javascript 是一种可以在客户端运行的脚本语言，不需要进行编译

Javascript 可以做什么？

- 表单动态校验（密码强度检测） 也是 JS 产生最初的目的
- 网页特效
- 服务端开发（Node.js）
- 命令行工具（Node.js）
- 桌面程序 (Electron)
- App (Cordova)
- 控制硬件-物联网 (Ruff)
- 游戏开发 (cocos2d-js)



## 2. JS 组成

- ECMAscript - Javascript 语法
- DOM - 页面文档对象模型
- BOM - 浏览器对象模型



ECMAscript

ECMAScript 是 ECMA 国际进行标准化的一门编程语言，往往被称为 Javascript 或 JScript，实际上后两者是 ECMAScript 的是实现和扩展



DOM - 页面文档对象模型

文档对象模型（Document Object Model）通过 DOM 提供接口可以对页面上的各种元素进行操作（大小、位置、颜色）



BOM - 浏览器对象模型

浏览器对象模型（Browser Object Model），可以对浏览器窗口进行互动的对象结构，通过BOM可以操作浏览器窗口，比如弹窗、控制浏览器跳转、获取分辨率等。


# 二、JS 基本使用

## 1. 主要函数

- console.log()
- alter()
- prompt()

console.log() - 主要在控制台显示信息
alter() - 窗口提示信息，不能输入，只能点确定
prompt() - 窗口提示信息，可以输入，例如输入密码

可以用propmt接受信息后，利用console传到后台，在利用alter反馈

## 2. 声明变量

declaration 用 let 和 const

let assign 几次都没问题，但是const只能一次。两者都不能redeclaration

## 3. 字符串

字符串主要操作有什么？

- 长度
- 字符串的属性
- 检索字符
- 切片
- indexof
- toLowerCase
- toUpperCase
- 分割

切片时，[开始位置，结束位置)，不包括结束位置字符。


## 4. 数组

```
index
length
push()
pop()
shift()
unshift
```
