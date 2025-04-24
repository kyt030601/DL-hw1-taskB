# DL-hw1-taskB
This project implements a 2-layer CNN with Multi-Head Self-Attention (MHSA) for image classification on the ImageNet-mini dataset. It is benchmarked against a baseline ResNet34 and includes full training, validation, FLOPs/parameter analysis, and an ablation test with a pure CNN version.

Q:How to Run?    
A:Change the data_dir in the program to the path of your own folder and you can use it    

This will:    
1.Train Baseline ResNet34 on ImageNet-mini.    
2.Train Custom CNN+MHSA with only 2 effective layers.    
3.Perform Ablation Test using a CNN-only model.    
4.Report:    
-Validation accuracy for each model    
-FLOPs and parameter count using thop    
-Training/validation accuracy plot    

Note:    
1.Training uses Adam optimizer, LR = 1e-3, Batch size = 32, Epochs = 20.    
2.FLOPs/parameters calculated using thop.    
3.Suitable for efficient deployment or limited-resource environments.    
