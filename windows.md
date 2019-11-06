## Install Intel OpenVINO on Windows 10 LTSC 2019
Date	2019/09/23

Installation Process
Step1: Download all of the Installation Packages
- OpenVINO Toolkit R2.0.1 (19 Aug 2019)
http://registrationcenter-download.intel.com/akdlm/irc_nas/15790/w_openvino_toolkit_p_2019.2.275.exe
- Visual Studio 2019 Community
https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16
- MS Build Tool 2019
https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16
- Cmake 3.14.6 win64-x64
https://www.python.org/ftp/python/3.6.5/python-3.6.5-amd64.exe
- Python 3.6.5 amd64
https://www.python.org/ftp/python/3.6.5/python-3.6.5-amd64.exe
- (Optional for GPU) Intel Graphic 21.20.15.65 or higher
https://downloadcenter.intel.com/product/80939/Graphics-Drivers?elq_cid=5783180

Step2: Install Visual Studio 2019 Community
 
 
 
 
 
 
 
 
 
 
 
 

Step3: Install MS Build Tool 2019
 
 
 
 
 

Step4: Install Cmake 3.14.6 win64-x64
  
  
  

Step5: Install Python 3.6.5 64-bit
 
  

Step6: Install OpenVINO Toolkit R2.0.1
 
  
  

Step7: Configure OpenVINO Environment System Variables (Important)
 
   

Name |	Value
--- | --- 
INTEL_OPENVINO_DIR | C:\Program Files (x86)\IntelSWTools\openvino
INTEL_CVSDK_DIR | %INTEL_OPENVINO_DIR%	
OpenCV_DIR | %INTEL_OPENVINO_DIR%\opencv\cmake	
OPENVX_FOLDER | %INTEL_OPENVINO_DIR%\openvx
InferenceEngine_DIR | %INTEL_OPENVINO_DIR%\deployment_tools\inference_engine\share	
HDDL_INSTALL_DIR | %INTEL_OPENVINO_DIR%\deployment_tools\inference_engine\external\hddl	
PYTHONPATH | %INTEL_OPENVINO_DIR%\python\python3.6

Edit the Path variable under System Variables and add the following entries:

|Name|Value|
|---|---|
|PATH|%INTEL_OPENVINO_DIR%\deployment_tools\inference_engine\bin\intel64\Release  |
||%INTEL_OPENVINO_DIR%\deployment_tools\inference_engine\bin\intel64\Debug  |
||%HDDL_INSTALL_DIR%\bin 
||%INTEL_OPENVINO_DIR%\opencv\bin  |
||%INTEL_OPENVINO_DIR%\openvx\bin |

Step8: Configure the Model Optimizer for all supported frameworks
 
 
 
Step9: Using administrator role to execute windows command to download some face detection models
*Notice: You can download the entire models, but it might take over 30 minutes
cd C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader
 
python downloader.py --name face-detection-retail-0004,age-gender-recognition-retail-0013,emotions-recognition-retail-0003
 
*Notice: If you meet error message no module named yaml, please enter “pip install pyyaml” to install it

Step10: Compile Inference Engine Sample
cd C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\inference_engine\demos
 
 
 
Step11: Run the interactive_face_detection_demo sample
You can check all of the parameters with -help
 
Step12: with face-detection model
 
CPU	interactive_face_detection_demo.exe -i cam -m "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_detection\face\sqnet1.0modif-ssd\0004\dldt\FP32\face-detection-retail-0004.xml" -d CPU
GPU	interactive_face_detection_demo.exe -i cam -m "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_detection\face\sqnet1.0modif-ssd\0004\dldt\FP32\face-detection-retail-0004.xml" -d GPU
VPU	interactive_face_detection_demo.exe -i cam -m "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_detection\face\sqnet1.0modif-ssd\0004\dldt\FP32\face-detection-retail-0004.xml" -d HDDL
VPU
(NC2)	interactive_face_detection_demo.exe -i cam -m "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_detection\face\sqnet1.0modif-ssd\0004\dldt\FP32\face-detection-retail-0004.xml" -d MYRIAD
*Notice: If you want to use GPU or VPU, Please refer below document to install the driver
https://docs.openvinotoolkit.org/2019_R2/_docs_install_guides_installing_openvino_windows.html#Install-GPU
https://docs.openvinotoolkit.org/2019_R2/_docs_install_guides_installing_openvino_windows.html#hddl-myriad
 
Step13: Execute the interactive_face_detection_demo sample with face-detection model and age-gender
 
interactive_face_detection_demo.exe -i cam -m "C:\Program Files (x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_detection\face\sqnet1.0modif-ssd\0004\dldt\FP32\face-detection-retail-0004.xml" -d CPU -m_ag "C:\Program Files in(x86)\IntelSWTools\openvino\deployment_tools\tools\model_downloader\Retail\object_attributes\age_gender\dldt\FP32\age-gender-recognition-retail-0013.xml" -d_ag CPU


