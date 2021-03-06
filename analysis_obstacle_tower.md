## Analysis on the replication of Obstacle Tower Challenge


The obstacle tower challenge environment has frame size of 84x84x3. Using this large size as input to trainable agent will consume huge memory and time to train. For this reason, I have attempted to train VAE (variational autoencoder) on Obstacle challenge dataset to have a compact representation of environment. The obstacle challenge data has been collected from Nichol's github [repo](https://github.com/unixpickle/obs-tower2). Nichol secured top position in this challenge.

After the training of VAE, I found that VAE is not going to be helpful for training of Obstacle tower challenge. It is because a single frame of Obstacle Tower environment contains multiple different objects and the reconstructed frame from VAE output is blurry. The different objects in the original frame becomes indistinquishable in the reconstructed frame. Let the image below:

![VAE image](/images/analysis_obstacle/obstacle_vae.gif)

Some of the competitors in this challenge had also applied world model and VAE but they could not achieve significant performance compared to other techiniques they applied. [Details of the competion winners and their approaches](https://blogs.unity3d.com/2019/08/07/announcing-the-obstacle-tower-challenge-winners-and-open-source-release/)

## Replication results of Nichols's code


## Sources

[Nichol's repo](https://github.com/unixpickle/obs-tower2)
