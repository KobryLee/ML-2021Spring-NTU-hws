# self-attention, cnn, rnn, gnn, spatial transform layer and unsupervised learning

## the structure of self-attention
![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/attention-score.png)
* attention means the relation between the input patches
* after calculationg the attention-score, we will normalize them with softmax or relu .etc and **we need to calculate the relation between query1 and itself key1**

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/attention-score-softmax.png)

* then we can extract information according to the attention score and value

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/value-based-attention.png)

* besides, position encoding will show the sequence of the input seq

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/position-encoding.png)

* self-attention matrix form

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/qkv-matrix.png)![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/attention-score-matrix.png)![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/whole-matrix.png)




## relation between cnn and self-attetion
![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/attention-vs-cnn.png)
* a paper introduce how to transfer a transformer to cnn [*on the relationship between self-attention and convolutional layers*](https://arxiv.org/abs/1911.03584)
* cnn is a subset of attention, attention is more flexible, and easy to overfit. This means attention need more data, to avoid overfitting.
![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture3/easy-overfit.png)
* when data is large, attention has a better performance. Cnn is good for less data.
* to do: how to reduce the memory of transformer [*Efficient Transformer: A survey*](https://arxiv.org/abs/2009.06732)
