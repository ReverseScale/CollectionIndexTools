# CollectionIndexTools

![](https://img.shields.io/badge/platform-iOS-red.svg) ![](https://img.shields.io/badge/language-Swift-orange.svg) ![](https://img.shields.io/badge/download-3.81MB-brightgreen.svg
) ![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg) 

相信你一定有想过给 Collection View 加一个类似 Table View 的索引条的想法，今天我就给你一个。

| 名称 |1.列表页 |2.展示页 |
| ------------- | ------------- | ------------- |
| 截图 | ![](http://og1yl0w9z.bkt.clouddn.com/17-7-13/49229440.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/17-7-13/87845745.jpg) |
| 描述 | 通过 storyboard 搭建基本框架 | 偷懒的展示页面 |

## Advantage 框架的优势
* 1.文件少，代码简洁
* 2.不依赖任何其他第三方库
* 3.使用代理方式传导，结构优良
* 4.纯原生系统支持，效率高
* 5.动态布局方式，自动适配

## Requirements 要求
* iOS 7+
* Xcode 8+

## Usage 使用方法
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

使用简单、效率高效、进程安全~~~如果你有更好的建议,希望不吝赐教!


## License 许可证
CollectionIndexTools 使用 MIT 许可证，详情见 LICENSE 文件。


## Contact 联系方式:
* WeChat : WhatsXie
* Email : ReverseScale@iCloud.com
* Blog : https://reversescale.github.io
