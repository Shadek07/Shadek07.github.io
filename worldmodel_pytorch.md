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

torch                  1.3.0

tqdm                   4.36.1


Conda Package        -    Version    -                Build -  Channel

-------------------------------------------------------------------
mkl             -          2018.0.3           -             1

**for cuda 10.0:**

cudatoolkit        -       10.0.130           -             0

cudnn           -          7.3.1        -        cuda10.0_0

cupti          -           10.0.130       -                0   -  anaconda

**for cuda 9.0:**

conda install cudatoolkit=9.0

conda install cudnn=7.1.2

conda install cupti=9.0


### Github Repo:
[Repository link](https://github.com/Shadek07/worldmodel_pytorch)

### Instructions to run pytorch version:

If your PC doesn’t have 64 CPU cores, you have to edit extract.bash file. Default code assumes that you have >= 64 core CPUs. Run the command (bash extract.bash) four times. Each time choose only 16 CPU cores (1 to 16, then 17 to 32, then 33 to 48 then 49 to 64)).

After that do the following 3 commands:
1. python vae_train.py

2. python series.py

3. python rnn_train.py

then following commands:

cp ./tf_vae/vae.pt ./vae/

cp ./tf_initial_z/initial_z.json ./initial_z/

cp ./tf_rnn/rnn.pt ./rnn/

Add this line: os.environ["CUDA_VISIBLE_DEVICES"]="",  inside **train.py** to stop using gpu for this job: **bash gce_train.bash**


if you get an error likeAttributeError: 'ImageData' object has no attribute 'data’, then do the following
changed line_number 380 of this file residing in the directory similar to this: /home/hdilab/.conda/envs/worldmodel/lib/python3.5/site-packages/gym/envs/box2d/car_racing.py:

**arr = np.fromstring(image_data.get_data('RGBA',image_data.width*len('RGBA') ), dtype=np.uint8, sep='')  **

### Some image reconstruction from vae training:
![vae_pytorch](/images/worldmodel_pytorch/vae_torch.gif)

## Training progess of worldmodel controller
![training](/images/worldmodel_pytorch/worldmodel_pytorch_train.png)

## Test trained controller with trained VAE and RNN:
for 100 episodes, we got an avg reward of 815.83 with std of 100.66 (**815 ± 100**)
