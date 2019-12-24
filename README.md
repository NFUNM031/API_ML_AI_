# 寻书APP
| 发布日期 | 2019年12月11日 | 
| ------ | ------ | 
| 产品名称 | 寻书APP | 
| 文件现状 | 正在更新 | 
| 文件的主人 | 黄晓宜 | 
| 领头的设计师 | 黄晓宜 |
| 领头的开发者 | 黄晓宜 |
| 迭代版本 | 2.0 |

## 一、价值主张设计
### 1.加值宣言
调用百度通用文字识别API实现拍照/截图识别功能，实现拍照文字识别、相册图片文字识别和截图文字识别，方便用户进行文本的提取或录入，有效提升产品易用性和用户使用体验
### 2.核心价值宣言
让社会的闲置书籍资源能够被回收利用
### 3.用户痛点宣言
对于旧版珍藏版书或者条形码损坏的书籍无法上传平台
### 4.AI概率性考量：
通用文字识别API：针对图片模糊、倾斜、翻转等情况进行了优化，鲁棒性强，识别速度快，且支持2W+大字库，总体识别准确率高达99%。
### 5.需求列表
| 需求列表 | API加值 | 重要程度 |
| ------ | ------ | ------ |
| 卖家可以一键上传书籍相关信息| 通用文字识别API | 最重要

## 二、原型
### 1.[原型](https://gitee.com/NFUNM031/book_search_pictures/blob/master/%E5%8E%9F%E5%9E%8B1.png "原型")
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/%E5%8E%9F%E5%9E%8B1.png)
### 2.口头操作说明
打开软件进入首页后可以看到首页下方有“发布”按钮，点击“发布”按钮后弹出窗口可选择“扫条形码卖书“或者”扫图卖书“，对于拥有可用条形码的书籍可以直接扫条形码提取信息（准确率较高）；而对于无条形码可用书籍杂志周边等产品可以选择扫图卖书通过文字识别提取信息（准确率相对较低）。本次主要介绍“扫图卖书”功能，用户点击”扫图卖书“后进入手机本地相册页面选取书籍照片，也可以点击“拍照”功能进行现场拍摄。选中图片后app自动扫描图片内容并直接进入“发布”页面，此时页面里已经自动提取生成了书籍的相关信息，用户确定价格后可以直接发布，也可以手动添加更多信息，以弥补第一次机器提取信息的不足。

## 三、产品使用关键AI或机器学习之API的输出入展示
1. [使用水平](https://gitee.com/NFUNM031/book_search_pictures/blob/master/%E4%BD%BF%E7%94%A8%E6%B0%B4%E5%B9%B3.png "使用水平")
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/%E4%BD%BF%E7%94%A8%E6%B0%B4%E5%B9%B3.png)
