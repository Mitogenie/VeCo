# VeCo

[![N|Solid](https://raw.githubusercontent.com/Mitogenie/VeCo/main/misc/lab-logo.png)](https://mic.med.virginia.edu/kashatus/)

## Vessel Co-option Analyzer
![N|Solid](https://raw.githubusercontent.com/Mitogenie/VeCo/main/misc/veco-version.png)

#### VeCo is a tool to enable high-throughput analysis of vessel co-option in brain.

##### User Interface
VeCo offers interactive, semi graphical user interface through Jupyter notebooks.

##### Software Requirements
Follow these instructions if you do not have Anaconda or Jupyter notebooks installed on your computer.
</br>
  - VeCo is developed in Jupyter notebooks using Python 3. Since it benefits from a wide range of Python libraries, along with Jupyter notebooks, we suggest installing Anaconda distribution of Python (V 3.7). --> [Download Anaconda](https://www.anaconda.com/distribution/)

If you do not already have OpenCV installed on your computer (which is likely), You may follow the rest of the instructions.
  - While Anaconda installation takes care of most of the library requirements for VeCo, there is only one more libary (OpenCV) that needs to be installed, which can be achieved through the command line. (You just need to copy and run the following command. (without the $))
    - Windows: Use Anaconda Prompt.
    - MacOS, Linux: Use Terminal.
```sh
$ pip install opencv-python==3.4.2.17
```
  - It is important to install this specific version of OpenCV for compatibility. If you receive a message that this version is not availbale, you may install the following version.
 ```sh
$ pip install opencv-python==3.4.10.37
```
  - Jupyter file is your interface with for VeCo (The file you have to run), which depends on depend on VeCo.py to run. This module includes all the functions used in the develepment of veco, and should be in the same folder as the jupyter notebook you are running.

### Where to start your analysis?
##### 1) Download the files on your computer
Once you have satistfied the requirements, you can start your analysis by downloading or cloning this repository on your computer. The simplest way is to download the whole directory by pressing the green button (top right) and download the ZIP file.

##### 2) Follow the step-by-step instructions in the tool you are using

### More on Mito Hacker Tools

#### Cell Catcher

###### What to know before use
- Input: 
    - Independent images of stained vessels and tumor 
    
- Output: 2 csv files containing vessel measurements
    - main output:
    - aggregated output: 

###### Instructions
- Run VeCo.ipynb using Jupyter notebook.
    - You may find this video on Jupyter notebooks very helpful: [Watch Here](https://youtu.be/HW29067qVWk)
        - Note: We are not affiliated with the owner of the above video. We just found this video on Jupyter notebooks very helpful, There are plenty of great tutorials about this subject, and you may use any source your prefer.
- The Jupyter notebook file provides the users with step-by-step instructions to analyze their data.

###### Development
- 15+ images were used to develop and test VeCo.

##### Processing
In the current version, VeCo uses CPU for processing the images. There is no GPU version of VeCo.

### Nomenclature of Features

What does each measured feature mean?

#### Main output: Vessel Level Measurements
##### Length, width, angle
- Measure of the vessel length, width, and angle of the vessel (w.r.t )
##### Vessel Center X & Y
- The position of the vessel center on the image w.r.t. tumor center.
##### Distance
- Distance of the vessel center from tumor center
##### Zone
- The Zone where the vessel is located (Tumor, Control, Residual)

#### Aggregated output: Aggregated Measurements

##### Tile Number
- The number of the tile. Each images has 100 tiles. The sliding tiles start from the top-left corner of the image, and sweeps the images to right and button. This information helps you to have a ballpark estimate of measuremnets across your image.
- Each Zone will have 100 tiles. However, the tiles with no overlap with the defined zone by the user will have a zero count.
  - Tile measurements for each zone only reflect the measurements for that zone. For instance, if a particular tile covers regions from control and residual. The respective tile/zone row only reflects the measurement for that zone over that particular tile.

##### Vessel_count
- The number of vessels in the tile

##### Cell count_in_tile
- The total number of cells in the tile

##### Co_opted_cell_count_in_tile
- The number of co-opted cells in the tile

##### Non_co_opted_cell_count_in_tile
- The number of non co-opted cells in the tile

##### Co_opted_to_NonCo_opted_Ratio
- The the ratio of co-opted to non-co-opted cells in the tile

##### Co_opted_to_total_Ratio
- The the ratio of co-opted to total number of cells in the tile

##### Zone
- It enbales your to further aggregate tiles data based on zone for further analysis 


### List of the libraries we used for development (A/Z)
- copy
- cv2
- ipywidgets
- matplotlib.pyplot
- numpy
- os
- pandas
- random
- scipy
- shutil
- skimage

### A note on imaging

Images should be acquired at ....

