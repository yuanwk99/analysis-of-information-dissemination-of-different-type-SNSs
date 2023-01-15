# 《不同社交媒体平台的热点事件传播演化的比较研究》
## 以微博和抖音平台为例，对比分析热点话题事件的信息传播及其演化规律。

## 3.1.2热点事件的主题具体合并规则
爬取微博热搜的原始主题类别有以下86种：
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/algorithm/微博热搜的原始主题类别（汇总）.png)

热点事件主题的横纵向的主题合并规则如下：
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/algorithm/热点事件主题的横纵向的主题合并规则.png)

## 3.1.2基于深度学习算法的热点事件的主题分类模型
利用微博热搜API获得微博热点话题的所属主题类别，将微博热搜的标题名称经过去重后，共计15718条热搜名称。其中，微博热点话题的主题类别为“暂无”的有1325条，将其余数据按照9:1的比例划分训练集和验证集，将微博热点话题的主题类别为“暂无”和抖音的所有热点话题的数据作为训练集。采用Bert及其优化模型进行文本标题分类模型的训练和预测。我们采用三种预训练模，采取focal loss和采用Over-Sampling的两种策略解决类别的分布不均衡的问题（效果如表4.1）。结果表明，Roberta加Over-Sampling的效果最好，在验证集得到了0.967的F1指标。 \

models|Sampling|focal loss|Sampling|focal loss
----|----|----|----|----
_| F1 |macro F1 | F1 |macro F1
chinese-bert-base | 0.9436	|0.9416|	0.8111|	0.7018
chinese-bert-wwm-ext | 0.9487|	0.947	|0.8147	|0.712
chinese-roberta-wwm-ext-large |**0.967**|	0.966	|0.8353|	0.7353


## 3．2 共同-特有热点事件分类算法
本文利用LAC工具对热点话题的标题名称实现词性标注，得到标题的分词集合与词性集合，并对不同平台的标题集合计算Jaccard相似度，若Jaccard相似度大于阈值且两个集合中人名、组织名、地名、时间、数量、动词等决定标题含义的实词相同，则将该标题加入共同热点话题集合，否则将该标题加入社交媒体平台的特有话题，具体算法如下
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/algorithm/社交平台共同-特有热点话题分类算法.png)

## 4.2热点事件主题的时间序列分析
（1）每个主题以月份为周期的季节性箱型图
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/月份为周期.png)
（2）每个主题以星期为周期的季节性箱型图
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/星期为周期.png)

## 4.3热点事件在不同社交媒体平台的生命周期分析

### 4.3.1热点事件的生命周期演化分析

(1)#甘肃山地马拉松事故21人遇难# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/微博-甘肃马拉松.html)\
![图片](https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/微博-甘肃马拉松-blog.png)
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/抖音-甘肃马拉松.html)

(2)#台风烟花# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/微博-台风烟花.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/抖音-台风烟花.html)

(3)#千万不要随便回复网友评论# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/微博-千万不要.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/抖音-千万不要.html)

(4)#苏炳添男子百米第6# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/微博-苏炳添.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/话题生命周期/抖音-苏炳添.html)

### 4.2.2热点事件的热门帖子的生命周期演化分析

(1)#甘肃山地马拉松事故21人遇难# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/wb评论-甘肃.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/dy评论-甘肃.html)

(2)#台风烟花# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/wb评论-台风烟花.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/dy评论-台风烟花.html)

(3)#千万不要随便回复网友评论# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/wb评论-千万不要.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/dy评论-千万不要.html)

(4)#苏炳添男子百米第6# \
微博事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/wb评论-苏炳添.html)\
抖音事件生命周期 [查看演化详情]( https://yuanwk99.github.io/analysis-of-information-dissemination-of-different-type-SNSs/results/survey2/帖子生命周期/dy评论-苏炳添.html)

