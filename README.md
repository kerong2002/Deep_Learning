# Deep_Learning
## Network
### LeNet5

| Number |      Layer      | Feature | Size  | Kernel Size | Stride | Activation |
|:------:|:---------------:|:-------:|:-----:|:-----------:|:------:|:----------:|
| input  |      image      |    1    | 32x32 |      -      |   -    |     -      |
|   1    |   Convolution   |    6    | 28x28 |     5x5     |   1    |    tanh    |
|   2    | Average Pooling |    6    | 14x14 |     2x2     |   2    |    tanh    |
|   3    |   Convolution   |   16    | 10x10 |     5x5     |   1    |    tanh    |
|   4    | Average Pooling |   16    |  5x5  |     2x2     |   2    |    tanh    |
|   5    |   Convolution   |   120   |  1x1  |     5x5     |   1    |    tanh    |
|   6    |  Full-Connect   |    -    |  84   |      -      |   -    |    tanh    |
| Output |  Full-Connect   |    -    |  10   |      -      |   -    |  softmax   |
