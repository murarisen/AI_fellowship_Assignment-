# AI_fellowship_Assignment


Overview
The project aims to develop a robust 3D segmentation model for medical imaging, specifically CT scans of the abdomen. The objective is to accurately segment critical organs: the liver, both kidneys, and the spleen. This segmentation aids in various medical applications, Setup Instructions

To set up the environment and run the code, follow these steps:

Environment Setup:

Install Python 3.8 or higher.

Create a virtual environment:

python -m venv venv
Activate the virtual environment:
bash
Copy code
source venv/bin/activate  # On Unix/macOS
venv\Scripts\activate  # On Windows
Install required packages:

or

use google colab 




Data Preparation:

Download the CT scan dataset from a public repository 
load to google drive 

Running the Code:

mount the google drive 
unzip the files 
open a new notebook and design the model 

Input Layer: Accepts a 3D volume of the CT scan.

Encoder and Decoder: Features multiple layers of 3D convolutions with batch normalization and ReLU activation, followed by max pooling for down-sampling in the encoder, and up-sampling layers in the decoder.

Skip Connections: Similar to U-Net, skip connections are employed between corresponding layers in the encoder and decoder to help recover spatial information lost during down-sampling.
Output Layer: A convolutional layer that maps the feature maps to the desired number of classes (organs).
Training Process

The training of the VNet model involves several key steps:

Data Preprocessing:

Rescale the intensity values of CT images to the range [0, 1].
Normalize the scans based on the mean and standard deviation of the pixel values.

colab gone out of memory so use 128 x128 size 

Use a batch size of 4 due to memory constraints of 3D data.
Employ the Adam optimizer with an initial learning rate of 0.001.

Train the model for 20 epochs

Validation and Inference




Validation: Use a separate validation set to evaluate the model during training. Calculate the accuracy or Dice score for each organ to assess segmentation quality.
Inference: For new CT scans, preprocess the data as during training, then forward it through the trained model to obtain segmentation maps.


To demonstrate the 3D rendered segments of the predicted organs, run each slice separately 
https://github.com/user-attachments/assets/1bf562fe-33b2-443d-b02c-e84c634e9601



