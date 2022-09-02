
# Rubhus-Cross-Langauge-Code-Clone-Detector

This repository contains the source code for the paper - "Improving Cross-Language Code CloneDetection via Code Representation Learning and Graph Neural Networks"

## 📜 Code Organisation 
Current organisation contains files pertaining to models (`rubhusModel.py`), trainers (` trainerRubhus.py`) and some helper function file.  

    Repository
    ├── helper functions
    ├── models
    └── trainers
   
After setting up the repository, it would contain dataset files as well.

## ⚙ Setting Up 

### 1. Download the repo

### 2. Installing Dependencies

       pip install -r requirements.txt

Note - Pytorch and Pytorch-Geometric (+ associated dependencies) versions must be installed in accordance the compatablity of Cuda version and operating system 

### 3. Setting up Datasets
The datasets which were used for experiments couldn't be uploaded to the repository due to file size limits. These files are to be downloaded and can be used independently for testing/running the models.

#### 3.1 Extraction of Dataset Files
- Java-Python Dataset - [Link](https://drive.google.com/file/d/1pOkkNpc9lmMXME8mCUYJRjl_-5GJzB6f/view?usp=sharing)  
- C-Java Dataset - [Link](https://drive.google.com/file/d/1pOkkNpc9lmMXME8mCUYJRjl_-5GJzB6f/view?usp=sharing)

#### 3.2 Setting up Dataset Files
- Unzip the downloaded files and extract the datasets files.
- Place these extracted files in the root directory of this repository

#### 3.3 Configuration of file paths
- **Dataset paths** - After extraction of the dataset, clone pair files and non-clone pair text files must be stored in the root directory in a folder named 'CloneDetectionSrc'. 
- **Processed Data folder** - A folder named 'cloneDetectionData' must be created  in the root directory where all the processed data files will be stored for training the model
- **Trained Models folder** - A folder named 'cloneDetectionModels' must be created  in the root directory where all the formed model files will be stored.


## 💫 Usage 

### 1. Configuration of Hyperparameters

- Hyperparameters are defined inside the trainer files and can modified as per convenience. 

The hyperparameter variables explanation table is as follows : 
 
|  Var Name |  Hyperparameter | Default Value  |
|--|--|--|
| dim  | Embedding size (dimension) for the model | 64 |
| epochs | #Epochs for the training  | 25 |
| batch_size | Size of the data batch | 32 |
| lamda | Regulariser  | 0.001 |
| use_unsup_loss | Usage of unsupervised loss in model training  | True |
| lr | Learning Rate (initial)  | 0.001 |
| optimizer | Optimizer of loss  | Adam |
| scheduler | Learning Rate Scheduler | ReduceLROnPlateau |

### 2. Training RUBHUS Model
       python3 trainerRubhus.py



## ⭐ About the original setup 
- In our experiments we have trained Rubhus for Java Python Dataset and for C-Java Dataset separately. 
- The hyperparameters used in the original experiments as well as in this source code are reported in the paper.
- We have used GTx 2080Ti GPU to run our experiments. The time analysis of the tool also has been reported in the paper.


