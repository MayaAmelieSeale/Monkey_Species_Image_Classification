# Monkey_Species_Image_Classification
Classifying Images of Monkeys by Species - Finetuned CNN and Vision Transformer approaches

I used three different approaches to classify 10 species of Monkeys Species dataset. The best model was a CNN model based on EfficientNet with finetuning that achieved 100% accuracy on the test set. For this project, I have used 10 Monkey Species Dataset hosted on kaggle, which consists of 1369 colour images in 10 classes.

Total Images = 1369

Training Dataset = 1097

Validation Dataset = 218

Test Dataset (Unique data removed from the validation dataset) = 54

### Classes

The dataset is fairly balanced, meaning accuracy is a good metric 

| Species Name              |   Number of Images |
|-------------|-------------|
| Mantled Howler            |     126 |
| Patas Monkey              |     135 |
| Bald Uakari               |     131 |
| Japanese Macaque          |     147 |
| Pygmy Marmoset            |     124 |
| White Headed Capuchin     |     133 |
| Silvery Marmoset          |     125 |
| Common Squirrel Monkey    |     137 |
| Black Headed Night Monkey |     129 |
| Nilgiri Langur            |     122 |

## Examples of Data (Silvery Marmoset is my favorite) 

<img width="646" alt="Screenshot 2023-11-07 at 6 06 34 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/d19168fc-86af-4ff2-b3ae-b4dca1b8860d">

## Example batch of results from best model (EfficientNet - B7) 

![download (7)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/a384c341-74ba-4dcb-bf7c-92c0df238869)

## Model Summary
Eval time refers to the time taken to make and evaluate predictions on the test datatset

| Model              |  Finetuned? | Train Accuracy (%)  |  Test Accuracy (%) | F1 Score (Test) | Eval Time (seconds)
|-------------|-------------| ------ | ----- |  ----- | ----- | 
| MobileNetV3 - Large     |     No | 84.2 | 90.0 | .798 | 3 
| MobileNetV3 - Large |     Yes | 99.2 | 96.7 | 1.0 | 3
| EfficientNet   |     No | 93.9 | 91.7 | .924 | 3
| EfficientNet   |     Yes | 100.0 | 100.0 | .909 | 3 
| Vision Transformer** | N/A |   | 23.3 | 

**Model needs improvement


### Future Directions 
In the future, I will explore combining EfficientNet with Vision Transformers to see if performance can get even better. In addition, I will seek out more complex data sets to play with, since any future comparisons between classifiers are liable to ceiling effects. 

## Approaches

All models used SparseCategoricalCrossentropy as a loss function, which was determined to be the best performing loss function. 

1. Pre-trained Convolutional Neural Network
   
   a. MobileNetv2 - With and without finetuning
   
   b. EfficientNet - With and without finetuning

3. Vision Transformer


## Pre - trained Convolutional Neural Network
   ### MobileNetV3
   This approach  utilized MobileNetV3 as a pre-trained model, which was kept as is in a first attempt and later fine tuned. 
   
  
   #### History Plot
   ![download (13)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/201ee182-fc38-48a7-ab43-a63d9495f661)

  #### Without Fine Tuning

  Test accuracy : 0.8999999761581421
  
F1 Score : 0.7988888888888889

              precision    recall  f1-score   support

           0       1.00      1.00      1.00         2
           1       0.50      0.50      0.50         2
           2       1.00      1.00      1.00         3
           3       1.00      1.00      1.00         4
           4       0.00      0.00      0.00         1
           5       1.00      1.00      1.00         6
           6       1.00      1.00      1.00         3
           7       0.80      1.00      0.89         4
           8       1.00      0.67      0.80         3
           9       0.67      1.00      0.80         2

  ##### Confusion Matrix 
   ![download (12)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/29d7f30b-891a-4be7-ab1a-be7384ef7326)

#### After Fine Tuning

Test accuracy : 0.9666666388511658

F1 Score : 1.0

              precision    recall  f1-score   support

           0       1.00      1.00      1.00         3
           1       1.00      1.00      1.00         3
           3       1.00      1.00      1.00         4
           4       1.00      1.00      1.00         1
           5       1.00      1.00      1.00         2
           6       1.00      1.00      1.00         4
           7       1.00      1.00      1.00         5
           8       1.00      1.00      1.00         5
           9       1.00      1.00      1.00         3


##### Confusion Matrix 

![download (14)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/18eee830-bac0-4985-91c8-620ea16ff805)

   ### EfficientNet-B7 
   Introduced by Tan et al. in EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks
   
   The EfficientNet family derives it's advantage over other ConvNets like MobileNetV3 from a new scaling method that uniformly scales all dimensions of depth/width/resolution using a simple yet highly effective compound coefficient. 
   Out of all of the members of the EfficientNet family, B7 has achieved the best performance. The best classifier depends on the application, as some may be faster while compromising accuracy. Here is a comparison based on performance on ImageNet from Tan et al: 
   
   <img width="580" alt="Screenshot 2023-11-07 at 11 33 51 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/800d88db-9bef-4251-bf53-c7df61b6767b">

   #### History Plot
   <img width="747" alt="Screenshot 2023-11-07 at 10 55 41 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/24a2f01d-fc5a-4172-907d-bc09d572581a">
   
   #### Without Fine Tuning
   
Test accuracy : 0.917

F1 Score : 0.924

F1 Score by class

              precision    recall  f1-score   support

           0       1.00      1.00      1.00         2
           1       1.00      1.00      1.00         3
           2       0.50      1.00      0.67         2
           3       1.00      0.50      0.67         2
           4       1.00      0.83      0.91         6
           5       1.00      1.00      1.00         3
           6       1.00      1.00      1.00         5
           7       1.00      1.00      1.00         3
           8       1.00      1.00      1.00         1
           9       1.00      1.00      1.00         3



##### Confusion Matrix 

![download (9)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/81757a59-3cdf-46ec-aefe-1eb247b57b6b)

Even before fine tuning, this model is performing well. This exemplifies the power of transfer learning, where knowledge gained in one domain can be carried to new domains. Let's see if we can improve it even more. 

#### After Fine Tuning

Test accuracy : 1.0

F1 Score : 1.0

F1 Score by class

              precision    recall  f1-score   support

           0       1.00      1.00      1.00         2
           1       1.00      1.00      1.00         4
           2       1.00      1.00      1.00         2
           3       1.00      1.00      1.00         5
           4       1.00      1.00      1.00         2
           5       1.00      1.00      1.00         5
           7       1.00      1.00      1.00         3
           8       1.00      1.00      1.00         4
           9       1.00      1.00      1.00         3



##### Confusion Matrix 

![download (11)](https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/a1ecba60-d8b3-4525-8864-d0c2d78e81f2)

 A test accuracy of 100% and an F1  score of 1.0 indicate a model that is performing extremely well 

 ## Vision Transformer 
 Vision Transformer (ViT) models are inspired by approaces that have poved successful in NLP, mainly those using self-attention and context to capture long range dependencies within images, ultimately improving performance. ViT allows for increased performance over CNN while using fewer computational resources. In addition, ViTs generally have a weaker inductive bias. 

 Example of the patches used in the ViT

<img width="338" alt="Screenshot 2023-11-07 at 11 54 33 PM" src="https://github.com/MayaAmelieSeale/Monkey_Species_Image_Classification/assets/140470683/631e81c6-a799-44b4-81c3-168717149acd">

This model currently has very low performance. This could be due to the small dataset, as ViTs typically perform best at the size of tens of thousands of images. However, I will nonetheless attempt to improve ViT's perfomance here in the future. 





