# Optimized Inference at the Edge with Intel® Tools and Technologies 
This workshop will walk you through a computer vision workflow using the latest Intel® technologies and comprehensive toolkits including support for deep learning algorithms that help accelerate smart video applications. You will learn how to optimize and improve performance with and without external accelerators and utilize tools to help you identify the best hardware configuration for your needs. This workshop will also outline the various frameworks and topologies supported by Intel® accelerator tools. 

## How to Get Started
   
> :warning: For the in-class training, the hardware and software setup part has already been done on the workshop hardware. In-class training participants should directly move to Workshop Agenda section. 

In order to use this workshop content, you will need to setup your hardware and install the Intel® Distribution of OpenVINO™ toolkit for infering your computer vision application.  
### 1. Hardware requirements
#### a).The hardware requirements are mentioned in the System Requirement section of the [Guide](https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_linux.html#development_and_target_platform)
#### b).Intel® Vision Accelerator Design with Intel® Movidius™ VPUs
[VEGA-320](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-320/mod_f8aaa5f2-fe32-4a58-b5b4-2a02a857852a):m.2 Edge AI Module with one Intel® Movidius™ Myriad™ X VPU onboard

[VEGA-330](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-330/mod_120c6dca-5210-4d0d-b71f-8854a7faf1a1):miniPCIe Edge AI Module with two Intel® Movidius™ Myriad™ X VPUs onboard

### 2. Operating System
These labs have been validated on [Ubuntu 16.04.6 64bit](https://ubuntu.com/download/alternative-downloads)

### 3. Software installation steps
#### a). Install Intel® Distribution of OpenVINO™ toolkit 
Use steps described in the [Guide](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux)
to install the Intel® Distribution of OpenVINO™ toolkit, configure Model Optimizer, run the demos, additional steps to install Intel® Media SDK and OpenCL™ mentioned in the the guide. 

#### b). Install required packages
	sudo apt install git
	sudo apt install python3-pip
	sudo apt install libgflags-dev
	sudo pip3 install opencv-python
	sudo pip3 install cogapp
    
#### c). Run the demo scipts and compile samples
Delete $HOME/inference_engine_samples folder if it already exists. 

	rm -rf $HOME/inference_engine_samples
	
Run demo scripts (any one of them or both if you want to both the demos) which will generate the folder $HOME/inference_engine_samples with the current Intel® Distribution of OpenVINO™ toolkit built. 

	cd /opt/intel/openvino/deployment_tools/demo
	./demo_squeezenet_download_convert_run.sh
	./demo_security_barrier_camera.sh
	
	sudo chown -R username.username $HOME/inference_engine_samples_build
	cd $HOME/inference_engine_samples_build
	make

	sudo chown -R username.username $HOME/inference_engine_demos_build
	cd $HOME/inference_engine_demos_build
	make

#### d). Download models using model downloader scripts in Intel® Distribution of OpenVINO™ toolkit installed folder
   - Install python3 (version 3.5.2 or newer) 
   - Install yaml and requests modules with command:

	cd /opt/intel/openvino/deployment_tools/tools/model_downloader	
	python3 -mpip install --user -r ./requirements.in
   
   - Run model downloader script to download example deep learning models
  	
	sudo python3 downloader.py --name mobilenet-ssd,ssd300,ssd512,squeezenet1.1,face-detection-retail-0004,age-gender-recognition-retail-0013,head-pose-estimation-adas-0001,emotions-recognition-retail-0003,facial-landmarks-35-adas-0002

> :warning: This workshop content has been validated with Intel® Distribution of OpenVINO™ toolkit version R2 2019 (openvino_toolkit_2019.3.334). 


		
## Workshop Agenda
* **Smart Video/Computer Vision Tools Overview**
  - Slides - [Introduction to Smart Video Tools](./presentations/01-Introduction-to-Intel-Smart-Video-Tools.pdf)

* **Training a Deep Learning Model**
  - Slides - [Training a Deep Learning Model](./presentations/DL_training_model.pdf)
  
* **Basic End to End Object Detection Inference Example**
  - Slides - [Basic End to End Object Detection Example](./presentations/02-03_Basic-End-to-End-Object-Detection-Example.pdf)
  - Lab Setup - [Lab Setup Instructions](./Lab_setup.md)
  - Lab - Basic End to End Object Detection Example   [[C++](./object-detection/README.md)] <!--  [[Python](./object-detection/Python/basic_end_to_end_object_detection.ipynb)] -->
  - Lab - Tensor Flow example [[C++](./advanced-video-analytics/tensor_flow.md)] <!-- [[Python](./object-detection/Python/Tensor_Flow_example.ipynb)] -->
  - Lab - [Object Detection with YOLOv3* model](./object-detection/README_yolov3.md)

* **Hardware Heterogeneity**
  - Lab - Hardware Heterogeneity [[C++](./hardware-heterogeneity/README.md)] <!-- [[Python](./hardware-heterogeneity/Python/hardware-heterogeneity.ipynb)] -->

* **HW Acceleration with Intel® Movidius™ Neural Compute Stick**
  - Lab - HW Acceleration with Intel® Movidius™ Neural Compute Stick [[C++](./HW-Acceleration-with-Movidious-NCS/README.md)] <!--[[Python](./HW-Acceleration-with-Movidious-NCS/Python/HW_Acceleration_with_Movidius_NCS.ipynb)] -->

* **Optimization Tools and Techniques** 
  - Slides - [Optimization Tools and Techniques](./presentations/04-05_Optimization_and_advanced_analytics.pdf)
  - Lab - Optimization Tools and Techniques [[C++](./optimization-tools-and-techniques/README.md)] <!-- [[Python](./optimization-tools-and-techniques/Python/optimization_tools_and_techniques.ipynb)] -->
  
* **Advanced Video Analytics**
  - Lab - Multiple models usage example [[C++](./advanced-video-analytics/multiple_models.md)] <!-- [[Python](./advanced-video-analytics/Python/advanced_video_analytics.ipynb)] -->
<!----  
* **UP²\* AI Vision Development kit as Edge**
  - Setup - [Development machine and Internet Connection Sharing](./up2-vision-kit/dev_machine_setup.md)
  - Lab - [Interact face detection on UP2 kit using Intel® System Studio](./up2-vision-kit/openvino-projects-using-iss2019.md) ---->
  
* **Additional Examples - Reference Implementations**
  - Industrial 
  	- [Safety Gear Detection](./safety-gear-example/README.md)
	- [Restricted Zone Notifier](https://github.com/intel-iot-devkit/restricted-zone-notifier-cpp)
  	- [Object Size Detector](https://github.com/intel-iot-devkit/object-size-detector-cpp)
  - Retail 
  	- [Store Traffic Monitor](https://github.com/intel-iot-devkit/store-traffic-monitor)
	- [Shopper Gaze Monitor](https://github.com/intel-iot-devkit/shopper-gaze-monitor-cpp)
<!--	
* **Workshop Survey**
  - [Workshop Survey](https://idz.qualtrics.com/jfe/form/SV_a9GvOxtOrOziykB)
  - [Custom Layer Tutorial Survey](https://intelemployee.az1.qualtrics.com/jfe/form/SV_1ZjOKaEIQUM5FpX)
  - [Embedded Vision Summit Workshop Survey](https://intel.az1.qualtrics.com/jfe/form/SV_6RsCwmj6QGD3PAF)
  -->
> #### Disclaimer

> Intel and the Intel logo are trademarks of Intel Corporation or its subsidiaries in the U.S. and/or other countries. 
 
> *Other names and brands may be claimed as the property of others
