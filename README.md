# FISCAS
## Fluorescence Integrated Single-Cell Analysis Script
***
### Introduction

This python based program can be used to combine MALDI imaging data with microscope images to: 
1. overlay maldi images with microscope images 
2. perform a cell segmentation (based on Cellprofiler)
3. calculate single cell mass spectra based on the previous 2 steps

### Installation and Prerequesites 

The installation can be a bit tricky due to dependency conflicts of different packages.

1) Python

The first thing you need is a clean installation of Python 3.8.10. Other versions might work as well but this is the one it was successfully tested on while many newer versions failed. This will be true for all the versions mentioned in the following. To circumvent dependency conflicts it is recommended to use a virtual environment for all of the following installations. If you don't know how to do that you can find help under this link: https://docs.python.org/3/library/venv.html.
If you have set up your environment and activated it, install numpy `pip install numpy`

2) Cellprofiler

Then you can start installing CellProfiler (Version 4.2.1). You can find detailed instructions for that under https://github.com/CellProfiler/CellProfiler/wiki/Source-installation-%28Windows%29. For version 4.2.1 you can skip the step in which you clone the github directory and replace `pip install -e .` with `pip install cellprofiler==4.2.1`

3) Cellpose and Stardist

Then you need to install Cellpose and Stardist. Simply run `pip install cellpose==2.1.1` and `pip install stardist==0.8.3`. After that you need to include both of them in your CellProfiler installation. For that you can download the 'runcellpose.py' and 'runstardist.py' skripts from the CellProfiler-plugins Github page (https://github.com/CellProfiler/CellProfiler-plugins) and move both of them into the plugin folder specified by your CellProfiler installation.  

4) Python packages

A complete list with all python packages can be found in the 'requirements.txt' file. 
Here is a list of command you need to run to install all the packages you need:

- `pip install matplotlib`
- `pip install pandas`
- `pip install jupyterlab`
- `pip install ipywidgets`
- `pip install scikit-image`
- `pip install scipy`
- `pip install opencv-python`
- `pip install pil`
- `pip install imageio`
- `pip install seaborn`
- `pip install pyimzml` (if you want to import .imzml)
- `pip install tqdm`
- `pip install tensorflow`

If you want to use the SCiLS import you also need to install the SCiLS API. Instructions for that can be found in the SCiLS Manual.

As stated above the installation can be quite tricky, but this is mainly due to requirements incompatibilities within cellprofiler, cellpose and stardist. 

### Getting Started

The program is implemented in Jupyter-lab.  

"JupyterLab is the latest web-based interactive development environment for notebooks, code, and data. Its flexible interface allows users to configure and arrange workflows in data science, scientific computing, computational journalism, and machine learning." --- jupyter.org

Jupyter-Lab is easy to use even without any programming experience. The interactive environment makes an intuitive workflow possible and minimizes running time while testing different run settings.
It is recommended to run the tutorial first. However due to the nature of the MALDI data, the size of the test-data is rather large. Therefore the data needed for the tutorial is not provided through github, but can be downloaded under this link instead (https://uni-muenster.sciebo.de/s/PAL52iMhSuUaS2W). To set everything up firstly clone the github repo to the destination of your choice. After that download the data folder from the sciebo cloud and move it into the tutorial folder of the github repo. Then you can start with the tutorial by activating your virtual environment and running `jupyter-lab <path-to-jupyter-lab-tutorial.ipynb>` in your command line tool. All the instructions on how to run the tutorial are already included in the notebook (tutorial.ipynb). 