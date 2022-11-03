# ECE1512-ProjectA
The goal of this project is Using Knowledge Distillation (KD)[[1]](#1) to compress a huge Teacher model to a smaller Student model.

## Task 1
### Knowledge Distillation Process
![alt text](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/KD.jpeg)
### Dataset
- MINIST
### Code
The code of task 1 is in [Task1.ipynb](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/Task1.ipynb). The Teacher model and Student model are both Sequential models. We train Teacher model using loss function `Teacher training loss = softmax cross entropy loss` and train Student model using loss function `Student training loss = ALPHA * Distillation Loss + （1-ALPHA）* student Softmax cross entropy loss`. Here, ALPHA is a hyperparameter to weigh the student and distillation loss.
### Student Accuracy with Different ALPHA and Temperature hyperparameters:
![alt text](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/performance1.png)

### State-of-art KD
We also implemented a recent approach of KD: **Subclass Distillation** proposed by Rafael M¨uller, Simon Kornblith, and Geoffrey Hinton[[2]](#2). 

## Task 2
We used pre-trained model `ResNet50V2` and `MobileNetV2` as Teacher model and Student model respectively. 
### Knowledge Distillation Using Pre-trained Model Process:
![alt text](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/KD%2BTL.png)
### Code 
The code for Taks 2 is provided in [Task2.ipynb](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/Task2.ipynb)
### Dataset
- MHIST
### Requirements
To run `Task2.ipynb` in colab, `annotations.csv` and `images.zip` files from MHIST dataset are required under **content** directory. 
### Student Accuracy with Different and Temperature hyperparameters:
![alt text](https://github.com/Joyce-ZhouY/ECE1512-ProjectA/blob/main/performance2.png)

## References
<a id="1">[1]</a> 
Geoffrey Hinton, Oriol Vinyals, and Jeff Dean. Distilling the Knowledge in a Neural Network. arXiv preprint
arXiv:1503.02531, 2015. https://arxiv.org/abs/1503.02531

<a id="2">[2]</a> 
Rafael M¨uller, Simon Kornblith, and Geoffrey Hinton. Subclass distillation. arXiv preprint
arXiv:2002.03936, 2020. https://arxiv.org/abs/2002.03936.
