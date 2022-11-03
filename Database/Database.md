# ASGaze Database Sample
 Detailed descriptions for ASGaze data used in SenSys 2022 paper: "Gaze Tracking on Any Surface with Your Phone".

**Download Link:** <a href="https://www.dropbox.com/s/rojfy4dapjxazmr/Database.zip?dl=0"> Database</a>

# Database Structure

```
|-- raw_data                   
    |-- tracking				  // video frames used for gaze tracking
    	|-- crop                  // cropped eye frames
        |-- frame				  // whole frames
        |-- GroundTruth.txt       // ground truth of gaze points
    |-- corner_1                  // video frames used for mapping
    	|-- crop	              
        |-- frame		         
        |-- GroundTruth.txt       
    |-- corner_2                  // video frames used for mapping
    	|-- crop	              
        |-- frame		         
        |-- GroundTruth.txt 
    |-- corner_3                  // video frames used for mapping
    	|-- crop	              
        |-- frame		         
        |-- GroundTruth.txt 
    |-- corner_4                  // video frames used for mapping
    	|-- crop	              
        |-- frame		         
        |-- GroundTruth.txt 

|-- output                        // checkpoint of saved pre-trained network
  
|-- camera_matrix                 // output of camera calibration
```

Note that: 

We have already put the intermediate results for `Step 1: Detect and crop the eye using Dilb` in `main.ipynb`, like `crop` and `frame` folders.

For privacy, we do not publish the original video (containing user's face).  So when you run this project, you can simply skip the `Step 1: Detect and crop the eye using Dilb` in `main.ipynb` and directly run the following steps.

