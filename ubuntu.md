# Install the Intel® Distribution of OpenVINO™ Toolkit Core Components
Download the Intel® Distribution of OpenVINO™ toolkit package file from [Intel® Distribution of OpenVINO™ toolkit for Linux*]( https://software.intel.com/en-us/openvino-toolkit/choose-download). Select the Intel® Distribution of OpenVINO™ toolkit for Linux package from the dropdown menu. 

## 1.	Open a command prompt terminal window.
## 2.	Change directories to where you downloaded the Intel Distribution of OpenVINO toolkit for Linux* package file.
If you downloaded the package file to the current user's Downloads directory: 
	cd ~/Downloads/
By default, the file is saved as l_openvino_toolkit_p_<version>.tgz. 
## 3.	Unpack the .tgz file:
	tar -xvzf l_openvino_toolkit_p_<version>.tgz
The files are unpacked to the l_openvino_toolkit_p_<version> directory.
## 4.	Go to the l_openvino_toolkit_p_<version> directory:
	cd l_openvino_toolkit_p_<version>
If you have a previous version of the Intel Distribution of OpenVINO toolkit installed, rename or delete these two directories:

	/home/<user>/inference_engine_samples_build
	/home/<user>/openvino_models
    
Installation Notes:
* Choose an installation option and run the related script as root.
* You can use either a GUI installation wizard or command-line instructions (CLI).
* Screenshots are provided for the GUI, but not for CLI. The following information also applies to CLI and will be helpful to your installation where you will be presented with the same choices and tasks.
## 5. Choose your installation option:
- Option 1: GUI Installation Wizard:
	sudo ./install_GUI.sh
- Option 2: Command-Line Instructions:
	sudo ./install.sh
## 6.	Follow the instructions on your screen. Watch for informational messages such as the following in case you must complete additional steps: 
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Linux-openvino-install-linux-01.png)
## 7.	If you select the default options, the Installation summary GUI screen looks like this: 
![image]( https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Linux-openvino-install-linux-02.png)

* Optional: You can choose Customize to change the installation directory or the components you want to install: 
![image]( https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Linux-openvino-install-linux-03.png)

When installed as root the default installation directory for the Intel Distribution of OpenVINO is /opt/intel/openvino_<version>/.
For simplicity, a symbolic link to the latest installation is also created: /opt/intel/openvino/.

NOTE: The Intel® Media SDK component is always installed in the */opt/intel/mediasdk* directory regardless of the OpenVINO installation path chosen.
## 8.	A Complete screen indicates that the core components have been installed:
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Linux-openvino-install-linux-04.png)
The first core components are installed. Continue to the next section to install additional dependencies.
# Install External Software Dependencies
NOTE: If you installed the Intel® Distribution of OpenVINO™ to the non-default install directory, replace /opt/intel with the directory in which you installed the software.
These dependencies are required for:
	* Intel-optimized build of OpenCV library
	* Deep Learning Inference Engine
	* Deep Learning Model Optimizer tools
## 1.	Change to the install_dependencies directory:

	cd /opt/intel/openvino/install_dependencies

## 2.	Run a script to download and install the external software dependencies:

	sudo -E ./install_openvino_dependencies.sh

![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Ubuntu_install_4.jpg)
The dependencies are installed. Continue to the next section to set your environment variables.
Set the Environment Variables
You must update several environment variables before you can compile and run OpenVINO™ applications. Run the following script to temporarily set your environment variables:

	source /opt/intel/openvino/bin/setupvars.sh

![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/Ubuntu_install_5.jpg)

Optional: The OpenVINO environment variables are removed when you close the shell. As an option, you can permanently set the environment variables as follows:
## 1.	Open the .bashrc file in <user_directory>:

	vi <user_directory>/.bashrc
	
## 2.	Add this line to the end of the file:

	source /opt/intel/openvino/bin/setupvars.sh
	
## 3.	Save and close the file: press the Esc key and type :wq.
## 4.	To test your change, open a new terminal. You will see [setupvars.sh] OpenVINO environment initialized.
The environment variables are set. Continue to the next section to configure the Model Optimizer.
Configure the Model Optimizer
The Model Optimizer is a Python*-based command line tool for importing trained models from popular deep learning frameworks such as Caffe*, TensorFlow*, Apache MXNet*, ONNX* and Kaldi*.
The Model Optimizer is a key component of the Intel Distribution of OpenVINO toolkit. You cannot perform inference on your trained model without running the model through the Model Optimizer. When you run a pre-trained model through the Model Optimizer, your output is an Intermediate Representation (IR) of the network. The Intermediate Representation is a pair of files that describe the whole model:
* .xml: Describes the network topology
* .bin: Contains the weights and biases binary data
For more information about the Model Optimizer, refer to the Model Optimizer Developer Guide(https://docs.openvinotoolkit.org/latest/_docs_MO_DG_Deep_Learning_Model_Optimizer_DevGuide.html). 
# Model Optimizer Configuration Steps
You can choose to either configure all supported frameworks at once OR configure one framework at a time. Choose the option that best suits your needs. If you see error messages, make sure you installed all dependencies.
NOTE: Since the TensorFlow framework is not officially supported on CentOS*, the Model Optimizer for TensorFlow can't be configured and ran on those systems.
IMPORTANT: The Internet access is required to execute the following steps successfully. If you have access to the Internet through the proxy server only, please make sure that it is configured in your OS environment.
Option 1: Configure all supported frameworks at the same time
## 1.	Go to the Model Optimizer prerequisites directory:
cd /opt/intel/openvino/deployment_tools/model_optimizer/install_prerequisites
## 2.	Run the script to configure the Model Optimizer for Caffe, TensorFlow, MXNet, Kaldi*, and ONNX:
sudo ./install_prerequisites.sh
Option 2: Configure each framework separately
Configure individual frameworks separately ONLY if you did not select Option 1 above.
## 1.	Go to the Model Optimizer prerequisites directory:
cd /opt/intel/openvino/deployment_tools/model_optimizer/install_prerequisites
## 2.	Run the script for your model framework. You can run more than one script:
* For Caffe:
	sudo ./install_prerequisites_caffe.sh
* For TensorFlow:
	sudo ./install_prerequisites_tf.sh
* For MXNet:
	sudo ./install_prerequisites_mxnet.sh
* For ONNX:
	sudo ./install_prerequisites_onnx.sh
* For Kaldi:
	sudo ./install_prerequisites_kaldi.sh
The Model Optimizer is configured for one or more frameworks.
You are ready to compile the samples by running the verification scripts.
