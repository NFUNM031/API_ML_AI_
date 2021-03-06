# 寻书APP
[Pecha Kucha.pptx](https://github.com/NFUNM031/API_ML_AI_/blob/master/Pecha%20Kucha.pptx)

| 发布日期 | 2019年12月11日 | 
| ------ | ------ | 
| 产品名称 | 寻书APP | 
| 文件现状 | 更新完毕 | 
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
- [通用文字识别API](https://ai.baidu.com/tech/ocr/general)：针对图片模糊、倾斜、翻转等情况进行了优化，鲁棒性强，识别速度快，且支持2W+大字库，总体识别准确率高达99%。
- [计算机视觉API](https://www.azure.cn/zh-cn/home/features/cognitive-services/computer-vision/)：计算机视觉算法可根据图像中标识的对象生成各种说明。会对说明一一进行评估，并生成置信度。 然后返回一个列表，将置信度从高到低进行排列。
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/probability.jpeg)
### 5.需求列表
用户身份：卖家

| 编号 | 核心功能 | 优先级 | 是否有可行及可用的API加值 |
| ------ | ------ | ------ | ------ |
| 1 | 注册 | 重要 | 无 |
| 2 | 登陆 | 重要 | 无 |
| 3 | 发布/录入图书信息 | 重要 | 百度通用文字识别API |
| 4 | 修改图书信息 | 次要 | 无 |
| 5 | 价格评估 | 次要 | 无 |
| 6 | 发货 | 重要 | 无 |
| 7 | 对话 | 重要 | 无 |
| 8 | 处理订单 | 重要 | 无 |

用户身份：买家

| 编号 | 核心功能 | 优先级 | 是否有可行及可用的API加值 |
| ------ | ------ | ------ | ------ |
| 1 | 注册 | 重要 | 无 |
| 2 | 登陆 | 重要 | 无 |
| 3 | 浏览图书信息 | 次要 | 计算机视觉API |
| 4 | 添加图书到购物车 | 重要 | 无 |
| 5 | 修改购物车中的图书 | 重要 | 无 |
| 6 | 下订单 | 重要 | 无 |
| 7 | 修改会员信息 | 重要 | 无 |
| 8 | 确认收货评价 | 重要 | 无 |

## 二、原型
### 1.[原型](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B%E5%9B%BE.png "原型")
- 交互及界面设计——卖家上传发布书籍（百度通用文字识别API）
- 信息设计——买家搜索书籍信息（计算机视觉API）
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E6%93%8D%E4%BD%9C%E6%B5%81%E7%A8%8B%E5%9B%BE.png)
### 2.[原型文档](http://nfunm031.gitee.io/book_finding)
[下载文档](https://github.com/NFUNM031/API_ML_AI_/blob/master/%E5%AF%BB%E4%B9%A6.rp)
### 3.口头操作说明
1. 卖家打开软件进入首页后可以看到首页下方有“发布”按钮，点击“发布”按钮后弹出窗口可选择“扫条形码卖书“或者”扫图卖书“，对于拥有可用条形码的书籍可以直接扫条形码提取信息（准确率较高）；而对于无条形码可用书籍杂志周边等产品可以选择扫图卖书通过文字识别提取信息（准确率相对较低）。本次主要介绍“扫图卖书”功能，用户点击”扫图卖书“后进入手机本地相册页面选取书籍照片，也可以点击“拍照”功能进行现场拍摄。选中图片后app自动扫描图片内容并直接进入“发布”页面，此时页面里已经自动提取生成了书籍的相关信息，用户确定价格后可以直接发布，也可以手动添加更多信息，以弥补封面信息的不足。
2. 买家进入APP后点击搜索框进入搜索页面，输入书籍名称后点击“搜索”按钮进入商品列表。点击感兴趣的商品进入商品主页面，对于无法正确感知色彩的用户可以长按图片（要识别的部位）使用扫图识别，app用机器识别物体并用人类可认知的语言表达描述出来。
- 详情见[原型文档](http://nfunm031.gitee.io/book_finding)

## 三、产品使用关键AI或机器学习之API的输出入展示
1. [使用水平](http://nfunm031.gitee.io/api_usage_level "使用水平")
2. 使用比较分析
#### （1）通用文字识别API对比：百度VS微软
##### 成熟度：对比可见百度的精确度比微软的高
#### 百度：![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E7%99%BE%E5%BA%A6%E4%BB%A3%E7%A0%81.png)
#### 微软：![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E5%BE%AE%E8%BD%AF%E4%BB%A3%E7%A0%81.png)
##### 性价比：百度每日有50000次免费调用量；微软每月5000 个免费事务。免费额度用尽后的收费标准也是百度较划算。
#### [百度](https://ai.baidu.com/ai-doc/OCR/9k3h7xuv6)
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E7%99%BE%E5%BA%A6%E6%80%A7%E4%BB%B7%E6%AF%94.png)
#### [微软](https://azure.microsoft.com/zh-cn/pricing/details/cognitive-services/computer-vision/)
#### 2019/12/25 汇率：1 USD = 7.0035 CNY
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E5%BE%AE%E8%BD%AF%E6%80%A7%E4%BB%B7%E6%AF%94.png)
#### 综合对比后得出：在文字识别API的应用中，百度较适用。
#### （2） 计算机视觉API对比：微软VS亚马逊
##### 成熟度：
- 通过对比可得“Amazon Rekognition 不仅仅能很好地识别主要对象，同时还能识别它周围的目标。例如当人、鸟和家具同时在图像中时，Rekognition 还能提供定性的判断，例如「漂亮」或「可爱」。这令其在最后预测时良好的均衡了主观和客观标签。”和“微软的标签通常层级较高，例如它经常返回「狗」、「犬」或「哺乳动物」，但从不具体反馈为「吉娃娃」或「松饼」。微软同样会将松饼识别为「毛绒玩具」，你可能认为 ResNet 有更好的性能，但也可能该测试受到数据集的影响，所以我建议你进行更鲁棒的测试。”两个结论。（参考链接：https://sdk.cn/news/7611 ）
- 除了基本的图像识别功能外，微软还能通过提供图像描述，为弱视用户提供支持。了解 Microsoft 如何将计算机视觉应用到 PowerPoint、Word、Outlook 和 Excel，以便为低视力用户实现图像的自动题注，帮助用户了解周围的世界。为视觉障碍者提供可行性方案是本产品调用计算机视觉API的最小可行目标，所以最终选用微软平台。（资料链接：https://azure.microsoft.com/zh-cn/services/cognitive-services/computer-vision/ ）
##### 性价比：微软长期每月5000 个免费事务；而亚马逊免费每月分析 5000 张图像的套餐只持续 12 个月。
#### [微软](https://azure.microsoft.com/zh-cn/pricing/details/cognitive-services/computer-vision/)
#### 2019/12/25 汇率：1 USD = 7.0035 CNY
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E5%BE%AE%E8%BD%AF%E6%80%A7%E4%BB%B7%E6%AF%94.png)
#### [亚马逊](https://aws.amazon.com/cn/rekognition/pricing/?nc=sn&loc=4)
#### 2019/12/25 汇率：1 USD = 7.0035 CNY
![image](https://github.com/NFUNM031/API_ML_AI_/blob/master/image/%E4%BA%9A%E9%A9%AC%E9%80%8A%E6%80%A7%E4%BB%B7%E6%AF%94.png)
- 综合对比后得出：在计算机视觉API的应用中，微软较合适。
3. 使用后风险报告
#### （1）通用文字识别API现在及未来发展性
- API市场竞争程度；市场上做通用文字识别API的公司有很多，较为出名的有百度、微软、Face++、华为、腾讯等，竞争十分激烈。
- 输入输出限制：对手写字体、艺术字体或背景复杂的文字识别有困难
- [可替代的程序库](https://www.cnblogs.com/lillylin/p/6893500.html)

#### （2）[计算机视觉API现在及未来发展性](https://36kr.com/p/5261408)
- API市场竞争程度
##### （1）国内竞争：“CV四小龙”（商汤、旷世、依图、云从），“海大宇”（海康威视、大华股份、宇视科技），BAT
##### （2）国际公司：谷歌，亚马逊，Facebook
- 计算机视觉现状与市场规模：
##### 计算机视觉作为人工智能的重要分支，在人工智能市场一直占有较高的比重，根据中国信通院报告数据，2017年中国人工智能市场中计算机视觉占比37%。
##### 国家虽然没有制定专门针对计算机视觉的政策，但在《新一代人工智能发展规划》中明确指出，将大力发展以计算机视觉为主要技术支撑的人类视觉能力感知获取、真实视觉感知以及智能城市的安全影像监控等。
##### 在政策鼓励和技术基础支撑下，计算机视觉行业逐步实现了从基础层到应用层的打通，开始涉足安防、金融、医疗、教育等领域，提供安防及监控、无人零售、人车识别等技术解决方案。
##### 根据前瞻产业研究院对CAICT（中国信息通信研究院）、Ganter、CBInsights等机构发布的数据汇总，2017年我国计算机视觉市场规模的增速都超过了110%。乐观估计2020年，我国计算机视觉市场规模有望突破1000亿；中性预测2020年我国计算机视觉市场规模在700亿元左右。





