### WorldModel in Pytorch

To understand the worldmodel implementation deeply, I have converted [tensorflow version](https://github.com/hardmaru/WorldModelsExperiments) (version 1.8.0) of carracing implementation into pytorch version. I identified several differences between tensorflow and pytorch. The implementation of pytorch is quite shorter than tensorflow in terms of number of lines of code. It is mostly because, in pytorch computational graph is computed dynamically and there is no need to create session as like in tensorflow. Many of the instructions from [replicating worldmodel](https://shadekcse.wordpress.com/2019/08/02/how-to-replicate-world-model-carracing-by-training-from-scratch-on-ubuntu-18-04/) is still relevant for this pytorch version. So I will not duplicate writing.

## Required pip libraries with versions:

## Github Repo:

## Instructions to run pytorch version:

Some image reconstruction from vae training
