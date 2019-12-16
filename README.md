# API_ML_AI
|   发布时期  |   2019-12-08  |
| --- | --- |
| 史诗名称    |   自然汉语  |
|  文件现状   |  完成  |
|  文件的主人   |  谭怡颖   |
|  领头设计者   |   谭怡颖  |
|  领头开发者   |  谭怡颖   |
|  领头测试者   |  谭怡颖   |  

### （一）背景  
随着中国“一带一路”的经济建设和语言学习旅行市场的扩大，愈来愈多的外国人学习中文，兴起了汉语热。汉语的语法不同于欧洲的语法，而且一词存在多词义想象，为此汉语也被评为世界难学语言的前十。目前，市场上虽然有许多汉语学习的APP，但是都只是针对汉语的发音和字词基础学习，不能对用户日常错误的文本/句子提供反馈，用户只能在现实生活中碰壁寻找答案。  
###  (二）价值主张  

### （三）加值宣言  
基于为了让初学汉语的外国人能够了解基本的汉语语法，还能够掌握更符合自然语境的语言表达。APP首先会采用百度的文本纠错api，识别用户输入的文本中有错误的片段，进行错误提示并给出正确的建议文本内容；然后采用百度的依存句法分析API，自动分析正确文本中的依存句法结构信息，实现对自然语言的精准理解；同时采用有道的文本翻译api，将中文的解析文本转换成目标语言文本，便于用户理解。
### （四）核心价值  
帮助用户提高对汉语自然语言的理解和运用水平。
### （五）用户痛点  
- 痛点一：课堂上不是很理解老师讲的这个句子的结构分析。
- 痛点二：汉语老师布置了一篇作文，不知道我的作文是否有错误的文本？
- 痛点三：身边没有中国的朋友，中文语法好难学啊。
### （六）需求列表  
标题 | 用户案例 | 重要程度 
--- | --- | ---
文本纠错    |    我句子里的文本有没有错误呢？      |    重要      
依存句法分析   |   这篇文章里的这个句子的各个词语之间的依存关系是什么？       |    重要      
文本翻译   |    这中文表达的是什么意思？      |    次重要      
### （七）AI产品概率性  
- **百度文本纠错API**  
在文本纠错上，对日常常用的固定词组和日常的常见的专有名词，文本纠错的成功率高；但对于古诗词和比较陌生的专有名词，文本纠错率会比较低。为此，在用户使用该功能时会弹出窗口，告诉用户“对于古诗词和比较陌生的专有名词，文本纠错率会比较低。”减少用户对该两类文本句子的文本纠错功能的使用，同时本产品针对的是对中文自然语言的理解，双重的前提提示下，降低用户获得错误反馈或者无结果反馈的失望值。  
- **百度依存句法分析API**  
在对句子的依存分析上，仅能对中文简体的句子有精准的理解，对中文繁体、文言文无法达到正常程度上的理解。为此，会在用户输入的文本框中以预文本的形式告诉用户“请输入现代中文简体文本内容哦~Please input modern Chinese Simplified text”。对于无法理解的拟声词、音译文本和古诗词等，则会给用户诙谐、幽默的错误反馈。  
- **有道文本翻译API**  
目前，有道在长篇内容的翻译质量上次于短篇文本内容的翻译质量。根据市场调研情况，大多数的用户在内容搜索上会更倾向短文本的搜索，认为短文本的搜索更具有精准性并且花费的时间更短。因此，有道这方面的缺陷不会对用户产生过大的负面影响，而压过产品对用户的正面影响。

### （八）API调用  
#### 百度文本纠错API
1. [百度文本纠错API调用代码档](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E6%96%87%E6%9C%AC%E7%BA%A0%E9%94%99api.ipynb)
- 百度文本纠错API输入输出  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E6%96%87%E6%9C%AC%E7%BA%A0%E9%94%99%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA.png)  
[腾讯文本纠错API调用代码档](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E8%85%BE%E8%AE%AF%E6%96%87%E6%9C%AC%E7%BA%A0%E9%94%99API.ipynb)
- 腾讯文本纠错API输入输出  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E8%85%BE%E8%AE%AF%E6%96%87%E6%9C%AC%E7%BA%A0%E9%94%99%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA.png)  

