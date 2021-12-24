# GAN (generative adversarial network)

## why need distribution

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/1-why-need-distribution.png)

* in real world, many times we need many different outputs for the same input, so we need a distribution to randomly generate outputs

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/2-why-need-distribution.png)

* for example, for a video game prediction, there may be many situations in the next moment, so we can't use just use one output to predict all situation, or there will be some conflicts

## algorithm

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/3-algorithm1.png)
![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/4-algorithm2.png)
![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/5-algorithm3.png)

* step 1: fix generator G, updata discriminator D to assign high scores to real objects and low scores to the generated objects
* step 2: fix discriminator D, update generator D to generate more real picture to "fool" discriminator
* step 3: repeat above processes


## theory

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/6-objective.png)

* make the divergence of the two distribution small
* the question is we do not know how to caluculate the divergence between distributions Pg and Pdata

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/7-sample-as-distribution.png)

* we don't know the distribution, we use sample to estimate the distribution

![iamge](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/8-discriminator.png)

* we train the discriminator to give real data from Pdata higher score and give generative data Pg lower score, by using log(D(y)) and log(1-D(y))
* the goal is a estimation of the js-div of distribution, amazingly.
* **maxD V(G,D) is very related to JS-Div(Pg,Pdata)**
![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/10-replace-div.png)

![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/9-effect-of-discriminator.png)

* this picture shows what discriminator does

## divergence and the object function

![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/11-paper.png)

* this paper tell us the divergence and the corresponding object function, which is highly related to.



