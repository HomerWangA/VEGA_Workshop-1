# Optimized Inference at the Edge with Intel® Tools and Technologies 
This workshop will walk you through a computer vision workflow using the latest Intel® technologies and comprehensive toolkits including support for deep learning algorithms that help accelerate smart video applications. You will learn how to optimize and improve performance with and without external accelerators and utilize tools to help you identify the best hardware configuration for your needs. This workshop will also outline the various frameworks and topologies supported by Intel® accelerator tools. 

## How to Get Started
   
> :warning: For the in-class training, the hardware and software setup part has already been done on the workshop hardware. In-class training participants should directly move to Workshop Agenda section. 

In order to use this workshop content, you will need to setup your hardware and install the Intel® Distribution of OpenVINO™ toolkit for infering your computer vision application.  
### 1. Hardware requirements
#### a).The hardware requirements are mentioned in the System Requirement section of the [Guide](https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_linux.html#development_and_target_platform)
#### b).Intel® Vision Accelerator Design with Intel® Movidius™ VPUs
Advantech Edge AI Acceleration Modules

[VEGA-320](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-320/mod_f8aaa5f2-fe32-4a58-b5b4-2a02a857852a): m.2 Edge AI Module with one Intel® Movidius™ Myriad™ X VPU onboard

[VEGA-330](https://www.advantech.com/products/3d060f1e-e73e-460d-b38c-c69f76312c91/vega-330/mod_120c6dca-5210-4d0d-b71f-8854a7faf1a1): miniPCIe Edge AI Module with two Intel® Movidius™ Myriad™ X VPUs onboard

### 2. Operating System
These labs have been validated on [Ubuntu 16.04.6 64 bit](https://ubuntu.com/download/alternative-downloads)

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
	
Modify the python module version networkx>=1.11 to networkx==1.11. Due to model optimizer will transfer the model failed when using python module "networkx" version 2.3. 

	sudo apt install -y vim
	sudo vim /opt/intel/openvino/deployment_tools/model_optimizer/requirements.txt

Then enter to install_prerequisites folder to excute the installation script.

	cd /opt/intel/openvino/development_tools/model_optimizer/install_prerequisites
	sudo -E ./install_prerequisites.sh
	
Run demo scripts (any one of them or both if you want to both the demos) which will generate the folder $HOME/inference_engine_samples with the current Intel® Distribution of OpenVINO™ toolkit built. 
	
	cd /opt/intel/openvino/deployment_tools/demo
	./demo_squeezenet_download_convert_run.sh
	./demo_security_barrier_camera.sh
	
	sudo chown -R {Your Username}.{Your Username} $HOME/inference_engine_samples_build
	cd $HOME/inference_engine_samples_build
	make

	sudo chown -R {Your Username}.{Your Username} $HOME/inference_engine_demos_build
	cd $HOME/inference_engine_demos_build
	make

#### d). Download models using model downloader scripts in Intel® Distribution of OpenVINO™ toolkit installed folder
   - Install python3 (version 3.5.2 or newer) 
   - Install yaml and requests modules with command:

	cd /opt/intel/openvino/deployment_tools/tools/model_downloader	
	python3 -mpip install --user -r ./requirements.in
   
   - Run model downloader script to download example deep learning models
  	
	sudo python3 downloader.py --name mobilenet-ssd,ssd300,ssd512,squeezenet1.1,face-detection-retail-0004,age-gender-recognition-retail-0013,head-pose-estimation-adas-0001,emotions-recognition-retail-0003,facial-landmarks-35-adas-0002

> :warning: This workshop content has been validated with Intel® Distribution of OpenVINO™ toolkit version R3 2019 (openvino_toolkit_2019.3.334). 

## Hands-on Pre-Configuration
#### Requirements
- Hardware & BIOS Configuration
- Advantech VEGA-320/330

#### OpenVINO Installation
- Ubuntu 16.04 (64-bit)
- Ubuntu 18.04 (64-bit)
- Windows 10 LTSC 2019 (64-bit)

## Hands-on LAB
#### Security_barrier_camera_demo
- Model Download
- Model Optimizer
- Inference Engine Compile
- Excute the Inference Engine Sample
#### Interactive_face_detection_demo
- Model Download
- Model Optimizer
- Inference Engine Compile
- Excute the Inference Engine Sample

<!--	
* **Workshop Survey**
  - [Workshop Survey](https://idz.qualtrics.com/jfe/form/SV_a9GvOxtOrOziykB)
  - [Custom Layer Tutorial Survey](https://intelemployee.az1.qualtrics.com/jfe/form/SV_1ZjOKaEIQUM5FpX)
  - [Embedded Vision Summit Workshop Survey](https://intel.az1.qualtrics.com/jfe/form/SV_6RsCwmj6QGD3PAF)
  -->
> #### Disclaimer

> Intel and the Intel logo are trademarks of Intel Corporation or its subsidiaries in the U.S. and/or other countries. 
 
> *Other names and brands may be claimed as the property of others
