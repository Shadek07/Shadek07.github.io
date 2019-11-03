## WorldModel in Pytorch

To understand the worldmodel implementation deeply, I have converted [tensorflow version](https://github.com/hardmaru/WorldModelsExperiments) (version 1.8.0) of carracing implementation into pytorch version. I identified several differences between tensorflow and pytorch. The implementation of pytorch is quite shorter than tensorflow in terms of number of lines of code. It is mostly because, in pytorch computational graph is computed dynamically and there is no need to create session as like in tensorflow. Another difference is: in pytorch you can set device type (either gpu or cpu) for each tensor in the computation graph. Many of the instructions from [replicating worldmodel](https://shadekcse.wordpress.com/2019/08/02/how-to-replicate-world-model-carracing-by-training-from-scratch-on-ubuntu-18-04/) is still relevant for this pytorch version. So I will not duplicate writing.

### Required pip and conda packages with versions:

Pip Package                Version

---------------------- ---------------

Box2D                  2.3.2

Box2D-kengz            2.3.3

cma                    2.2.0

gym                    0.9.4

gym-pull               0.1.7

mpi4py                 2.0.0

numpy                  1.17.3

Pillow                 6.2.0

pybullet               1.6.3

pyglet                 1.4.5

scipy                  1.1.0

tensorboard            1.8.0

tensorflow             1.8.0

tensorflow-tensorboard 0.4.0

torch                  1.3.0

tqdm                   4.36.1


Conda Package            Version                   Build  Channel

-------------------------------------------------------------------

cudatoolkit               10.0.130                      0

cudnn                     7.3.1                cuda10.0_0

cupti                     10.0.130                      0    anaconda

mkl                       2018.0.3                      1


### Github Repo:

### Instructions to run pytorch version:

### Some image reconstruction from vae training:
![vae_pytorch](/images/worldmodel_pytorch/vae_torch.gif)
