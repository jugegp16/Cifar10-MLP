# Cifar10-MLP

Description
-----------------
I created a custom data loader in PyTorch to set up a pipeline for my model. Then implemented a 3-layer Multi-layer perceptron to classify images from the Cifar-10 dataset. Finally, I played around with two different spices of transfer learning and reported my results! 


Multi-Layer-Perceptron. (P2)
-------------------
I experimented with the batch size, hidden size, dropout, learning rate, lr_schedueler and optimizer type. I did my all my tests on 15 epochs and wrote down the first output recieved. I found that a combination of AdamW and CosineAnnealingLR with a batch size arround 20 and hidden size of 450 yielded the best results. If I were to do further testing I would try out more Optimizers such as ASGD, AdaGrad and AdaMax.

Test Results (P2)
-------------------
| learning rate |0.001    | 0.0005  | 0.0001
|---------------|---------|---------|-------|
|   accuracy    | 51.44%  | 51.854  | 42.12 |
|   loss        | 1.78    | 1.06    | 2.13  |

| lr_schedueler| CosineAnnealingLR | CosineAnnealingWarmRestarts | StepLR |
|--------------|-------------------|-----------------------------|--------|
|   accuracy   |      54.97%       |         40.74%              | 39.79% |
|   loss       |      1.01         |         0.99                | 1.04   |

| optimizer  | Adam    | AdamW  | SGD    |
|------------|---------|--------|--------|
|  accuracy  | 55.05%  | 51.07% | 35.11% |
|  loss      | 1.30    | 1.19   | 1.94   |


Transfer Learning  (P3)
-------------------
Transfer learning is a machine learning technique where a model developed for one task is reused as the starting point for a model on a second task. I used an ImageNet pre-trained model, MobileNetV2 and finetuned it to my Cifar10 dataloader. I experimented with two different methods of transfer learning...

  * Feature extraction - freezing all layers of the model layers except the final classifcation layer.
  * Fine-tuning - Further training all layers of pretrained model with a small learning rate
  

Test results (P3)
-------------------
| Type of Tranfer Learning | Accuracy|  Loss  |
|--------------------------|---------|--------|
| feature extraction       |  76.69 %|   0.91 |
| fine-tuning              |  92.81 %|   0.22 |
