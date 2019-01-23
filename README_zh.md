相信你一定有想过给 Collection View 加一个类似 Table View 的索引条的想法，今天我就给你一个。

## 🎨 测试 UI 什么样子？

| 1.列表页 |2.展示页 |
| ------------- | ------------- |
| ![kEirwT.png](https://s2.ax1x.com/2019/01/23/kEirwT.png) | ![kEisTU.png](https://s2.ax1x.com/2019/01/23/kEisTU.png) |
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

## 😬  联系

* 微信 : WhatsXie
* 邮件 : ReverseScale@iCloud.com
* 博客 : https://reversescale.github.io
