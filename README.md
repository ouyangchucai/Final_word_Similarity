## 词语相似度高级版
综合词林扩展版与Hownet的相似度计算策略和评价指标，来自文献1，代码为本人实现。采用融合计算方式，扩大了词汇覆盖面，也改进了计算结果的合理性。</br>

**具体算法选择**：</br>
+ 词林扩展版</br>
（1）最初采用了[【词林相似度计算：实现了3种算法】](https://github.com/ashengtx/CilinSimilarity)
中的2016版代码（文献1），比另2种算法效果更好。</br>
（2）后来发现作者团队发表了更新、更优的算法——文献2。于是实现了其中算法，经验证论文结果属实。</br>
（3）再后来发现又有了新的算法——文献3。然后按论文思想，原封不动实现效果略逊色于论文数据。但经过调整策略，最终效果优于论文本身。</br>

+ 知网Hownet</br>
（1）开源的代码大多均参考刘群的论文，但效果与主观感受有差距。目前选用:[【知网相似度计算】。](https://github.com/240400968/hownet-similarity)本人修改了其中读取词表遗漏的bug，改善了代码的风格，提高了可读性。</br>
（2）知网计算相似度已有最新论文——文献4，性能有较大提升（在改进Hownet上达到0.84），但算法代码有待实现，希望得到网友贡献。

### 参考文献
> 【1】《基于知网与词林的词语语义相似度计算》朱新华,马润聪,孙柳,陈宏朝,2016年7月《中文信息学报》 </br>
> 【2】《基于路径与深度的同义词词林词语相似度计算》陈宏朝, 李飞, 朱新华,马润聪. 2016年9月《中文信息学报》</br>
> 【3】《基于信息内容的词林词语相似度计算》彭琦, 朱新华, 陈意山,等.2018年2月《计算机应用研究》</br>
> 【4】《基于多重继承与信息内容的知网词语相似度计算》张波，陈宏朝，朱新华等.2017年10月 《计算机应用研究》

### 不同语义库上算法对比：

|相似度方法|所用语义词典|词汇量|皮尔逊系数|
|------------|:--:|:-:|:-:|
|田久乐 赵蔚(2010)	|同义词词林	|77456	|0.53|
|吕立辉等(2013)	|同义词词林	|77456|	0.74|
|陈宏朝等(2016-9)	|同义词词林|77456|	0.856|
|yaleimeng(2018)|改进的词林|77490	|0.917|

|相似度方法|所用语义词典|词汇量|皮尔逊系数|
|------------|---------|:-:|:-:|
|刘群、李素建(2002)|HowNet(知网)|	53335|0.699|
|Seco(2004)+Lin方法|HowNet(知网)|	53335|0.738|
|李峰、李芳(2007)|	HowNet(知网)|	53335|	0.793|
|张波等(2017)|改进HowNet|	53335	|0.84|

|相似度方法|所用语义词典|词汇量|皮尔逊系数|
|------------|---------|:-:|:-:|
|yaleimeng（2018）|词林+HowNet|85777	|0.885|
>注：</br>
1 上面的皮尔逊系数均在MC30数据集上测得。</br>
2 本混合方法计算可调节词林与hownet计算结果的权重，表格中成绩可能为最大值(两词均被同时收录)。</br>

如需了解预训练词向量计算的中文词语相关度，可参见：[中文近义词工具包Synonyms](https://github.com/huyingxi/Synonyms)

**原创不易，欢迎打赏、捐赠：**</br>
<img src="https://github.com/yaleimeng/Scrapy_Projects/blob/master/movie/payQR.png" title="Logo" width="400" /> 
