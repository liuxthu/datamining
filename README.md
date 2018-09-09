数据挖掘可以对大量数据集进行清理，处理，总结规律，将这原理应用于分类，推荐系统，预测等方面。
### 一、数据挖掘的一般过程
1.数据选择

2.数据预处理

3.数据转换

4.数据挖掘

5.解释与评价

### 二、数据挖掘常用算法概括

#### 1.关联分析算法

Apriori算法：在关联分析中经典算法是R．Agrawal等人提出的Apriofi算法Ⅲ，这是一种很有影响力的挖掘关联规则频繁项集的算法，它探查逐级挖掘Apfiofi性质：频繁项集的所有非空子集都必须是频繁的。根据频繁k．项集，形成频繁(k+1)．项集候选，并扫描数据库1次，完成第k次迭代(k>1)，找出完整的频繁 (k+1)一项集Lk+-。

AprioriTID算法

FP-growth算法

#### 2.分类算法
决策树算法：ID3算法，C4.5算法， SLIQ算法， SPRINT算法， RainForest算法

朴素Bayes分类算法

CBA(Classification Based on Association)算法

MIND(Mining in Database)算法 

神经网络：

粗集理论:
粗集理论的特点是不需要预先给定某些特征或属性的数量描述，如统计学中的概率分布、模糊集理论的隶属度或 隶属函数等，而是直接从给定问题出发，通过不可分辨关系和不可分辨类确定问题的近似域,从而找出问题中的内在规律。 

遗传算法
遗传算法是模拟生物进化过程，利用复制(选择)、交叉(重 组)和变异(突变)3个基本算子优化求解的技术。遗传算法类 似统计学，模型的形式必须预先确定，在算法实施的过程中， 首先对求解的问题进行编码，产生初始群体，然后计算个体的
适应度，再进行染色体的复制、交换、突变等操作，优胜劣汰， 适者生存，直到最佳方案出现为止。


#### 3.聚类算法
聚类分析与分类不同，聚类分析处理的数据对象的类是未知的。聚类分析就是将对象集合分组为由类似的对象组成 的多个簇的过程。

