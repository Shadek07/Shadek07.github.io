As part of my worldmodel experiment, I wanted to create Unity environment executable of VisualPushBlock game. Visual Push Block is different from PushBlock where in VisualPushBlock environment will be provided as first person image of size (1x84x84x3). I was having issue of generating visual observation of pushBlock in python. The issue is that: after I load unity environment in python, a visual unity environment opens up but Any code below the opening of UnityEnv was not executed. So I could not get data of visual image via python. Here is what I was trying to do:


```from mlagents.envs import UnityEnvironment

env_name = './VisualPushBlock/Unity Environment.exe'

env = UnityEnvironment(file_name=env_name)

default_brain = env.brain_names[0]

brain = env.brains[default_brain]

print(brain)

print(brain.camera_resolutions)
```


Here, the last two print statements were not being executed.

To solve this problem, I basically had to change the way I created Unity environment executable by changing several parameters and adding a few items while creating environment executable. First of all, “Control checkbox” of VisualPushBlock academy brain has to be checked to make the brain external.
![External](/images/create_visual_pushblock_unity_env/unity-brain-external.png)

Second, Under “visual area” hierarchy there is ‘Agent’ object. Agent object has a segment of ‘Push Agent basics’. Change brain in that segment to ‘VisualPushBlockLearning’ instead of ‘VisualPushBlockPlayer’. See figure below.
![Learning](create_visual_pushblock_unity_env/unity-visual-brain.png)

Next, Click on ‘VisualPushBlockLearning’ within brains hierarchy. On the parameter section, change vector observation space size to 0 and add a visual observation of size 84x84. 
![Space](create_visual_pushblock_unity_env/space_size.png.png)

When creating executable (with env_name.86_64 extension) for linux, a separate folder is also get created named as env_name_data. You need to move this folder too where you want to execute .86_64 file.
