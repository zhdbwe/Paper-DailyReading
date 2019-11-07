# Paper-DailyReading
2019-11-07

[Improving Abstractive Document Summarization with Salient Information Modeling](https://www.aclweb.org/anthology/P19-1205.pdf) ACL2019


这篇论文针对长文本编码和有效信息抽取的问题，提出了两种机制去解决。都是在注意力的基础上进行修改的。

1. focus attention 用于解决长文本编码问题，考虑到局部的信息，在query和key的运算之后加入高斯噪声，使其在远离注意力中心的单词权重更小一些。
2. selection network 用于解决有效信息抽取的问题，用key和query计算出当前单词的有效信息打分，然后将打分乘上注意力的权重

|Models|RG-1|RG-2|RG-L|
|------|----|----|----|
|ETADS|41.75|19.01|38.89| 
