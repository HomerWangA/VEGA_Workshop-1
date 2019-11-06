## Install Intel OpenVINO on Windows 10 LTSC 2019
Date	2019/09/23

### Step 1: Download all of the Installation Packages
- [OpenVINO Toolkit R2.0.1 (19 Aug 2019)](https://software.intel.com/en-us/openvino-toolkit/choose-download/free-download-windows)
- [Visual Studio 2019 Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16)
- [MS Build Tool 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)
- [Cmake 3.14.6 win64-x64](https://www.python.org/ftp/python/3.6.5/python-3.6.5-amd64.exe)
- [Python 3.6.5 amd64](https://www.python.org/ftp/python/3.6.5/python-3.6.5-amd64.exe)
- [(Optional for GPU) Intel Graphic 21.20.15.65 or higher](https://downloadcenter.intel.com/product/80939/Graphics-Drivers?elq_cid=5783180)

### Step 2: Install Visual Studio 2019 Community
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_1.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_2.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_3.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_4.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_5.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_6.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_7.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_8.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_9.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_10.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_11.png)

### Step 3: Install MS Build Tool 2019
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_12.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_13.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_14.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_15.png)

### Step 4: Install Cmake 3.14.6 win64-x64
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_16.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_17.png) 
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_18.png)

### Step 5: Install Python 3.6.5 64-bit
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_19.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_20.png)

### Step 6: Install OpenVINO Toolkit R2.0.1
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_21.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_22.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_23.png)

### Step 7: Configure OpenVINO Environment System Variables (Important)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_24.png)
![image](https://github.com/ADVANTECH-EIoT/VEGA_Workshop/blob/master/photos/windows_25.png)

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



