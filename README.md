# CollectionIndexTools

![](https://img.shields.io/badge/platform-iOS-red.svg) ![](https://img.shields.io/badge/language-Swift-orange.svg) ![](https://img.shields.io/badge/download-3.81MB-brightgreen.svg
) ![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg) 

[EN](#Requirements) | [中文](#中文说明)

I believe you must have thought about adding an index like Table View to Collection View. I will give you one today.

## 🎨 Why test the UI?

| 1.List page | 2.Show page |
| ------------- | ------------- |
| ![kEirwT.png](https://s2.ax1x.com/2019/01/23/kEirwT.png) | ![kEisTU.png](https://s2.ax1x.com/2019/01/23/kEisTU.png) |
| Building a basic framework through storyboard | Lazy presentation page |

## 🤖 Requirements

* iOS 9.0+
* Xcode 9.0+
* Swift

## 🚀 Getting started

* 1.Less files, simple code
* 2.Does not rely on any other third party library
* 3.Propagation using proxy method, excellent structure
* 4.Pure native system support, high efficiency
* 5.Dynamic layout method, automatic adaptation


## 🛠 Configuration
### Drag the tool file into the project file
file：PackageTableView 
### Call method
#### set up
```Swift
    func setupCollectionIndex() {
        let views: [String: AnyObject] = [
            "topLayoutGuide": topLayoutGuide,
            "bottomLayoutGuide": bottomLayoutGuide,
            "collectionViewIndex": collectionViewIndex,
            ]
        
        view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "[collectionViewIndex]|", options: [], metrics: nil, views: views))
        view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "V:[topLayoutGuide][collectionViewIndex][bottomLayoutGuide]", options: [], metrics: nil, views: views))
    }
```
#### lazy
```Swift
    lazy var collectionViewIndex: CollectionViewIndex = {
        let collectionViewIndex = CollectionViewIndex()
        collectionViewIndex.indexTitles = ["肺", "大", "胃", "脾", "心", "小", "膀", "肾", "包", "三", "胆", "肝", "督", "任", "冲", "带", "维", "跷", "奇"]
        collectionViewIndex.addTarget(self, action: #selector(FakeCollectionViewController.selectedIndexDidChange(_:)), for: .valueChanged)
        collectionViewIndex.translatesAutoresizingMaskIntoConstraints = false
        return collectionViewIndex
    }()
```
#### call back
```Swift
    func selectedIndexDidChange(_ collectionViewIndex: CollectionViewIndex) {
        title = collectionViewIndex.indexTitles[collectionViewIndex.selectedIndex]
    }
```

## ⚖ License

```
MIT License

Copyright (c) 2017 ReverseScale

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 😬 Contributions

* WeChat : WhatsXie
* Email : ReverseScale@iCloud.com
* Blog : https://reversescale.github.io

---
# 中文说明


相信你一定有想过给 Collection View 加一个类似 Table View 的索引条的想法，今天我就给你一个。

## 🎨 测试 UI 什么样子？

| 1.列表页 |2.展示页 |
| ------------- | ------------- |
| ![](http://og1yl0w9z.bkt.clouddn.com/18-3-20/23970127.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/18-3-20/66191.jpg) |
| 通过 storyboard 搭建基本框架 | 偷懒的展示页面 |

## 🤖 要求

* iOS 9.0+
* Xcode 9.0+
* Swift

## 🚀 准备开始

* 1.文件少，代码简洁
* 2.不依赖任何其他第三方库
* 3.使用代理方式传导，结构优良
* 4.纯原生系统支持，效率高
* 5.动态布局方式，自动适配


## 🛠 配置
### 第一步 将工具文件拖入工程文件
文件夹：PackageTableView 
### 第二部 调用方法
#### 1.设置
```Swift
    func setupCollectionIndex() {
        let views: [String: AnyObject] = [
            "topLayoutGuide": topLayoutGuide,
            "bottomLayoutGuide": bottomLayoutGuide,
            "collectionViewIndex": collectionViewIndex,
            ]
        
        view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "[collectionViewIndex]|", options: [], metrics: nil, views: views))
        view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "V:[topLayoutGuide][collectionViewIndex][bottomLayoutGuide]", options: [], metrics: nil, views: views))
    }
```
#### 2.懒加载
```Swift
    lazy var collectionViewIndex: CollectionViewIndex = {
        let collectionViewIndex = CollectionViewIndex()
        collectionViewIndex.indexTitles = ["肺", "大", "胃", "脾", "心", "小", "膀", "肾", "包", "三", "胆", "肝", "督", "任", "冲", "带", "维", "跷", "奇"]
        collectionViewIndex.addTarget(self, action: #selector(FakeCollectionViewController.selectedIndexDidChange(_:)), for: .valueChanged)
        collectionViewIndex.translatesAutoresizingMaskIntoConstraints = false
        return collectionViewIndex
    }()
```
#### 3.回调
```Swift
    func selectedIndexDidChange(_ collectionViewIndex: CollectionViewIndex) {
        title = collectionViewIndex.indexTitles[collectionViewIndex.selectedIndex]
    }
```


## ⚖ 协议

```
MIT License

Copyright (c) 2017 ReverseScale

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 😬  联系

* 微信 : WhatsXie
* 邮件 : ReverseScale@iCloud.com
* 博客 : https://reversescale.github.io
