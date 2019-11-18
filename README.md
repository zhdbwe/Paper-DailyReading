# Paper-DailyReading

|Models|RG-1|RG-2|RG-L|
|------|----|----|----|
|ETADS|41.75|19.01|38.89| 

|Models|RG-1|RG-2|RG-L|
|------|-----|----|----|
|BART|44.16|21.28|40.90|

2019-11-07

[Improving Abstractive Document Summarization with Salient Information Modeling](https://www.aclweb.org/anthology/P19-1205.pdf) ACL2019


这篇论文针对长文本编码和有效信息抽取的问题，提出了两种机制去解决。都是在注意力的基础上进行修改的。

1. focus attention 用于解决长文本编码问题，考虑到局部的信息，在query和key的运算之后加入高斯噪声，使其在远离注意力中心的单词权重更小一些。
2. selection network 用于解决有效信息抽取的问题，用key和query计算出当前单词的有效信息打分，然后将打分乘上注意力的权重

2019-11-08

[BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension](https://arxiv.org/pdf/1910.13461.pdf) arxiv

这是一篇关于预训练的论文，和之前的预训练任务不同，本篇论文专注于生成任务。

创新点主要有两点：
1. 和其他预训练模型不同，本模型同时使用了encoder(双向用于编码信息)和decoder(单向用于生成任务),好像和原始的transformer也没有什么区别
2. 提出了不同的掩码和变换方式,包括了Token masking ,token deletion, text infilling, sentence permutation, document rotation

2019-11-18

[Transformer-XL: Attentive Language Models Beyond a Fixed-Length Context](https://arxiv.org/pdf/1901.02860.pdf) arxiv

本论文对原始Transformer模型只能编码固定长度的数据进行改进(Vaswani Transformer -> Universal Transformer -> Transformer-XL)

1. 使用RNN的思想，将前面的状态作为历史信息输入到下一个时间步，和RNN不同的地方在于他不是在同一层输入历史信息，而是利用了上一层的历史信息
2. 使用了相对位置编码，防止绝对位置编码时，两个不同的Block的同一位置不能区分。
