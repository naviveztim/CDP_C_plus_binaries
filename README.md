##  C++ implementation of CDP (Concatenated Decisions Path) algorithm - fast and accurate algorithm for time series classification 

### Overview 
 CDP is a novel method for time-series classification using shapelets. The approach focuses on overcoming the limitations of traditional 
 shapelet-based methods, primarily their slow training times, while maintaining high accuracy. Proposed algorithm 
 involves training small decision trees and combining their decisions to form unique patterns for identifying time-series 
 data. Method is tested on dataset from [UCR](https://www.cs.ucr.edu/~eamonn/time_series_data_2018/))

### Why C++ implementation?
- Very short training and inference times  
- Very compact (KB) code and executables  
- Very small (KB) models 
- Very low memory and CPU usage 

### Results

Table 1. Training time and accuracy of **C++ implementation**. Results produced on: CPU: Intel-i7 @ 2.6GHz, RAM: 32GB, OS: Windows 11 

| UCR Dataset  | Num. classes | Num. train samples | Num. test samples | Training time, [sec] | Accuracy, [%] | Compression rate | Num. decision trees | Normalize | 
|--------------|--------------|--------------------|-------------------|----------------------|---------------|------------------|---------------------|-----------|
|   ADAC       |       37     |         390        |        391        |        12.7          |    76.5%      |        2         |    1000             |    No     |
| Italy pd     |        2     |          67        |       1029        |         1.6          |    96.2%      |        2         |     500             |    No     |
| MixedSRT     |        5     |        2425        |       1024        |        51.7          |    94.1%      |        4         |     500             |   Yes     |
|              |              |                    |                   |                      |               |                  |                     |           |
|              |              |                    |                   |                      |               |                  |                     |           |
|              |              |                    |                   |                      |               |                  |                     |           |

### Usage
- Windows: 
    Run: **cdp_application.exe** -train <path_to_train_file> -test <path_to_test_file> -delimiter <delimiter__string> -compress_factor <number_of_samples_to_average> -num_classifiers <number_of_shapelets_classifiers> -normalize <true/false>
	Where: 
	* * -train - path to txt train file path in format: Requires qutes. Ex. "C:\folder 1\foleer 2\train_file.txt"  
	* -test - path to txt test file path in format: Requires qutes. Ex. "C:\folder 1\foleer 2\test_file.txt"
	* -delimiter - delimiter used in txt or csv file 
	* -compress_factor - applies averaging of input signal of every k samples
	* -num_classifiers - number of decision trees. Principally, increased number leads better accuarcy. 
	* -normalize true/false - apply z-score normalization to the train/test signals 

- Linux: 
  * Make sure that both files: cdp_application_u, libcdp_methodlib.so are in the same folder
  * Type: "export LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH"
  * Run: **cdp_application_u** -train <path_to_train_file> -test <path_to_test_file> -delimiter <delimiter__string> -compress_factor <number_of_samples_to_average> -num_classifiers <number_of_shapelets_classifiers> -normalize <true/false>
  

### How to build my own executable, based on CDP core library?
Send request to cdp_project@outlook.com

### C++ source code questions and inquiries: 
Send request to cdp_project@outlook.com

### References: 

“Concatenated Decision Paths Classification for Datasets with Small Number of Class Labels”, Ivan Mitzev and N.H. Younan, ICPRAM, Porto, Portugal, 24-26 February 2017

“Concatenated Decision Paths Classification for Time Series Shapelets”, Ivan Mitzev and N.H. Younan, International journal for Instrumentation and Control Systems (IJICS), Vol. 6, No. 1, January 2016

“Combined Classifiers for Time Series Shapelets”, Ivan Mitzev and N.H. Younan, CS & IT-CSCP 2016 pp. 173–182, Zurich, Switzerland, January 2016

“Time Series Shapelets: Training Time Improvement Based on Particle Swarm Optimization”, Ivan Mitzev and N.H. Younan, IJMLC 2015 Vol. 5(4): 283-287 ISSN: 2010-3700


