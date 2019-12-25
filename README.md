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
- 对于不可以直接扫条形码上传的书籍，在本产品用户可以使用“扫图上传”。本产品调用百度通用文字识别API实现拍照/截图识别功能，实现拍照文字识别、相册图片文字识别和截图文字识别，方便用户进行文本的提取或录入，有效提升产品易用性和用户使用体验。
- 对于色盲用户，本产品会调用微软的计算机视觉API，以人类可读语言生成整个图像的说明。
### 2.核心价值宣言
让社会的闲置书籍资源能够被回收利用
### 3.用户痛点宣言
- 对于旧版珍藏版书或者条形码损坏的书籍无法上传平台
- 色盲用户无法正确感知彩色图片的相关信息
### 4.AI概率性考量：
- 通用文字识别API：针对图片模糊、倾斜、翻转等情况进行了优化，鲁棒性强，识别速度快，且支持2W+大字库，总体识别准确率高达99%。
- 计算机视觉API：计算机视觉算法可根据图像中标识的对象生成各种说明。会对说明一一进行评估，并生成置信度。 然后返回一个列表，将置信度从高到低进行排列。
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/probability.jpeg)
### 5.需求列表
用户身份：卖家

| 编号 | 核心功能 | 优先级 | 是否有可行及可用的API加值 |
| ------ | ------ | ------ | ------ |
| 1 | 注册 | 高 | 无 |
| 2 | 登陆 | 高 | 无 |
| 3 | 发布/录入图书信息 | 高 | 百度通用文字识别API |
| 4 | 修改图书信息 | 中 | 无 |
| 5 | 价格评估 | 中 | 无 |
| 6 | 发货 | 高 | 无 |
| 7 | 对话 | 高 | 无 |
| 8 | 处理订单 | 高 | 无 |

用户身份：买家

| 编号 | 核心功能 | 优先级 | 是否有可行及可用的API加值 |
| ------ | ------ | ------ | ------ |
| 1 | 注册 | 高 | 无 |
| 2 | 登陆 | 高 | 无 |
| 3 | 浏览图书信息 | 中 | 计算机视觉API |
| 4 | 添加图书到购物车 | 高 | 无 |
| 5 | 修改购物车中的图书 | 高 | 无 |
| 6 | 下订单 | 高 | 无 |
| 7 | 修改会员信息 | 高 | 无 |
| 8 | 确认收货评价 | 高 | 无 |

## 二、原型
### 1.[原型](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B%E5%9B%BE.png "原型")
- 交互及界面设计——卖家上传发布书籍（百度通用文字识别API）
- 信息设计——买家搜索书籍信息（计算机视觉API）
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B%E5%9B%BE.png)
### 2.[原型文档](http://nfunm031.gitee.io/book_finding)
[下载文档](https://github.com/NFUNM031/API_ML_AI_/blob/master/%E5%AF%BB%E4%B9%A6.rp)
### 3.口头操作说明
见原型文档
## 三、产品使用关键AI或机器学习之API的输出入展示
1. [使用水平](http://nfunm031.gitee.io/api_usage_level "使用水平")
2. 使用比较分析
#### （1）通用文字识别API对比：百度VS微软
- 成熟度：对比可见百度的精确度比微软的高
#### 百度：![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E7%99%BE%E5%BA%A6%E4%BB%A3%E7%A0%81.png)
#### 微软：![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E5%BE%AE%E8%BD%AF%E4%BB%A3%E7%A0%81.png)
- 性价比：百度每日有50000次免费调用量；微软每月5000 个免费事务。免费额度用尽后的收费标准也是百度较划算。
[百度](https://ai.baidu.com/ai-doc/OCR/9k3h7xuv6)
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E7%99%BE%E5%BA%A6%E4%BB%B7%E6%A0%BC.png)
[微软](https://azure.microsoft.com/zh-cn/pricing/details/cognitive-services/computer-vision/)
#### 2019/12/25 汇率：1 USD = 7.0035 CNY
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E5%BE%AE%E8%BD%AF%E4%BB%B7%E6%A0%BC.png)
#### 综合对比后得出：在文字识别API的应用中，百度较适用。



