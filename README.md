### Text to image conversion
This is the implementation for the research paper [**StackGAN: Text to Photo-realistic Image Synthesis with Stacked Generative Adversarial Networks**](https://arxiv.org/pdf/1612.03242.pdf).   

#### Dependencies
- python 3.6
- TensorFlow 1.7
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
- [Download](https://drive.google.com/file/d/0B3y_msrWZaXLT1BZdVdycDY5TEE/view?resourcekey=0-sZrhftoEfdvHq6MweAeCjA) our preprocessed text embeddings. Extract them to **Data/birds**.

- Type the following command to preprocess the images: 

  `python misc/preprocess_birds.py`

#### Training
To train a StackGAN model on the CUB dataset using our preprocessed data type the following command.

train Stage-II GAN 

`python stageII/run_exp.py --cfg stageII/cfg/birds.yml --gpu 1`

#### Run
Type the following command to generate bird samples from sentences.: 

`python demo/birds_skip_thought_demo.py --cfg demo/cfg/birds-skip-thought-demo.yml --gpu 2`  

The results will be saved to **Data/birds/example_captions-skip-thought/**. 




