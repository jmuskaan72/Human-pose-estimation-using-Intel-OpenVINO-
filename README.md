# Intel-Edge-AI-Basics
Stay at the cutting-edge of AI technology by gaining practical skills for deploying edge AI using the Intel OpenVINO Toolkit.

This is a multi-person 2D pose estimation network (based on the OpenPose approach) with tuned MobileNet v1 as a feature extractor. 

For every person in an image, the network detects a human pose: a body skeleton consisting of keypoints and connections between them.

The pose may contain up to 18 keypoints:

ears, eyes, nose, neck, shoulders, elbows, wrists, hips, knees, and ankles.

#Inputs::
Name: input , shape: [1x3x256x456]. An input image in the [BxCxHxW] format , where:
B - batch size
C - number of channels
H - image height
W - image width. Expected color order is BGR.

#Outputs::
The net outputs two blobs with the [1, 38, 32, 57] and [1, 19, 32, 57] shapes.
The first blob contains keypoint pairwise relations (part affinity fields), while the second blob contains keypoint heatmaps.
