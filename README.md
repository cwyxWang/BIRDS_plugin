# BIRDS_plugin
BIRDS plug-in on Fiji and attached jar package
# Overview

BIRDS（Bi-channel Image Registration and Deep-learning Segmentation for efficient, versatile mapping of mouse brain）is an open source automation pipeline suitable for brain data from different microscopy platforms.
1.	The integration of Fiji platform facilitates the import and export of big data and preprocessing;
2.	High-precision registration of mouse brain data in different modalities with Allen CCFv3;
3.	Interactive platform for visual inspection of registration results and real-time correction;
4.	Mapping the three-dimensional digital framework in Imaris, and cell counting and neuron tracing can be performed under the framework;
5.	Prediction of brain areas of incomplete mouse brain data under the trained neural network.

All Rights Reserved.
# Before installing BIRDS
## Reference
If you use BIRDS in your work please cite our preprint paper:
Bi-channel Image Registration and Deep-learning Segmentation (BIRDS) for efficient, versatile mapping of mouse brain. https://www.biorxiv.org/content/10.1101/2020.06.30.181255v1 <br>
Some of our functions are built on the following tools:<br>
* Allen CCFv3 
* Fiji
* Elastix
* Imaris
* Python
* TensorFlow
* Deeplab v3+

# Acknowledgements
The program was developed by Prof. Peng Fei’s group. Prof. Fei oversaw the project. Weilin Zeng and Xuechun Wang created the basic frameworks for the pipeline, optimized the sub-workflows, implemented the code and integrate them into a complete procedure. The example brain data are from Prof. Yunyun Han’s group.

# 1 Installation and start
## Requirements
BIRDS is written in Java 1.8.0 and Python 3.6.1, and links to Imaris software module. The software runs on the Fiji platform. The deep-learning prediction module requires a Python environment, and the visualization and quantitative analysis are based on Imaris. To run the program smoothly, we recommend a computer workstation running Windows 10 with at least 6 CPU cores, 128Gb of RAM and SSD disks. A configuration with 256GB RAM / 8 CPU cores or above will allow better performance. A good graphic card (e.g., GeForce RTX 2080 Ti) is recommended for implementing efficient computation. In addition, if Imaris is used for 3D digital framework mapping and data analysis, a large-capacity hard drive (e.g., 4Tb or larger) is also required to save the cached data. It should be noted that the output of BIRDS is partially determined by the parameters set, users with different experiences may obtain different results. Therefore, it is recommended to use the default parameters preset in the program. 
## 1.1 Install Fiji
Download link: https://imagej.net/Fiji#Downloads. Please choose any windows version.
## 1.2 Install Python and dependencies (optional)
Setting up a virtual environment is required. It’s recommended to install a Python 3.6. Please download Anaconda for Python 3.6 at: https://www.anaconda.com/. The required dependency packages and recommended versions are:<br>
    TensorFlow-GPU == 1.10.0<br>
    xlwt == 1.3.0<br>
    xlrd == 1.2.0<br>
    xlutils == 2.0.0<br>
    NumPy == 1.18.3<br> 
    LibTIFF == 0.4.2 <br>
    OpenCV == 4.1.0<br>
## 1.3 Install Imaris (optional) 
Version 9.0.0 or above is recommended. https://imaris.oxinst.com/downloads
## 1.4 Local installation
Steps to install BIRDS on a workstation (Windows system):
#### 1.4.1 Download jar packages required for BIRDS plugin:
git clone https://github.com/bleach1by1/BIRDS_plugin <br>
Unzip the downloaded zip file (containing 5 jar packages). Open the Fiji’s folder, copy the birds.jar (from zip file) to the Fiji/plugins folder of Fiji and copy junrar-0.7.jar、ant-1.6.5.jar、poi-3.17.jar、ImarisLib.jar to Fiji/ jars folder
#### 1.4.2 Training the neural network to segment brain regions (optional):
git clone https://github.com/bleach1by1/birds_dl.git <br>
#### 1.4.3 Downloading path of example data:
https://github.com/bleach1by1/BIRDS_demo
## 1.5 Modules and workflow
BIRDS program contains five modules, which are according to different functions of workflow.<br>
Find the BIRDS in the Fiji plugins<br>

![image](https://github.com/bleach1by1/figure_github/blob/master/1.png)<br>

Select main-plugin to run. The GUI is shown in the below picture, with five modules indicated in the red box<br>

![image](https://github.com/bleach1by1/figure_github/blob/master/2.png)<br>

downsample -> image preprocessing <br>
coarse -> registration<br>
precise -> visual inspection and manual correction<br>
visual -> visualization and quantitative analysis<br>
setSeg -> prediction of brain segmentations by neural network<br>








