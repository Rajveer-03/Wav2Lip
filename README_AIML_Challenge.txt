For this challenge, I proceeded to clone the Wav2Lip GitHub repository provided in the challenge description. 

Since I had to adjust frames with no-face of the video as per the model requirement. I made a change in the inference.py file in the face_detect(images) module. Previously, the module would throw an exception whenever it encountered a frame with no face. I changed it so that it takes the previous frame with a face instead of throwing an exception.

Also, according to the model requirement, both the video and the audio were required to be of the same length. So, I edited the video and audio using Microsoft ClipChamp to some extent to satisfy the model requirement.

At last, I tried different combinations of available parameters to get the best result possible. I used the --nosmooth flag to minimize the Lipsync glitches, and decreased the fps to 20 using --fps 20 to get the audio and video in coherence. I also reduced the resolution of the video using --resuce_size 2, since the model was trained on low-resolution data as per the documentation. Finally, I provided custom padding of 0px 20px 0px 0px to accommodate the chin part in the Lipsync.

During My exploration, I also encountered other models that could provide better and more optimized results. For eg: visual_quality_disc.pth and lipsync_expert.pth provided by Wav2Lip, even some other models e.g.: WaveGlow by NVIDIA. Unfortunately, I could not generate a successful result under the time constraint.