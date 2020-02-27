# 文本检索：如何让计算机处理自然语言？
- 信息检索就是让计算机根据用户信息需求，从大规模、非结构化的数据中，找出相关的资料
- 这里的“非结构化”其实是针对经典的关系型数据库（Relation Database）而言的，因为资料没有经过严格的分析没有严格的定义
### 信息检索中的向量空间模型
- 我们通常会使用词包（Bag Of Word）的方式，忽略了单词在文章中出现的顺序，简化计算复杂度。类似地，这个模型也会把用户输入的查询转换为向量。如此一来，相关性问题就转化为计算查询向量和文档向量之间的距离或者相似度了。距离越小或者说相似度越高，那么我们就认为相关度越高。
- 1.把文档集合都转换成向量的形式。
- 2.把用户输入的查询转换成向量的形式，然后把这个查询的向量和所有文档的向量，进行比对，计算出基于距离或者夹角余弦的相似度。
- 3.根据查询和每个文档的相似度，找出相似度最高的文档，认为它们是和指定查询最相关的。
- 4.评估查询结果的相关性。
#### 向量的构成要素
- 维度：向量有多少维分量、每个分量的含义是什么，简单地说，我们要把文章中唯一的单词或者词组，作为向量的一个维度。经过预处理，我们就可以获得每篇文档出现的单词和词组。而通过对所有文档中的单词和词组进行去重，我们就可以构建整个文档集合的词典（Vocabulary）。向量空间模型把词典中的每个词条作为向量的一个维度。
- 取值：表示每个分量的数值是多少
##### 查询和文档的匹配
- 查询和文档长度不一致，文档中的词条是多维的，而查询的向量可能存在很多0 的多维
- 查询里出现了文档集合里没有的词。简单的做法是直接去除这维分量，也可以使用相对于其他维度来说极小的一个数值，这和分类中的平滑技术类似。
- 查询里词条的 idf 该如何计算。如果我们使用 tf-idf 机制来计算向量中每个维度的取值，那么就要考虑这个问题。由于查询本身并不存在文档集合的概念，所以也就不存在 df 和 idf。对于这种情况，我们可以借用文档集合里对应词条的 idf。
##### 排序和评估
- 完成了前两步，后面的排序和评估就很直观了。我们按照和输入查询的相似程度，对所有文档进行相似度由高到低的排序，然后取出前面的若干个文档，作为相关的信息返回