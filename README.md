# 寻书APP
| 发布日期 | 2019年12月11日 | 
| ------ | ------ | 
| 产品名称 | 寻书APP | 
| 文件现状 | 正在更新 | 
| 文件的主人 | 黄晓宜 | 
| 领头的设计师 | 黄晓宜 |
| 领头的开发者 | 黄晓宜 |
| 迭代版本 | 1.0 |

### 一、加值宣言
- 用户在使用软件时可以通过通用文字识别API搜索和上传相关产品；平台在管理软件时可以通过通用文字识别API和图像审核API对平台的健康维护进行机器审核。
### 二、核心价值
- 最小可用产品为可进行图片文字识别的二手书交易平台
### 三、用户痛点：
- 闲置书籍杂志过多占空间，扔掉又过于可惜；
- 对于学生党来说全新正版实体书价格偏昂贵;
- 看到感兴趣的片段不知出自哪本书
- 对于旧版珍藏版书或者条形码损坏的书籍无法上传平台
- 书籍内容鱼龙混杂，不小心就会买到“踩坑”（违法、色情淫秽之类）的书
### 四、API加值：
- 通用文字识别API：
1.实现拍照文字识别、相册图片文字识别和截图文字识别，可应用于搜索和上传书籍信息。
2.实现对图像中文字内容的提取，结合文本审核技术识别违规内容，提示相应风险，协助进行违规处理，应用于违禁书籍审核，帮助用户有效规避业务风险。
- 图像审核API：
准确识别图片和视频中的涉黄、涉暴涉恐、政治敏感、微商广告、恶心等内容，也能从美观和清晰等维度对图像进行筛选，快速精准，解放审核人力
### 五、需求列表与人工智能API加值
| 用户痛点 | API加值 | 重要程度 |
| ------ | ------ | ------ |
| 对于旧版珍藏版书或者条形码损坏的书籍无法上传平台| 通用文字识别API | 最重要
| 看到感兴趣的片段不知出自哪本书 | 通用文字识别API | 重要
| 书籍内容鱼龙混杂，不小心就会买到“踩坑”（违法、色情淫秽之类）的书 | 通用文字识别API和图像审核API | 次重要
### 六、具体运用场景：
1. 新学期开头，小明买了一大堆新书籍，宿舍里书架放不下了，想要清理掉一批不要的旧书，但是有一本书是买的盗版的条形码扫描不了，此时软件可以使用通用文字识别技术，实现拍照文字识别，方便小明进行书籍文本的录入。
2. 小红在网络上看到一段很优美的文字，想购买此本书，但觉得先去百度搜索书名再去别的平台购书太麻烦了。此时软件可以使用通用文字识别技术，实现相册图片文字识别或截图文字识别，小红可应用于直接搜索该文字出处的书籍商品信息。
3. 肖老师想把这个平台推荐给他的学生可以低价去购买各类书籍，他希望他的学生们能在该平台上找到自己喜欢的积极向上健康的书籍。平台可以同时使用通用文字识别和图像审核功能，对含有不良信息的书籍进行下架。
### 七、API之输入及输出
1. 通用文字识别API：基于业界领先的深度学习技术，提供多场景、多语种、高精度的整图文字检测和识别服务
输入：
用户向服务请求识别某张图中的所有文字
```
""" 读取图片 """
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

image = get_file_content('example.jpg')

""" 调用通用文字识别, 图片参数为本地图片 """
client.basicGeneral(image);

""" 如果有可选参数 """
options = {}
options["language_type"] = "CHN_ENG"
options["detect_direction"] = "true"
options["detect_language"] = "true"
options["probability"] = "true"

""" 带参数调用通用文字识别, 图片参数为本地图片 """
client.basicGeneral(image, options)

url = "https//www.x.com/sample.jpg"

""" 调用通用文字识别, 图片参数为远程url图片 """
client.basicGeneralUrl(url);

""" 如果有可选参数 """
options = {}
options["language_type"] = "CHN_ENG"
options["detect_direction"] = "true"
options["detect_language"] = "true"
options["probability"] = "true"

""" 带参数调用通用文字识别, 图片参数为远程url图片 """
client.basicGeneralUrl(url, options)
```

输出：
```
{
"log_id": 2471272194,
"words_result_num": 2,
"words_result":
    [
        {"words": " TSINGTAO"},
        {"words": "青島睥酒"}
    ]
}
```

2. 图像审核API：为用户提供色情识别、暴恐识别、政治敏感人物识别、广告识别、图像垃圾文本识别（反作弊）、恶心图像识别等一系列图像识别接口的一站式服务调用，并且支持用户在控制台中自定义配置所有接口的报警阈值和疑似区间，上传自定义文本黑库和敏感人物名单等。相比于组合服务接口，本接口除了支持自定义配置外，还对返回结果进行了总体的包装，按照用户在控制台中配置的规则直接返回是否合规，如果不合规则指出具体不合规的内容。
输入：
```
""" 读取图片 """
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

""" 调用色情识别接口 """
result = client.imageCensorUserDefined(get_file_content('example.jpg'))

""" 如果图片是url调用如下 """
result = client.imageCensorUserDefined('http://www.example.com/image.jpg')
```

输出：
```
// 失败返回示例
{
    "log_id": 149319909347709,
    "error_code": 282800,
    "error_msg":"configId param is error or null"
}
// 成功返回示例-合规
{
    "log_id": 123456789,
    "conclusion": "合规"
}
// 成功返回示例-不合规
{
    "log_id": 123456789,
    "conclusion": "不合规",
    "data": [
        {
            "msg": "存在色情内容",
            "probability": 0.94308,
            "type": 1
        },
        {
            "msg": "存在性感内容",
            "probability": 0.94308,
            "type": 2
        },
        {
            "msg": "存在暴恐内容",
            "probability": 0.94308,
            "type": 3
        },
        {
        "msg": "存在恶心内容",
        "probability": 0.9688154,
        "type": 4
    },
        {
            "msg": "存在政治敏感内容",
            "stars": [
                {
                    "probability": 0.94308,
                    "name": "敏感人1"
                },
                {
                    "probability": 0.44308,
                    "name": "敏感人2"
                }
            ],
            "type": 8
        },
        {
            "msg": "存在二维码内容",
            "probability": 0.94308,
            "type": 6
        },
        {
            "msg": "存在水印码内容",
            "probability": 0.94308,
            "type": 5
        },
        {
            "msg": "存在条形码内容",
            "probability": 0.94308,
            "type": 7
        },
        {
            "msg": "包含联系方式",
            "probability": 0.94308,
            "words": "包含联系方式",
            "type": 8
        }
    ]
}
```
