# CollectionIndexTools

![](https://www.travis-ci.org/ReverseScale/CollectionIndexTools.svg?branch=master)
![](https://img.shields.io/badge/platform-iOS-red.svg) 
![](https://img.shields.io/badge/language-Swift-orange.svg) 
![](https://img.shields.io/badge/download-3.81MB-brightgreen.svg) 
![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg) 

[EN](https://github.com/ReverseScale/CollectionIndexTools) | [中文](https://github.com/ReverseScale/CollectionIndexTools/blob/master/README_zh.md)

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

## 😬 Contributions

* WeChat : WhatsXie
* Email : ReverseScale@iCloud.com
* Blog : https://reversescale.github.io

