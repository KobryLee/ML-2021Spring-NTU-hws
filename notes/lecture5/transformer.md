# transformers

## structure

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/5-decoder-structure.png)

## encoder

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/1-encoder-overall-structure.png)

* encoder is a set of blocks, and one block consist of a self-attention module and a MLP to get intermediate variables as the input of the next block. After several blocks, we get the final output of encoder.

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/2-transformer-encoder-structure.png)

* in every block, the input will first processed by a self-attention module with skip-connection to get the variable *a+b*
* then it uses a lyaer norm for the output of the self-attention module, which work on the different dimensions of one feature. by contrast, batch norm calculate the average of the same dimension of different features.
* then MLP will process the output of self-attention will fully-connected networks and use skip -connection tech, after this the output of MLP will also be applied to layer norm.

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/3-encoder-detail.png)

* as for the detailed structure, the block in encoder has such a structure, consisting of self-attention(skip-connection), layer norm and MLP(skip-connection) layer norm

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/4-paper-about-norm.png)

* some research about the layer norm

## decoder

### masked self-attention

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/6-masked-self-attention(generate-b-one-by-one).png)

* in decoder, the output will be generated one-by-one, which mean the first output will only notice the first input and second output will notice the first and the second input

### stucture

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/7-stop-decoder.png)

* there is a question, we need to let decoder automatically stop, otherwise the decoder will generate output endlessly. So we add a stop token to be predicted.

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/8-non-auto-regressive.png)

* except the one-by-one generating form, we also have a non-auto-regressive type decoder
* specifically, NAT decoder need another predictor to determine the length of output, or set a very large number for the length of output and output a very long sequence and ignore the tokens after END 
* NAT is faster and can control the length of output.


### connection between encoder and decoder

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/9-connection.png)

* we use cross attention to connect encoder and decoder, decoder provide query and encoder provide key and value

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/10-detailed-connection.png)
![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/11-detailed-connection-2.png)

* above two imgs show how the first two output of decoder generate
** we need to notice that, decoder's output only act as query, do not calculate the key and value, which means its value will not be used.
** the second output will only calculate the attention-score with the output of the encoder, because decoder will not generate query and value
** *all in all, decoder will only generate query*

### training method

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/12-training-method.png)

* in the training stage, we will provide the ground truth token to the decoder and minimize the cross entropy betweent the output and the ground trurh

![img](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture5/15-mismatch-train-inference.png)

* because we offer the decode the ground truth in training, so there is a gap between train and inference.
* to be specific, in the inference stage, if a middle token is predicted wrong, the following output tokens have a very large chance to get wrong ouput
* some solution: *scheduled sampling*




