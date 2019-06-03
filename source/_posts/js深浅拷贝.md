---
title: js深浅拷贝
date: 2019-06-03 16:07:53
tags:
	- js  
---

## 深浅拷贝（克隆）

1、 回顾基本类型和引用类型赋值过程
    
  - 基本类型：按值传递
  - 引用类型：按址传递

2、  内存中的栈和堆

- 栈：系统自动分配内存空间，且自动释放，里面存放的是基本类型的值和引用类型的地址
- 堆：动态分配的内存，大小不定，也不会自动释放。里面存放引用类型的值。


3、深浅拷贝

- 浅拷贝：把一个对象赋值给另一个新对象，对新对象的值进行修改会影响到原来的对象，我们称之为浅拷贝。其本质是新旧对象还是共享同一块内存。
- 深拷贝：把一个对象赋值给另一个新对象，对此新对象的值进行修改不会影响到原来的对象。我们称之为深拷贝。深拷贝会另外创造出一个一模一样的对象，新对象跟原对象不共享内存，修改新对象不会改到原对象


4、借助第三方库实现深浅拷贝
- jquery库：[$.extend](http://jquery.cuishifeng.cn/jQuery.extend.html)
- lodash函数库：[_.cloneDeep()](https://lodash.com/docs/4.17.11#cloneDeep)


```javascript
var obj1 = {
        a: 1,
        b: {
            f: {
                g: 1
            }
        },
        c: [1, 2, 3]
    };
    // var obj2 = $.extend(true, {}, obj1); //jquery库
    var obj2 = _.cloneDeep(obj1); // lodash库
    console.log(obj1.b.f === obj2.b.f); // false
    obj2.c.push(4);
    obj2.c.push(5);
    console.log(obj1);
    console.log(obj2);
```

## underScore函数库的基本使用

[https://underscorejs.org/](https://underscorejs.org/) 


## [重中之重]JS运行机制-事件循环


- 进程（孙悟空）：正在进行的程序。操作系统需要给其分配资源（cpu、内存）
- 线程（猴毛）：是操作系统中执行任务的最小单位。

一个进程最少要做一任务，所以一个进程最少有一个线程。

> 一个进程中只有一个线程，一般把此线程是称之为主线程。   

操作系统是多进程的。

360安全卫士、浏览器是多线程的应用程序。


谁去执行线程？
cpu去执行他们，会在多个线程之间，做着快速的切换。

