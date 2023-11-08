# Monkey_Species_Image_Classification
Classifying Images of Monkeys by Species - Finetuned CNN and Vision Transformer approaches

I  used three different approaches to classify 10 species of Monkeys Species dataset, with a CNN model based on EfficientNet with finetuning achieving 100% accuracy on the test set. For this project, I have used 10 Monkey Species Dataset hosted on kaggle, which consists of 1369 colour images in 10 classes.

Total Images = 1369
Training Dataset = 1097
Validation Dataset = 218
Test Dataset (Unique data removed from the validation dataset) = 54

Classes
Mantled Howler
Patas Monkey
Bald Uakari
Japanese Macaque
Pygmy Marmoset
White Headed Capuchin
Silvery Marmoset
Common Squirrel Monkey
Black Headed Night Monkey
Nilgiri Langur

## Examples of Data (Silvery Marmoset is my favorite) 0

<img width="646" alt="Screenshot 2023-11-07 at 6 06 34 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/d19168fc-86af-4ff2-b3ae-b4dca1b8860d">

## Example of results from best model (EfficientNet - B7) 

![download (7)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/a384c341-74ba-4dcb-bf7c-92c0df238869)


## Approaches
1. Pre-trained Convolutional Neural Network
   
   a. MobileNetv2 - With and without finetuning
   
   b. EfficientNet - With and without finetuning
3. Vision Transformer


## Pre - trained Convolutional Neural Network
   ### MobileNetv2
   This approach  utilized MobileNetV2 as a pre-trained model, which was kept as is in a first attempt and later fine tuned. 
   
   <img width="582" alt="Screenshot 2023-11-07 at 6 36 35 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/bab89285-8772-47d6-83bc-f845c220f6eb">


   
   #### Example of results 
   
   ### EfficientNet-B7 
   Introduced by Tan et al. in EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks
   The EfficientNet family derives it's advantage over other ConvNets like MobileNetV3 from a new scaling method that uniformly scales all dimensions of depth/width/resolution using a simple yet highly effective compound coefficien. 
   #### Fine Tuning 

 




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


