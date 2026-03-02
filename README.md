Oxford-IIIT Pet Segmentation: U-Net vs. FCNThis repository contains a comparative study of two deep learning architectures for Semantic Segmentation using the Oxford-IIIT Pet Dataset. 
The goal is to perform pixel-level classification into three categories: Pet, Background, and Outline (Trimap).
🚀 How to Run1.
Prerequisites
You will need a Google Colab account or a local environment with a GPU (NVIDIA T4 or better recommended).
2. Environment SetupInstall the necessary libraries if they aren't already available:Bashpip install torch torchvision numpy matplotlib pillow
3. Execution StepsOpen the .ipynb notebook in Google Colab.
Enable GPU: Go to Edit > Notebook settings > Hardware accelerator > Select T4 GPU.
Run the cells in order:
Step 1: Downloads the dataset directly from PyTorch.
Step 2: Defines the custom U-Net architecture.
Step 3: Sets up the FCN-ResNet50 model.
Step 4: Runs the training loop (set to 2-3 epochs for a quick demonstration).
Step 5: Visualizes the results.
🏗️ Model Architectures
Custom U-Net (Built from Scratch)
A symmetric encoder-decoder network
.Encoder: Extracts features using convolutional layers and Max Pooling.
Decoder: Upsamples features using Transposed Convolutions.
Skip Connections: Concatenates high-resolution features from the encoder to the decoder to preserve sharp object boundaries.
FCN-ResNet50 (Baseline)A Fully Convolutional Network using a ResNet-50 backbone.
This model utilizes transfer learning principles to achieve high accuracy quickly.
📊 Results & Analysis
ModelInitializationPerformance Observation
FCN-ResNet50Pre-trained
Highly accurate; clean and solid masks.
U-NetRandom (Scratch)Fragmented masks; requires more training epochs to converge.