Ipartitioning method(划分方法) 给定1个N个对象或者元组的数据库，1个划分方法构建 数据的K个划分，每1个划分表示1个聚簇，并且K<N。
经典算法有K．MEAN(K平均值)[161 K-MEDOIDS(K中心 点)o”，而且这些算法已经被加入到许多统计分析软件包或系统中，例如SAS、SPSS。 

hierarchical method(层次方法)
层次方法对给定数据对象集合进行层次的分解。根据分 解的形成不同，层次方法可以分为凝聚的层次方法和分裂的 层次方法。
层次方法存在着缺陷：一旦1个步骤完成，它就不能被撤 消，这样它就不能更正错误的决定。有两种方法可改进层次
聚类的结果；第1，使用CU爪．E和变色龙方法中的做法，在每个 层次划分时，仔细分析对象之间的联接；第2，综合层次凝聚和 迭代的重定位方法，首先用凝聚的自底向上的分析算法，然后 进行迭代的重定位来改进结果，BIRTH中用的就是这种算法。

grid．based method(基于网格的方法) 这种方法采用一个多分辨率的网格数据结构。将空间量
化为有限数目的单元，这些单元形成了网格结构，所有聚类分 析都在网格上进行。这种方法主要优点是：处理速度快，它的 处理时间仅依赖于量化空间中每一维上的单元数目，却独立
于数据的数目。常用的算法有STING，SkWAVECLUSTER和 CLIQUE。

其它基于模型的聚类分析方法
主要有统计学和神经网络方面的方法。




### 小结
随着数据量的日益积累以及数据库种类的多样化，数据 挖掘的应用前景相当广阔。本文对各类算法进行了分析、比 较和总结。总而言之，各种数据挖掘方法作用范围有限，都有 局限性，因此采用单一方法难以得到决策所需的各种知识。但
它们的有机组合具有互补性，多方法融合将成为数据挖掘算 法的发展趋势。


### 四、数据挖掘算法实现
### 1、相关知识

#### (1)距离度量：在数据挖掘中需要明确样本数据相似度，通常我们计算样本间的距离，如下为常用距离度量的介绍。
样本数据以：
![样本数据](https://user-gold-cdn.xitu.io/2018/9/6/165acaff8aac01cf?w=605&h=99&f=png&s=6558)

![坐标](https://user-gold-cdn.xitu.io/2018/9/6/165ad72a029f3d22?w=605&h=362&f=png&s=12159)


#### 曼哈顿距离：
也称曼哈顿街区距离，就如从街区的一个十字路口点到另一个十字路口点的距离，
二维空间（多维空间按同理扩展）用公式表示为
![](https://user-gold-cdn.xitu.io/2018/9/6/165af852e320fea3?w=682&h=92&f=png&s=14741)

![](https://user-gold-cdn.xitu.io/2018/9/6/165af7c0321440e0?w=605&h=356&f=png&s=15230)


#### 欧氏距离：
表示为点到点的距离。二维空间（多维空间按同理扩展）的公式表示为
![](https://user-gold-cdn.xitu.io/2018/9/6/165af8375b661141?w=846&h=99&f=png&s=23089)

![](https://user-gold-cdn.xitu.io/2018/9/6/165af84b783a086b?w=596&h=356&f=png&s=15492)

#### 闵可夫斯基距离：
是一组距离方法的概括，当p=1既是曼哈顿距离，当p=2既是欧氏距离。
![](https://user-gold-cdn.xitu.io/2018/9/6/165af8eebd55abee?w=155&h=57&f=png&s=2367)

闵可夫斯基距离（包括欧氏距离，曼哈顿距离）的优缺点：


优点：应用广泛。

缺点：无法考虑各分量的单位以及各分量分布（方差，期望）的差异性。（其中个分量的单位差异可以使用数据的标准化来消除，下面会有介绍。）

#### 余弦相关系数：
样本数据视为向量，通过两向量间的夹角余弦值确认相关性，数值范围[-1，1], -1表示负相关，0表示无关，1表示正相关。

![](https://user-gold-cdn.xitu.io/2018/9/7/165b211e1adf40e8?w=353&h=48&f=png&s=3937)
余弦相关系数的优缺点：

优点：余弦相似度与向量的幅值无关，只与向量的方向相关，在文档相似度（TF-IDF）和图片相似性（histogram）计算上都有它的身影；
在样本数值离散的时候仍可以使用。

缺点：余弦相似度受到向量的平移影响，上式如果将 x 平移到 x+1, 余弦值就会改变。(可以理解为受样本的起始标准的影响，接下来介绍的皮尔逊相关系数可以消除这个影响)

#### 皮尔逊相关系数
皮尔逊相关系数具有平移不变性和尺度不变性，计算出了两个向量（维度）的相关性。
![](https://user-gold-cdn.xitu.io/2018/9/7/165b29dfceee4ae8?w=704&h=68&f=png&s=6525)

考虑计算的遍历的次数，有一个替代公式可以近似计算皮尔逊相关系数：

![](https://user-gold-cdn.xitu.io/2018/9/7/165b2a5756a5a4a3?w=533&h=189&f=png&s=25601)

 皮尔逊相关系数优点：可消除每个分量标准不同（分数膨胀）的影响；
 
#### (2)数据标准化：
当需要通过各分量计算距离而各分量的单位尺度差异很大，可以使用数据标准化消除不同分量间单位尺度的影响，常用的方法有两种：

min-max 标准化：将数值范围缩放到（0,1）,但没有改变数据分布

![](https://user-gold-cdn.xitu.io/2018/9/7/165b2bdd4a7cd845?w=128&h=62&f=png&s=1391)
z-score 标准化：将数值范围缩放到0附近, 但没有改变数据分布

![](https://user-gold-cdn.xitu.io/2018/9/7/165b2bc6bd1995f7?w=95&h=47&f=png&s=1114)

#### (3) 算法的效果评估：

十折交叉验证：将数据集随机分割成十个等份，每次用9份数据做训练集，1份数据做测试集，如此迭代10次。

N折交叉验证又称为留一法：用几乎所有的数据进行训练，然后迭代留一个数据进行测试。留一法的优点是：确定性。

### 2、协同过滤推荐算法
#### (1)基于用户的协同推荐算法
这个方法是利用他人的喜好来进行推荐，工作原理是这样的：如果要推荐一个乐队给你，会在网站上查找一个和你类似的用户，然后将他喜欢的乐队推荐给你。

算法的关键在于找到相似的用户，迭代你与每个用户对乐队的评分距离来确定谁是你最相似的用户，距离计算可以用曼哈顿距离，皮尔斯相关系数等等。
![](https://user-gold-cdn.xitu.io/2018/9/7/165b33cfd31f1d8a?w=648&h=257&f=png&s=58602)
基于用户的协同推荐算法算法的缺点：

扩展性：随着用户数量的增加，其计算量也会增加。这种算法在只有几千个用户的情况下能够工作得很好，但达到一百万个用户时就会出现瓶颈。稀疏性：大多数推荐系统中，物品的数量要远大于用户的数量，因此用户仅仅对一小部分物品进行了评价，这就造成了数据的稀疏性。比如亚马逊有上百万本书，但用户只评论了很少一部分，于是就很难找到两个相似的用户了。

#### (2)基于物品的协同推荐算法
基于用户的协同过滤是通过计算用户之间的距离找出最相似的用户（通过将所有的评价数据在读取在内存中处理进行推荐），并将他评价过的物品推荐给目标用户。而基于物品的协同过滤则是找出最相似的物品（通过构建一个物品的相似度模型来做推荐），再结合用户的评价来给出推荐结果。

基于物品的协同推荐算法常用有如下两种：

#### 修正余弦相似度算法：
与皮尔逊相关系数的原理相同，对比物品i,j的相关性，对物品的每一评分减去该物品的平均值，而消除分数膨胀。

![](https://user-gold-cdn.xitu.io/2018/9/7/165b4596a0bf0e1f?w=399&h=128&f=png&s=17472)
修正余弦相似度的优点：扩展性好，占用内存小；消除分数膨胀的影响；

#### Slope One算法：
第一步，计算平均差值：
![slopeone](https://user-gold-cdn.xitu.io/2018/9/7/165b456e6ef82636?w=276&h=74&f=png&s=9386)
dev(i,j)为遍历所有共有物品i，j的用户u的评分平均差异。 card(Sj,i(X))则表示同时评价过物品j和i的用户数。

第二歩，使用加权的Slope One算法：
![](https://user-gold-cdn.xitu.io/2018/9/9/165bd05c5b75f331?w=320&h=116&f=png&s=12784)


 Slope One算法优点：算法简单；扩展性好，只需要更新共有属性的用户评价，而不需要重新载入整个数据集。
``` 
#推荐结果示例：
{'角斗士': 4.93334343410001,
'阿甘正传': 4.671796123644535}
 ```
 


论文参考：
代码实现：github
### 3、分类算法
#### (1)贝叶斯分类算法

#### (2)神经网络分类算法

### 4、聚类算法
#### (1)层次聚类

#### (2)K-means聚类




