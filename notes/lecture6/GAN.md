# GAN (generative adversarial network)

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



