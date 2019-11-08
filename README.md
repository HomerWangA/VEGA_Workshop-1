# Optimized Inference at the Edge with Intel® Tools and Technologies 
This workshop will walk you through a computer vision workflow using the latest Intel® technologies and comprehensive toolkits including support for deep learning algorithms that help accelerate smart video applications. You will learn how to optimize and improve performance with and without external accelerators and utilize tools to help you identify the best hardware configuration for your needs. This workshop will also outline the various frameworks and topologies supported by Intel® accelerator tools. 

## How to Get Started
   
> :warning: For the in-class training, the hardware and software setup part has already been done on the workshop hardware. In-class training participants should directly move to Workshop Agenda section. 

> :warning: This workshop content has been validated with Intel® Distribution of OpenVINO™ toolkit version R3 2019 (openvino_toolkit_2019.3.334). 

In order to use this workshop content, you will need to setup your hardware and install the Intel® Distribution of OpenVINO™ toolkit for infering your computer vision application.  
### 1. Hardware requirements
#### Option 1. Advantech AIR-100 with VEGA-320
[VEGA-320](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-320/mod_f8aaa5f2-fe32-4a58-b5b4-2a02a857852a): m.2 Edge AI Module with one Intel® Movidius™ Myriad™ X VPU onboard
#### Option 2. Advantech AIR-200 withc VEGA-330
[VEGA-330](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-330/mod_120c6dca-5210-4d0d-b71f-8854a7faf1a1): miniPCIe Edge AI Module with two Intel® Movidius™ Myriad™ X VPUs onboard

### 2. OS & Pre-Configuration
- Ubuntu 18.04 x86_64 or Windows 10 2019 LTSC 64 bit
- [VEGA-320/330 Check](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/Pre_configure/VEGA_Check.md)

### 3. Intel OpenVINO Installation Steps
- [Ubuntu 16.04/18.04 (x86_64)](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/Installation/ubuntu.md)
- [Windows 10 LTSC 2019 (64-bit)](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/Installation/windows.md)

### 4. LAB Setup

Set the folder to execute labs in the workshop github.

#### Download workshop content and set directory path
Step 1. Create the workshop directory

	sudo mkdir -p /opt/advantech
	
Step 2. Change ownership of the workshop directory to the current user 

> **Note:** *replace the usernames below with your user account name*
		
	sudo chown username.username -R /opt/advantech

Step 3. Navigate to the new directory

	cd /opt/advantech

Step 4. Download and clone the workshop content to the current directory (/opt/intel/workshop/smart-video-workshop).
	
	sudo apt install -y git
	git clone https://github.com/ADVANTECH-EIoT/VEGA_Workshop.git
	
If you get a fatal message, "fatal: destination path 'smart-video-workshop' already exists and is not an empty directory.
",

	cd /opt/advantech/VEGA_Workshop/
	git pull

Step 5. Set short path for the workshop directory

	export SV=/opt/advantech/VEGA_Workshop/


### 5. Hands-on LABs (Ubuntu)

- [LAB 1: classification_sample_async](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/hands_on/classification_sample_async/classification_sample_async.md)

- [LAB 2: security_barrier_camera_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/Hands_on/security_barrier_camera_demo/security_barrier_camera_demo.md)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Security_Barrier_Camera_Demo.png)

- [LAB 3: interactive_face_detection_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/interactive_face_detection_demo/interactive_face_detection_demo.md)

- [LAB 4: human_pose_estimation_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/human_pose_estimation_demo/human_pose_estimation_demo.md)

- [LAB 5: text_detection_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/text_detection_demo/text_detection_demo.md)

- [LAB 6: gaze_estimation_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/gaze_estimation_demo/gaze_estimation_demo.md)

- [LAB 7: smart_classroom_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/smart_classroom_demo/smart_classroom_demo.md)

- [LAB 8: multichannel_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/multichannel_demo/multichannel_demo.md)

- [LAB 9: super_resolution_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/super_resolution_demo/super_resolution_demo.md)

- [LAB 10: segmentation_demo](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/tree/master/hands_on/segmentation_demo/segmentation_demo.md)

<!--	
* **Workshop Survey**
  - [Workshop Survey](https://idz.qualtrics.com/jfe/form/SV_a9GvOxtOrOziykB)
  - [Custom Layer Tutorial Survey](https://intelemployee.az1.qualtrics.com/jfe/form/SV_1ZjOKaEIQUM5FpX)
  - [Embedded Vision Summit Workshop Survey](https://intel.az1.qualtrics.com/jfe/form/SV_6RsCwmj6QGD3PAF)
  -->
> #### Disclaimer

> Intel and the Intel logo are trademarks of Intel Corporation or its subsidiaries in the U.S. and/or other countries. 
 
> *Other names and brands may be claimed as the property of others
