# ASGaze
This is the repo for SenSys 2022 paper: "Gaze Tracking on Any Surface with Your Phone" and TMC 24 paper: "Practical Gaze Tracking on Any Surface with Your Phone".

**Project website:** <a href="https://asgaze.github.io/"> ASGaze</a>

**Demo video:**

<div align="center">       
    <a href="https://youtu.be/_4NIigLkK0k">      
        <img src="http://img.youtube.com/vi/_4NIigLkK0k/0.jpg"        
             alt="Everything Is AWESOME"        
             style="width:50%;">       
    </a>     
</div>

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
@inproceedings{cao2022gaze,
title={Gaze Tracking on Any Surface with Your Phone},
author={Cao, Jiani and Lin, Chengdong and Liu, Yang and Li, Zhenjiang},
booktitle={Proceedings of the 20th ACM Conference on Embedded Networked Sensor Systems},
pages={320--333},
year={2022}
}
```
```
@article{cao2024practical,
  title={Practical Gaze Tracking on Any Surface with Your Phone},
  author={Cao, Jiani and Chen, Jiesong and Lin, Chengdong and Liu, Yang and Wang, Kun and Li, Zhenjiang},
  journal={IEEE Transactions on Mobile Computing},
  year={2024},
  publisher={IEEE}
}
```

  ---

# License

You may use this source code for academic and research purposes. Commercial use is strictly prohibited.
