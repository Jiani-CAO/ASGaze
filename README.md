# ASGaze
 This is the repo for SenSys 2022 paper: "Gaze Tracking on Any Surface with Your Phone" 

**Project website:** <a href="https://asgaze.github.io/"> ASGaze</a>

**Demo video:**

<div align="center">       <a href="https://youtu.be/_4NIigLkK0k">      <img        src="https://i9.ytimg.com/vi_webp/_4NIigLkK0k/mq1.webp?sqp=COjahJsG-oaymwEmCMACELQB8quKqQMa8AEB-AH-BYAC0AWKAgwIABABGHIgSSg-MA8=&rs=AOn4CLDR7V-P7jfUIfWzALOmzvx3zaJLLQ"        alt="Everything Is AWESOME"        style="width:50%;">       </a>     </div>

<br>

# Requirements

The program has been tested in the following environment: 

* Python 3.7
* Numpy 1.21.4
* Pytorch 1.10.3
* torchvision 0.11.1
* opencv-python 3.4.2.17
* dlib  19.17
  <br>


# Project Structure

```
|-- iris_boundary_detector                   
    |-- data_sources					  
    	|-- detection.ipynb               // detect and save eye regions using dlib library	
        |-- cvdata						  // facial landmarks used in "detection.ipynb"
        |-- ASGaze_data.ipynb             // Pytorch Dataset prepared for train and inference
        |-- transform.ipynb	              // data augmentation
    |-- graph		
        |-- vgg_unet.ipynb                // backbone of segmentation network
    	|-- losses.ipynb                  // loss functions used to train segmentation network
    |-- utils
    	|-- load_model.ipynb	          // helper functions used to load and save model
        |-- metrics.ipynb		          // metrics used to evaluate segmentation network
        |-- refinement.ipynb              // leverage temporal relationship to refine iris boundary
    |-- configs
    	|-- segmentation_train.json	      // config parameters for training network
    	|-- gaze_inference.json           // config parameters for output inferenced iris boundary
    |-- train.ipynb	                      // main workflow of train
    |-- inference.ipynb	                  // main workflow of inference

|-- gaze_ray_estimator    
    |-- cone_model.ipynb                  // cone model used to establish the relationship between 3D circle and 2D ellipse
    |-- estimator.ipynb                   // main workflow of gaze ray estimator
  
|-- mapping    
    |-- mapping_principle.ipynb           // mapping principle
    |-- shape_constrained.ipynb           // proposed mapping method

|-- Database                              // conclude data sample, pretrained model and camera matrix

|-- setup.ipynb                           // remove ambiguity and calculate offsets (one-time effort)

|-- main.ipynb                            // main workflow of ASGaze
```

<br>

# Quick Start

* Download and unzip the `Database` folders. Detailed descriptions are in [Database.md](https://github.com/Jiani-CAO/ASGaze/blob/main/Database/Database.md).

* Change the "dir", "runs_dir" of data and pretrained model in `gaze_inference.json` to the path on your machine.

* Run the `main.ipynb` script and you can visualize the tracking process, just like the demo video.

  ---

# Citation

If you find our work useful in your research, please consider citing:

```
Coming soon…
```
