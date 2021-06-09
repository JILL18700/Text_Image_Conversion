### Text to image conversion
This is the implementation for the research paper [**StackGAN: Text to Photo-realistic Image Synthesis with Stacked Generative Adversarial Networks**](https://arxiv.org/pdf/1612.03242.pdf).   

#### Dependencies
- python 2.7
- TensorFlow 0.11
- [skip-thought](https://github.com/ryankiros/skip-thoughts) text-encoder
- pip install the following packages:
 	- prettytensor
 	- progressbar
 	- python-dateutil
 	- easydict
 	- pandas
 	- torchfile

#### Dataset
Download the [birds](http://www.vision.caltech.edu/visipedia/CUB-200-2011.html)  image data. Extract them to **Data/birds/**.

#### Preprocessing 
Type the following command to preprocess the images: 

`python misc/preprocess_birds.py`

#### Training

To train a StackGAN model on the CUB dataset using our preprocessed data type the following command.

Step 1: train Stage-I GAN 

`python stageI/run_exp.py --cfg stageI/cfg/birds.yml --gpu 0`

Step 2: train Stage-II GAN 

`python stageII/run_exp.py --cfg stageII/cfg/birds.yml --gpu 1`

#### Pretrained Model
Download and save the pre-trained models to **models/**.

#### Run
Type the following command to generate bird samples from sentences.: 

`python demo/birds_skip_thought_demo.py --cfg demo/cfg/birds-skip-thought-demo.yml --gpu 2`  

The results will be saved to **Data/birds/example_captions-skip-thought/**. 