**2. “百度文本纠错API”与“腾讯文本纠错API”的对比分析**  
- [百度文本纠错API官方文档](https://ai.baidu.com/ai-doc/NLP/vk3pmn49r#%E6%96%87%E6%9C%AC%E7%BA%A0%E9%94%99%E6%8E%A5%E5%8F%A3)  
- [腾讯文本纠错API官方文档](https://cloud.tencent.com/document/product/271/35509)  

|        | 百度 | 腾讯 | 
| ------ | ---- | ---- |
| 成熟度 |  文本内容可以支持GBK和UTF-8两种格式的编码；付费版本提供7乘24小时售后客服响应；拥有百度十几年的中文互联网数据积累；效果稳定性强  |  基于千亿级大规模互联网语料和LSTM、BERT等深度神经网络模型进行训练；提供指定区域数据，保证数据传输质量；提供腾讯云命令行工具，可以快速轻松地调用腾讯云API管理自己的腾讯云资源  |  
| 性价比 |  提供限量免费调用；按量结算付费：0.0025元/次，QPS限制20；次数包付费参考下图    |   公测期间（截至2019年12月31日24:00），暂不提供购买服务，提供免费的无限制量调用服务	   |  

- 百度文本纠错接口次数包价目表  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E6%96%87%E6%9C%AC%E5%88%86%E6%9E%90%E4%BB%B7%E7%9B%AE%E8%A1%A8.png)  

**3.所使用的API类别的使用风险报告**  
- 市场竞争程度：目前国内中文文本纠错相关的API在自己能查询的条件下，有腾讯、百度、聚合数据和三色云四个平台提供文本纠错的接口服务。相对腾讯和百度，聚合和三色云成熟度与市场知名度较低，未见有该接口的相关合作案例。而目前腾讯文本纠错API仍处于公测期间，未有正式产品，成熟度、价格、优劣等各方面有待考量。因此，就个人分析而言，中文文本纠错接口服务目前在国内市场竞争程度不大。（在自己可查询范围下，未找到相关文献说明）
- 输入输出限制：待分析文本，长度有字节限制和编码要求；允许中英文结合，但无法理解句子的语义；返回内容的编码指定为用户指定输入的编码；返回格式通常为JSON格式。
- 定价：就目前已查询的公司来看，百度和聚合数据提供了购买服务，聚合数据的每次调用价格约为0.0067元/次，而百度的每次调用费用是0.0025元。百度的价格低于聚合数据的价格。
- 可替代程序库：https://my.oschina.net/keyven/blog/516808

#### 百度依存句法分析API
1. [百度依存句法分析API调用代码档](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E4%BE%9D%E5%AD%98%E5%8F%A5%E6%B3%95%E5%88%86%E6%9E%90.ipynb)   
- 百度依存句法API输入输出  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E4%BE%9D%E5%AD%98%E5%8F%A5%E6%B3%95.png)  
[讯飞依存句法分析API调用代码档](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E8%AE%AF%E9%A3%9E%E4%BE%9D%E5%AD%98%E8%AF%AD%E5%8F%A5%E5%88%86%E6%9E%90.ipynb)
- 讯飞依存句法API输入输出  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E8%AE%AF%E9%A3%9E%E4%BE%9D%E5%AD%98%E5%8F%A5%E6%B3%95.png)
**2. "百度依存语句分析API"与"腾讯句法依存分析API"的对比分析**  
- [百度依存句法分析接口官方文档](https://ai.baidu.com/ai-doc/NLP/ak3pmn40n#%E4%BE%9D%E5%AD%98%E5%8F%A5%E6%B3%95%E5%88%86%E6%9E%90%E6%8E%A5%E5%8F%A3)
- [讯飞依存句法分析接口官方文档](https://www.xfyun.cn/doc/nlp/dependencyParsing/API.html)  

|        | 百度 | 讯飞 | 
| ------ | ---- | ---- |
| 成熟度 |  文本内容可以支持GBK和UTF-8两种格式的编码；提供两个不同情境使用的模型训练数据集；除了输出依存关系数据外，还提供该文本的词性，便于用户更透彻地理解；支持中英结合的语句依存关系分析   |  以哈工大社会计算与信息检索研究中心研发的 “语言技术平台（LTP）” 为基础提供自然语言处理服务； 文本输入长度可长至500字节；采用MD5哈希计算，保证安全性  |  
| 性价比 |  提供限量免费调用；按量结算付费：0.015元/次，QPS限制20；次数包付费参考下图    |   提供限量免费调用；暂不提供购买服务   |  

- 百度依存句法接口次数包价目表  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E4%BE%9D%E5%AD%98%E8%AF%AD%E5%8F%A5-%E6%AC%A1%E6%95%B0%E5%8C%85%E8%B4%AD%E4%B9%B0.png)

**3. 所使用的API类别的使用风险报告**  
- 市场竞争程度：目前国内依存句法相关的API在自己能查询的条件下，除了以上提到的百度和讯飞的依存句法接口外，还有腾讯的依存句法接口。目前腾讯的依存句法分析处于公测期间。腾讯和讯飞依存句法分析结果都只返回父节点与依存关系两点有用数据，缺少对该词/字的词性说明，需要额外调用词性分析API，并且目前两款产品也暂不提供购买服务。就目前状况而言，国内的中大型企业以及定制化需求市场上市场竞争程度不大。句法分析是自然语言处理的基本问题，虽然目前国内提供的依存句法分析的平台很少，但依存句法分析在学术界得到广泛地讨论和研究，因此未来依存句法分析的机器研究应会被广泛开发，具有巨大的市场竞争力。
- 输入输出限制：待分析文本，长度有字节限制和编码要求。内容中如果有相关音译词或非中华字典中存在的字词，则无法理解，返回内容为输入的内容。返回内容的编码指定为用户指定输入的编码，返回格式通常为JSON格式。  
- 定价：就目前所查询到的国内企业中，除了百度提供了购买服务外，另外两个公司均无提供购买服务。无法判断定价的合理性和未来竞争性。
- 可替代程序库：LTP是是哈工大社会计算与信息检索研究中心历时十年研制的一整套开放中文自然语言处理系统，具有一整套自底向上的丰富、高效、高精度的中文自然语言处理模块，并且目前LTP是国内外最具影响力的中文处理基础平台。pyltp是LTP的Python封装，![python&pyltp实现依存句法分析](https://blog.csdn.net/weixin_43846196/article/details/100635711)

#### 有道文本翻译API  
1. **有道文本翻译API输入输出**  
```
import sys
import uuid
import requests
import hashlib
import time
from imp import reload
import time

reload(sys)

YOUDAO_URL = 'https://openapi.youdao.com/api'
APP_KEY = '?' # 自己申请的APP_KEY
APP_SECRET = '?' # APP_KEY对应的APP_SECRET

def encrypt(signStr):
    hash_algorithm = hashlib.sha256()
    hash_algorithm.update(signStr.encode('utf-8'))
    return hash_algorithm.hexdigest()

def truncate(q):
    if q is None:
        return None
    size = len(q)
    return q if size <= 20 else q[0:10] + str(size) + q[size - 10:size]

def do_request(data):
    headers = {'Content-Type': 'application/x-www-form-urlencoded'}
    return requests.post(YOUDAO_URL, data=data, headers=headers)

def connect():
    q = "待输入的文字"

    data = {}
    data['from'] = 'zh-CHS'
    data['to'] = 'en'
    data['signType'] = 'v3'
    curtime = str(int(time.time()))
    data['curtime'] = curtime
    salt = str(uuid.uuid1())
    signStr = APP_KEY + truncate(q) + salt + curtime + APP_SECRET
    sign = encrypt(signStr)
    data['appKey'] = APP_KEY
    data['q'] = q
    data['salt'] = salt
    data['sign'] = sign

    response = do_request(data)
    contentType = response.headers['Content-Type']
    print(response.content)


if __name__ == '__main__':
    connect()
```  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E6%9C%89%E9%81%93%E7%BF%BB%E8%AF%91%E8%BE%93%E5%87%BA.png)  
[百度文本翻译API调用代码档](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E7%BF%BB%E8%AF%91.ipynb)
- 百度文本翻译API输入输出  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E7%99%BE%E5%BA%A6%E6%96%87%E6%9C%AC%E7%BF%BB%E8%AF%91.png)  

