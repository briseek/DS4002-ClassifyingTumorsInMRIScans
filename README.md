# Classifying Tumors In MRI Scans

## Repository Contents
This repository contains all of the necessary files and scripts for classifying 3 types of tumors from 3064 MRI scans. The analysis aims to determine whether different modeling techniques, CNN and SVM , can result in a highly accurate classification.

## 1. Software and Platform

### Programming Languages and Software
- **MATLAB**: For converting the .mat files into .jpg images for analysis.
- **Python**: For running the machine learning models with the .jpg images. 

### Python Packages
- `tensorflow` – building the CNN model
- `keras` – calling specific functions to modify the layers and build CNN model
- `sklearn` – splitting the data into training and testing, building the SVM model
- `tqdm` – loading in the image data
- `cv2` – loading in the image data
- `os` – loading in the image data from a specific file path
- `io` – loading in the image data
- `pandas` – cleaning the image data labels and predicted values
- `numpy` – cleaning the image data labels and predicted values
- `seaborn` – used to visualize the data for the exploratory data analysis
- `matplotlib` – used to visualize the data for the exploratory data analysis and measuring performance metrics
- `random` – randomize which rows are selected when balancing the data set

### Platform Compatibility
Developed and tested on Mac, but should work on Windows and Linux with appropriate installations.

## 2. Project Folder Structure

```
📂 DS4002-ClassifyingTumorsInMRIScans
 ├── 📂 DATA/  
 ├──── 📂 INITIAL/
 │   │   ├── MAT Images 
 ├──── 📂 FINAL/
 │   │   ├── JPG Images
 │   │ MRI Scans Data Appendix.pdf
 │  
 ├── 📂OUTPUT/
 │   ├── ResNet50 CNN model heatmap.png
 │   ├── ResNet50 CNN model performance.png
 │   ├── SVM model heatmap.png
 │   ├── SVM model performance.png
 │   ├── VGG16 CNN model heatmap.png
 │   ├── VGG16 CNN model performance.png
 │   ├── VGG19 CNN model heatmap.png
 │   ├── VGG19 CNN model performance.png
 │   ├── brain_tumor_example.png
 │   ├── dist_brain_tumors.png
 │
 ├── 📂 SCRIPTS/  
 │   ├── 01_MATLAB_mat_to_jpg_conversion.m
 │   ├── 02_brain_tumor_classification.ipynb
 │  
 ├── LICENSE
 ├── README.md   

```


## 3. Instructions for Reproducing Results

### Stage 1: Image Conversion in MATLAB
- Before you start, it is recommended that you make two subfolders in your  `data/` directory called `MAT Images` and `JPG Images` (or some variant of these names) for easier data handling.
- Download the Brain Tumor Data Set from the [Figshare website](https://figshare.com/articles/dataset/brain_tumor_dataset/1512427).
- Extract the image .zip files and place them in your `data/MAT Images` directory. These files will typically be named ‘brainTumorDataPublic_1-766-[date downloaded].zip’ (where 1-766 represents the image numbers; in total, there will be 4 folders and 3064 images in total after extraction). 
- Run `01_MATLAB_mat_to_jpg_conversion.m` in MATLAB to do the following:
  - Locate the ‘input_folder’ variable (located in line 15) and replace the '**your input folder here**' with the filepath of your downloaded folder. This will be one of the four folders in the `data/MAT Images`.  
  - On the following line (line 16), find the ‘output_folder’ variable and replace the '**your output folder here**’ with the filepath of your .jpg images, called `data/JPG Images` in this case.
  - Run this code three more times, each time replacing the ‘input_folder’ variable with the filepath of the next folder in your `data/MAT Images` directory. 
- By the end of this process, your `JPG Images` folder should contain three subfolders: ‘1,’ ‘2,’ and ‘3.’ This is because the code classifies the images into the three tumors: ‘1’ corresponds to the meningioma tumor, ‘2’ corresponds to the glioma tumor, and ‘3’ corresponds to the pituitary tumor. 
- Rename the numbered folders to the corresponding tumors so that the Python analysis in the next step runs smoothly. 

### Stage 2: Exploratory Data Analysis
- Open up JupyterLab to run `02_brain_tumor_classification.ipynb`
- You may need to use the following commands in the JupyterLab Terminal to install the appropriate packages (if you don’t have them already):
  ```pycon
  pip install tensorflow
  pip install keras
  pip install sklearn
  python -m pip install opencv-python
  pip install tqdm
  pip install os
  pip install io
  pip install pandas
  pip install numpy
  pip install seaborn
  pip install matplotlib
  pip install random
  ```
- Import .jpg data from wherever you have this saved.
- Run the code file to obtain the following graphs:
  - Distribution of Brain Tumors
  - Distribution of Types of Brain Tumors
- Use Google Slides to annotate the graphs

- Using `02_brain_tumor_classification.ipynb`, run the remaining code chunks after conducting the exploratory data analysis
  - Balance the data in order to have accurate prediction
  - Split the data into training and testing
  - Use the training data set to build the 3 different CNN models and perform cross validation to find the best SVM model
  - Use the testing data set in order to assess the performance of the 4 models
- Run the code file to obtain the relevant figures.
  - **Heatmaps** (contains heatmaps of the 4 models predicted and theoretical values)
  - **Performance Metrics** (contains tables of different performance metrics like recall, precision, accuracy, etc.)
