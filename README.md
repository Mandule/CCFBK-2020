# [CCF2020-贝壳-房产行业聊天问答匹配](https://www.datafountain.cn/competitions/474)

---

## 赛题介绍

### 背景

贝壳找房是以技术驱动的品质居住服务平台，“有尊严的服务者、更美好的居住”，是贝壳的使命。在帮助客户实现更美好的居住过程中，客户会和服务者（房产经纪人）反复深入交流对居住的要求，这个交流发生在贝壳APP上的IM中。

IM交流是双方建立信任的必要环节，客户需要在这个场景下经常向服务者咨询许多问题，而服务者是否为客户提供了感受良好、解答专业的服务就很重要，贝壳平台对此非常关注。因此，需要准确找出服务者是否回答了客户的问题，并进一步判断回答得是否准确得体，随着贝壳平台规模扩大，需要AI参与这个过程。

### 任务（文本匹配）

给定IM交流片段，片段包含一个客户问题以及随后的经纪人若干IM消息，从这些随后的经纪人消息中找出一个是对客户问题的回答。

#### 要点：
1. 数据来自一个IM聊天交流过程；
2. 选取的客户问题之前的聊天内容不会提供；
3. 提供客户问题之后的经纪人发送的内容；
4. 如果在这些经纪人发送内容之间原本来穿插了其他客户消息，不会提供；
5. 这些经纪人发送内容中只有1条是对客户问题的回答，把他找出来。

参赛者需要根据训练语料，构建出泛化能力强的模型，对不在训练语料中的测试数据做识别，从测试数据中为客户问题找出对应经纪人回答。希望参赛者能构建基于语义的识别模型，模型类型不限。

#### 难度与挑战：
1. IM聊天的随意性和碎片化，各个地方的语言习惯不同。
2. 要求模型的泛化性好。在测试集上模型的度量指标。
3. 要求模型的复杂度小。最终提交模型需要符合生产环境使用要求。

---

## 赛题数据

### 训练集

两个文件：客户问题文件和经纪人回复，涉及6000段对话（有标签答案）

客户问题文件：
1. 对话ID：Int
2. 客户问题：String（同一对话ID有且仅有一个问题）

经纪人回复文件：
1. 对话ID：Int
2. 经纪人回复ID：Int（对应真实回复顺序）
3. 经纪人回复内容：String
4. 经纪人回复标签：Int [0, 1]（只有一个是回答）

### 测试集

两个文件：客户问题文件和经纪人回复，涉及14000段对话（无标签答案）

客户问题文件：
1. 对话ID：Int
2. 客户问题：String（同一对话ID有且仅有一个问题）

经纪人回复文件：
1. 对话ID：Int
2. 经纪人回复ID：Int（对应真实回复顺序）
3. 经纪人回复内容：String

---

## 评测

提交文件格式：
1. 对话ID：Int
2. 经纪人回复ID：Int（对应真实回复顺序）
3. 经纪人回复标签：Int [0, 1]（只有一个是回答）

评测标准：F1

---

## 参考

[huggingface](https://huggingface.co/transformers/#)

[【HugBert01】Huggingface Transformers，一个顶级自然语言处理框架](https://zhuanlan.zhihu.com/p/141527015)

[【HugBert02】热身运动：安装及向量编码](https://zhuanlan.zhihu.com/p/143161582)

[【HugBert03】最后一英里：下游NLP任务的微调](https://zhuanlan.zhihu.com/p/149779660)

[【HugBert04】GLUE：BERT类模型的通用评估基准](https://zhuanlan.zhihu.com/p/151818251)

[【HugBert05】照猫画虎：理解from_pretrained，攒个模型下载器](https://zhuanlan.zhihu.com/p/158974273)

[HuggingFace-Transformers系列的下游应用](https://zhuanlan.zhihu.com/p/149740784)

[RoBERTa中文预训练模型，你离中文任务的「SOTA」只差个它](https://zhuanlan.zhihu.com/p/81274077)

[SMP2020微博情绪分类比赛总结](https://zhuanlan.zhihu.com/p/264864179)

[BDCI2019-SENTIMENT-CLASSIFICATION](https://github.com/cxy229/BDCI2019-SENTIMENT-CLASSIFICATION)

[清华中文预训练语言模型](https://github.com/thunlp/OpenCLaP)

[RoBERTa中文预训练模型](https://github.com/brightmart/roberta_zh)

[CLUE中文预训练语言模型](https://github.com/CLUEbenchmark/CLUEPretrainedModels)

[哈工大讯飞中文预训练语言模型Chinese-BERT-wwm](https://github.com/ymcui/Chinese-BERT-wwm)

[哈工大讯飞中文预训练语言模型Chinese-ELECTRA](https://github.com/ymcui/Chinese-ELECTRA)



