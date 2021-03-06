1.模型简介

该模型用于实验电影字幕生成。主要用于试用RNN模型，因此模型结构相对简单。最后生成的电影字幕有很多都是没有语义的，这一方面是由于训练数据过少，另外也是由于模型建模简单。可用于拓展成其他复杂模型。

2.要点

- 采用train, test, data_helper以及model的形式，将深度学习模型的书写结构固化成这种形式，有利于代码的阅读和扩展
- 采用tf.contrib.layers.embed_sequence(input_text, vocab_size, embed_dim)的方法直接将输入文本（转换成数字后）转换成添加成embed层后的
- 采用np.split进行数据的切割，用于生成数据
- 在预测文本时有两种方式，第一种是每次采用最大的概率值对应的词（greedy）的方式，第二种是采用np.random.choice，根据概率来随机选择一个词，其中概率越大的词越容易被选中。一般情况下，更推荐第二种方式来生成文本。