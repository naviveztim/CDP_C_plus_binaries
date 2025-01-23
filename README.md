##  C++ implementation of CDP (Concatenated Decisions Path) algorithm - fast and accurate algorithm for time series classification 

<span style="color:red">**Note:** This version of CDP algorithm does not allow more than 10 classifiers!
For full source code and non restricted version please visit cdp-project.com or e-mail at cdp_project@outlook.com</span>

This is a demo project for producing time series classification models.   
It takes the training datasets as CSV file and produces fully working model in binary format (.bin), as well shows accuracy, if test dataset is provided.  
Running binaries with no parameters will show available command line options.  
Available command line options are: train dataset, test dataset, number of decision trees, normalization, compression, among others. 
This is fully working code, although the number of allowed decision trees is limited to 10!  
In order to achieve good accuracy the number of decision trees may vary from 50 up to 1000, depending on time series set (as shown in the table below).  
To obtain unrestricted version of this project or the source code, please contact the author at: cdp_project@outlook.com. 

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

### Donate
If you like this project, consider supporting me by donating.

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=E7U5FRCCUVNL6)

### Results

Table 1. Training time and accuracy of **C++ implementation**. Results produced on: CPU: Intel-i7 @ 2.6GHz, RAM: 32GB, OS: Windows 11. Datasets taken from [UCR](https://www.cs.ucr.edu/~eamonn/time_series_data_2018/) 

| UCR Dataset  | Num. classes | Num. train samples | Num. test samples | Training time, [sec] | Accuracy, [%] | compress_factor | num_classifiers | normalize | 
|--------------|--------------|--------------------|-------------------|----------------------|---------------|-----------------|-----------------|-----------|
|   ADAC       |       37     |         390        |        391        |        12.7          |    76.5%      |        2        |    1000         |  false    |
| Italy pd     |        2     |          67        |       1029        |         1.6          |    96.2%      |        2        |     500         |  false    |
| MixedSRT     |        5     |        2425        |       1024        |        51.7          |    94.1%      |        4        |     500         |   true    |
| Coffee       |        2     |          28        |         28        |         0.5          |    96.4%      |        4        |     100         |   true    |



### Usage
- Windows: 
	- Make sure that both files: **cdp_application.exe**, **cdp_method.dll** are in the same folder
	- Run: 
	```sh
	cdp_application -train <path_to_train_file> -test <path_to_test_file> -delimiter <delimiter_string> -compress_factor <number_of_samples_to_average> -num_classifiers <number_of_shapelets_classifiers> -normalize <true/false>
	```

- Linux: 
	- Make sure that both files: **cdp_application_u**, **libcdp_methodlib.so** are in the same folder
	- Type: "export LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH 
    - Run: 
	```sh
	cdp_application_u -train <path_to_train_file> -test <path_to_test_file> -delimiter <delimiter_string> -compress_factor <number_of_samples_to_average> -num_classifiers <number_of_shapelets_classifiers> -normalize <true/false>
	```
### How to build my executable, based on CDP core library?
cdp_project@outlook.com

### Source code questions and inquiries: 
cdp_project@outlook.com

### References: 

�Concatenated Decision Paths Classification for Datasets with Small Number of Class Labels�, Ivan Mitzev and N.H. Younan, ICPRAM, Porto, Portugal, 24-26 February 2017

�Concatenated Decision Paths Classification for Time Series Shapelets�, Ivan Mitzev and N.H. Younan, International journal for Instrumentation and Control Systems (IJICS), Vol. 6, No. 1, January 2016

�Combined Classifiers for Time Series Shapelets�, Ivan Mitzev and N.H. Younan, CS & IT-CSCP 2016 pp. 173�182, Zurich, Switzerland, January 2016

�Time Series Shapelets: Training Time Improvement Based on Particle Swarm Optimization�, Ivan Mitzev and N.H. Younan, IJMLC 2015 Vol. 5(4): 283-287 ISSN: 2010-3700


