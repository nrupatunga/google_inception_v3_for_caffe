# Google Inception V3 for Caffe

## Introduction

This model is a replication of the model described in the [Rethinking the Inception Architecture for Computer Vision](http://arxiv.org/abs/1512.00567)

If you wish to train this model on ILSVRC2012 dataset remember to prepare
LMDB with 300px images instead of 256px.


## Hardware and Training

Original implementation from paper uses 32 batch size for 100 epochs
using RMSProp with learning rate of 0.045. This is provided
in paper_solver.prototxt, however if you want implementation that fits
onto 12GB GPU use solver.prototxt. You need some Titan X or K40 with more
than 10GB of RAM. Provided train_val.prototxt use batch_size = 20 and fits
into Titan X.


## Training

I have trained this model for 26 days on Titan X. At the time of writing
I had reached epoch 53 and here are accuracy tests:

```
I0307 16:25:17.482136  2001 solver.cpp:341] Iteration 3425000, Testing net (#0)
I0307 16:33:10.836920  2001 solver.cpp:409]     Test net output #0: acc/top-1 = 0.579853
I0307 16:33:10.837085  2001 solver.cpp:409]     Test net output #1: acc/top-5 = 0.813467
```

Accuracy still goes up so training is expected to finish in next 23 days
if everything will run smooth. According to the paper this model should
reach 3.46% top-5 error rate on ILSVRC2012 test set.



## License

This model is released for unrestricted use.
