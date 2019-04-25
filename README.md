# PIV dataset for neural network training

## License and citation

The dataset in this repository is used to train a neural network performing **dense** particle image velocimetry. It is provided for research purposes only. All rights reserved. Any commercial use requires our consent. If you use this dataset in your research work, please cite the following paper:

[Dense motion estimation of particle images via a convolutional neural network, Exp Fluids, 2019](https://doi.org/10.1007/s00348-019-2717-2)


	@article{cai2019dense,
	  title={Dense motion estimation of particle images via a convolutional neural network},
	  author={Cai, Shengze and Zhou, Shichao and Xu, Chao and Gao, Qi},
	  journal={Experiments in Fluids},
	  volume={60},
	  number={4},
	  pages={73},
	  year={2019},
	  publisher={Springer}
	}


## Data description

Each data item contains a particle image pair (input for CNN) and the corresponding ground-truth motion field (output). For example:

	\PIV-genImages\data\uniform\uniform_00001_img1.tif
	\PIV-genImages\data\uniform\uniform_00001_img2.tif
	\PIV-genImages\data\uniform\uniform_00001_flow.flo

A train-validation split is also provided:

	FlowData_train.list
	FlowData_test.list


## Generating particle images

The intensity for each particle of the synthetic images is satisfied to a Gaussian function:

<div align=left><img width="250" src="https://github.com/shengzesnail/PIV_dataset/raw/master/demos/Gaussian_fun.PNG"/></div>  
where $I_{0}$ is the peak intensity in the Gaussian center, $d_p$ denotes the particle diameter and $(x_0,y_0)$ the position of the particle. Let $\rho$ be the particle seeding density of the image. Each parameter is randomly selected in a proper range:


|Parameter       |Range                       | Unit                        |
|----------------|----------------------------|-----------------------------|
|Seeding density $\rho$  |  0.05 - 0.1         |particle per pixel           |
| Particle diameter $d_p$ | 1-4               |pixel                        |
|Peak intensity   $I_{0}$| 200-255            |grey value                   |
|Location $(x_0,y_0)$| 1-256                  |pixel                        |


All the images are in a resolution of 256 * 256 pixel. 
**Here are some images with different parameters：**
**a)** seeding density $\rho$ = 0.078 ppp, particle diameter $d_p$ = 1.31 pixel, **b)** $\rho$ = 0.051 ppp, $d_p$ = 3.68 pixel, **c)** $\rho$ = 0.069 ppp, $d_p$ = 2.81 pixel.

<div align=left><img width="500" src="https://github.com/shengzesnail/PIV_dataset/raw/master/demos/particle_images.PNG"/></div>



## Flow motions

The dataset includes a variety of flow motions to increase the data diversity. Some simple cases are simulated by using computational fluid dynamics (CFD). Also, there are some flow fields available online, such as [2D DNS turbulent flow](http://fluid.irisa.fr/data-eng.htm), sea flow driven by [surface quasi-geographic model](http://vressegu.github.io/sqgmu/) and various flow patterns provides by [Johns Hopkins Turbulence Databases](http://turbulence.pha.jhu.edu/).

The descriptions of the motion fields for PIV neural network training are presented below:

<div align=left><img width="450" src="https://github.com/shengzesnail/PIV_dataset/raw/master/demos/dataset.PNG"/></div>  

<br> 

**Here are some samples of flow motion we used in the PIV dataset:** 
<div align=left><img width="600" src="https://github.com/shengzesnail/PIV_dataset/raw/master/demos/CFD_motions.PNG"/></div>


## Others

You can also download the data from Baidu Cloud:   
>URL: [https://pan.baidu.com/s/1GVVENe3NN0h2QKbiqS3cJA](https://pan.baidu.com/s/1GVVENe3NN0h2QKbiqS3cJA)   
>Key code: fljs 


