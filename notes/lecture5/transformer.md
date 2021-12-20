# transformers

## encoder

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/1-encoder-overall-structure.png)

* encoder is a set of blocks, and one block consist of a self-attention module and a MLP to get intermediate variables as the input of the next block. After several blocks, we get the final output of encoder.

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/2-transformer-encoder-structure.png)

* in every block, the input will first processed by a self-attention module with skip-connection to get the variable *a+b*
* then it uses a lyaer norm for the output of the self-attention module, which work on the different dimensions of one feature. by contrast, batch norm calculate the average of the same dimension of different features.
* then MLP will process the output of self-attention will fully-connected networks and use skip -connection tech, after this the output of MLP will also be applied to layer norm.
