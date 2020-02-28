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

## Installation of the Intel® Distribution of OpenVINO™ toolkit 2019 R2 for Windows* 

This tutorial assumes that you have already installed the [Intel® Distribution of OpenVINO™ toolkit 2019 R2 for Windows*](https://software.intel.com/openvino-toolkit/choose-download/free-download-windows) into the default */opt/intel/openvino* directory.    If you have installed the toolkit to a different directory, you will need to change the directory paths that include "*/opt/intel/openvino*" in the commands below to point to your installation directory. If having any trouble iinstalling, you can refer to [Install Intel® Distribution of OpenVINO™ toolkit for Windows* 10](https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_windows.html).

The Intel® Distribution of OpenVINO™ toolkit includes the [Model Optimizer](https://docs.openvinotoolkit.org/2019_R2/_docs_MO_DG_Deep_Learning_Model_Optimizer_DevGuide.html).  This tutorial uses a TensorFlow framework model and assumes that you have already configured the Model Optimizer for use with TensorFlow.  If you did not configure the Model Optimizer for all the frameworks or not for TensorFlow explicitly during installation, be sure to do so following the steps for [Configuring the Model Optimizer](https://docs.openvinotoolkit.org/2019_R2/_docs_MO_DG_prepare_model_Config_Model_Optimizer.html) before proceeding.

After installing the Intel® Distribution of OpenVINO™ toolkit, the *classification_sample* executable binary will be located in the directory *%userprofile%\Documents\Intel\OpenVINO\inference_engine_samples_build\intel64\Release*.  This tutorial will use the *classification_sample* executable to run the example model.

## Setting Up the Environment

To begin, always ensure that your environment is properly setup for working with the Intel® Distribution of OpenVINO™ toolkit by running the command:

```bash
"C:\Program Files (x86)\IntelSWTools\openvino\bin\setupvars.bat"
```

