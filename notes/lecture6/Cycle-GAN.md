# Cycle GAN

## unsupervised transfer

![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/28-unsup-transfer.png)

* we can use unpaired samples(without label) to do image style transfering
* for example, in the picture, we can input images in domain X and expect to generate this image in another domain y.

## cycle GAN

![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/29-cycle-gan.png)

* we need a G(x->y) and a G(y->x), to avoid G(x->y) randomly generates a sample in domain y which will get high score in discriminator, but which has a very consistency with the input
* we add G(y->x) to calculate the cycle consistency between input and the output after two generator.

![image](https://github.com/KobryLee/ML-2021Spring-NTU-hws/blob/main/notes/statics/lecture6/30-cycle-gan.png)

* the full strucutre of the cycle gan is shown as above.
* we will train another Dx to discriminate the the output of sample in domain y after G(y->x), to obain a much better performance