**2. "有道文本翻译API"与"百度通用翻译API"的对比分析**  
- [有道文本翻译接口官方文档](https://irma.youdao.com/html/%E8%87%AA%E7%84%B6%E8%AF%AD%E8%A8%80%E7%BF%BB%E8%AF%91/API%E6%96%87%E6%A1%A3/%E6%96%87%E6%9C%AC%E7%BF%BB%E8%AF%91%E6%9C%8D%E5%8A%A1/%E6%96%87%E6%9C%AC%E7%BF%BB%E8%AF%91%E6%9C%8D%E5%8A%A1-API%E6%96%87%E6%A1%A3.html)
- [百度通用翻译接口官方文档](http://fanyi-api.baidu.com/api/trans/product/apidoc#joinFile)  

|        | 有道 | 百度 | 
| ------ | ---- | ---- |
| 成熟度 |  支持对上百种语言间的互译，并可对多个国家的语种进行自动识别；提供24小时云端高稳定服务；提供中英离线句子翻译结果，确保无网络或网络不佳等情况下稳定的翻译服务；达到企业机构对安全性的要求;拥有健全的用户翻译数据统计报表，实时了解翻译情况   |  提供28种语言高质量翻译服务；无访问频次限制，服务稳定性SLA高达99.99%  |  
| 性价比 |  提供50元体验资金，体验文本翻译服务；中文与其他语种间互译：48元/百万字符    |  标准版：免费使用，不限使用字符量；高级版、尊享版：每月翻译字符数低于200万，享免费服务；超过200万字符，按照49元/百万字符支付当月超出部分字符量费用。    |  

**3.所使用的API类别的使用风险报告**  
- 市场竞争程度：目前文本翻译相关的API在自己能查询的条件下，有百度、腾讯、讯飞、有道、谷歌、微软等BAT大型IT公司，还有一些机器翻译的创业公司如火如荼地发展起来。无论在国内还是国外，现在还是将来，文本翻译的市场竞争力是非常大的。
- 输入输出限制：
- 定价：根据上述所提到的公司，查找了各自文本翻译API服务的产品价格，产品的平均价格为53元/百万字符。有道的文本翻译价格低于该平均价格5元，有道的市场竞争力会更大，并且价格设置也是合理的。

### （九）产品架构图  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E4%BA%A7%E5%93%81%E6%9E%B6%E6%9E%84%E5%9B%BE.jpg)
### （十）产品原型设计  
[产品原型文档下载](https://github.com/ViTaSoyi/interactive_prototype)  
[产品交互原型](http://virginiat.gitee.io/interactive_prototype/start.html#g=1&p=%E9%A6%96%E9%A1%B5)

- **首页**  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E9%A6%96%E9%A1%B5.png)  
- **收藏**  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E6%94%B6%E8%97%8F.png)  
- **发现**  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E5%8F%91%E7%8E%B0.png)  
- **我的**  
![](https://github.com/ViTaSoyi/API_ML_AI/blob/master/%E6%88%91%E7%9A%84.png)
