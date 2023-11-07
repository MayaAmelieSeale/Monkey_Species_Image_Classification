# Monkey_Species_Image_Classification
Classifying Images of Monkeys by Species - CNN and Vision Transformer approaches

## Approaches
1. Pre-trained Convolutional Neural Network
   a. MobileNetv2 - With and without finetuning
   b. EfficientNet - With and without finetuning
3. Vision Transformer


### Pre - trained Convolutional Neural Network
   #### MobileNetv2
   ##### Fine Tuning 
   #### EfficientNet 
   ##### Fine Tuning 

   
A Convolutional Neural Network Approach to 
This approach relied utilized MobileNetV2 as a pre-trained model, which was kept as is in a first attempt and later fine tuned. In addition, using a threshold ReLU function as an activation function, with a theta vaue of .1 or .5, proved to be the most accurate model. 
### Example of results 
<img width="550" alt="Screenshot 2023-07-29 at 6 04 12 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/4d157a5d-cd66-4b1f-9bc1-d8285b5074e5">

## History Plots
### First iteration, without fine-tuning the pre-trained model:<img width="437" alt="Screenshot 2023-07-29 at 6 05 31 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/a2c03b9c-f5c9-417f-be41-774744881dfc">
### After Fine-tuning:<img width="594" alt="Screenshot 2023-07-29 at 6 05 55 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/c89bb5c5-78e7-499c-be91-14d18ad7842b">
### Final Model:
<img width="574" alt="Screenshot 2023-07-29 at 6 06 23 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/c56cdd54-1c35-4c00-aab6-5509b9ffb6eb">

 ## Log of Iterations 


| Iteration       | # Layers           | Activation Function  | Train Accuracy (%) | Test Accuracy (%)
| ------------- |:-------------:| -----:| -----: | ------ | 
| 1      | 7 | softmax | 95.59 | 94.99
| 2     | 7 | softmax | 98.58 | 96.66
| 3      | 7 | ReLU | 100 | 98.33
| 4      | 7 | Leaky ReLU | 100 | 96.67
| 5      | 7 | Thresholded ReLU (Theta = 1) | 100 | 98.33
| 6      | 7 | Thresholded ReLU (Theta = 5) | 100 | 98.33
| 7      | 7 | Thresholded ReLU (Theta = .1) | 100 | 98.33
| 8      | 7 | Thresholded ReLU (Theta = .5) | 100 | 98.33


