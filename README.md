# Cifar10-MLP

Evaluating Different Hyperparamaters
-------------------
I experimented with the batch size, hidden size, dropout, learning rate, lr_schedueler and optimizer type. I did my all my tests on 15 epochs and wrote down the first output recieved. I found that a combination of AdamW and CosineAnnealingLR with a batch size arround 20 and hidden size of 450 yielded the best results. If I were to do further testing I would try out more Optimizers such as ASGD, AdaGrad and AdaMax.

# Test Results

| batch size   |   10    |   15    |  20    |
|--------------|---------|---------|--------|
|  * accuracy  | 51.41%  | 51.96%  | 55.70% |
|  * loss      | 1.68    | 1.03    | 1.70   |

# hidden size   - 100     | 450     | 800
#   * accuracy  - 45.47%  | 51.96%  | 52.21% 
#   * loss      - 1.57    | 0.97    | 2.28 

# dropout       - 0.25    | 0.5     | .8
#   * accuracy  - 54.97%  | 46.94%  | 38.78%
#   * loss      - 1.01    | 1.70    | 2.01

# learning rate - 0.001   | 0.0005  | 0.0001
#   * accuracy  - 51.44%  | 51.854  | 42.12
#   * loss      - 1.78    | 1.06    | 2.13

# lr_schedueler - CosineAnnealingLR | CosineAnnealingWarmRestarts | StepLR
#   * accuracy  - 54.97%            | 40.74%                      | 39.79%
#   * loss      - 1.01              | 0.99                        | 1.04

# optimizer     - Adam     | AdamW  | SGD
#   * accuracy  - 55.05%   | 51.07% | 35.11%
#   * loss      - 1.30     | 1.19   | 1.94
