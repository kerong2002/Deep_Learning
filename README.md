# Deep_Learning
<details> 
 <summary><b>Pytorch</b></summary> 

# Pytorch parameter
## nn.Conv2d()
visualization ： https://github.com/vdumoulin/conv_arithmetic/blob/master/README.md

- input = (N, Cin, H, W)
- output = (N, Cout, Hout, Wout)
  
![con2d.svg](svg%2Fcon2d.svg)
![H_out.svg](svg%2FH_out.svg)
![W_out.svg](svg%2FW_out.svg)


|    Parameter    | Description |
|:---------------:|:-----------:|
|   in_channels   |   輸入的通道數    |
| out_channels=64 |   輸出的通道數    |
|   kernel_size   |   捲積核的大小    |
|     stride      |     步長      |
|     padding     |    外圍的填充    |
|    dilation     |    核之間空隙    |
|     groups      |    分組捲積0    |
|      bias       |    偏置參數     |

## nn.MaxPool2d()

|   Parameter    |     Description     |
|:--------------:|:-------------------:|
|  kernel_size   |       捲積核的大小        |
|     stride     |         步長          |
|    padding     |        外圍的填充        |
|    dilation    |       核之間的空隙        |
| return_indices | 如果true，則會回傳等於最大值的序列 |
|   ceil_mode    |    如果true，會向上取整     |

## nn.ReLU()

| Parameter | Description |
|:---------:|:-----------:|
|  inplace  |    直接覆蓋     |

## nn.Linear()

|  Parameter   | Description |
|:------------:|:-----------:|
| in_featuers  |   輸入的張量大小   |
| out_features |   輸出的張量大小   |
|     bias     |    偏置參數     |

    
</details>

# Network
## LeNet5

| Number |      Layer      | Feature | Size  | Kernel Size | Stride | Activation |
|:------:|:---------------:|:-------:|:-----:|:-----------:|:------:|:----------:|
| input  |      image      |    1    | 32x32 |      -      |   -    |     -      |
|   1    |   Convolution   |    6    | 28x28 |     5x5     |   1    |    tanh    |
|   2    | Average Pooling |    6    | 14x14 |     2x2     |   2    |    tanh    |
|   3    |   Convolution   |   16    | 10x10 |     5x5     |   1    |    tanh    |
|   4    | Average Pooling |   16    |  5x5  |     2x2     |   2    |    tanh    |
|   5    |   Convolution   |   120   |  1x1  |     5x5     |   1    |    tanh    |
|   6    | Fully-Connected |    -    |  84   |      -      |   -    |    tanh    |
| Output | Fully-Connected |    -    |  10   |      -      |   -    |  softmax   |

## AlexNet

| Number |      Layer      | Feature | Size | Kernel Size | Stride | Padding | Activation |
|:------:|:---------------:|:-------:|:----:|:-----------:|:------:|:-------:|:----------:|
| input  |      image      |    3    |      |             |        |         |            |
|   1    |   Convolution   |   64    |      |     3x3     |   1    |    2    |    ReLU    |
|   2    |   Max Pooling   |   64    |      |     2x2     |   -    |    -    |            |
|   3    |   Convolution   |   192   |      |     3x3     |   1    |    2    |    ReLU    |
|   4    |   Max Pooling   |   192   |      |     2x2     |   -    |    -    |            |
|   5    |   Convolution   |   384   |      |     3x3     |   1    |    1    |    ReLU    |
|   6    |   Convolution   |   256   |      |     3x3     |   1    |    1    |    ReLU    |
|   7    |   Convolution   |   256   |      |     3x3     |   1    |    1    |    ReLU    |
|   8    |   Max Pooling   |   256   |      |     3x3     |   2    |    -    |            |
|   9    |     Dropout     |    -    |      |             |        |         |            |
|   10   | Fully-Connected |  2048   |      |             |        |         |    ReLU    |
|   11   |     Dropout     |    -    |      |             |        |         |            |
|   12   | Fully-Connected |  2048   |      |             |        |         |    ReLU    |
| Output | Fully-Connected |   10    |      |             |        |         |            |


## VGG16
| Number |      Layer      | Input Channels | Output Channels | Kernel Size | Stride | Padding | Activation |
|:------:|:---------------:|:--------------:|:---------------:|:-----------:|:------:|:-------:|:----------:|
| input  |      image      |       3        |                 |             |        |         |            |
|   1    |   Convolution   |       3        |       64        |     3x3     |   1    |    1    |    ReLU    |
|   2    |   Convolution   |       64       |       64        |     3x3     |   1    |    1    |    ReLU    |
|   3    |   Max Pooling   |       64       |                 |     2x2     |   2    |    0    |            |
|   4    |   Convolution   |       64       |       128       |     3x3     |   1    |    1    |    ReLU    |
|   5    |   Convolution   |      128       |       128       |     3x3     |   1    |    1    |    ReLU    |
|   6    |   Max Pooling   |      128       |                 |     2x2     |   2    |    0    |            |
|   7    |   Convolution   |      128       |       256       |     3x3     |   1    |    1    |    ReLU    |
|   8    |   Convolution   |      256       |       256       |     3x3     |   1    |    1    |    ReLU    |
|   9    |   Convolution   |      256       |       256       |     3x3     |   1    |    1    |    ReLU    |
|   10   |   Max Pooling   |      256       |                 |     2x2     |   2    |    0    |            |
|   11   |   Convolution   |      256       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   12   |   Convolution   |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   13   |   Convolution   |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   14   |   Max Pooling   |      512       |                 |     2x2     |   2    |    0    |            |
|   15   |   Convolution   |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   16   |   Convolution   |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   17   |   Convolution   |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   18   |   Max Pooling   |      512       |                 |     2x2     |   2    |    0    |            |
|   19   | AdaptiveAvgPool |      512       |                 |     7x7     |   -    |    -    |            |
|   20   | Fully-Connected |    512*7*7     |      4096       |      -      |   -    |    -    |    ReLU    |
|   21   |     Dropout     |                |                 |      -      |   -    |    -    |            |
|   22   | Fully-Connected |      4096      |      4096       |      -      |   -    |    -    |    ReLU    |
|   23   |     Dropout     |                |                 |      -      |   -    |    -    |            |
|   24   | Fully-Connected |      4096      |       10        |      -      |   -    |    -    |            |


## ResNet18
| Number |      Layer      | Input Channels | Output Channels | Kernel Size | Stride | Padding | Activation |
|:------:|:---------------:|:--------------:|:---------------:|:-----------:|:------:|:-------:|:----------:|
| input  |      image      |       3        |                 |             |        |         |            |
|   1    |   Convolution   |       3        |       64        |     3x3     |   1    |    1    |    ReLU    |
|   2    |  ResidualBlock  |       64       |       64        |     3x3     |   1    |    1    |    ReLU    |
|   3    |  ResidualBlock  |       64       |       64        |     3x3     |   1    |    1    |    ReLU    |
|   4    |  ResidualBlock  |       64       |       128       |     3x3     |   2    |    1    |    ReLU    |
|   5    |  ResidualBlock  |      128       |       128       |     3x3     |   1    |    1    |    ReLU    |
|   6    |  ResidualBlock  |      128       |       256       |     3x3     |   2    |    1    |    ReLU    |
|   7    |  ResidualBlock  |      256       |       256       |     3x3     |   1    |    1    |    ReLU    |
|   8    |  ResidualBlock  |      256       |       512       |     3x3     |   2    |    1    |    ReLU    |
|   9    |  ResidualBlock  |      512       |       512       |     3x3     |   1    |    1    |    ReLU    |
|   10   |   Avg Pooling   |      512       |       512       |     4x4     |   -    |    -    |            |
|   11   | Fully-Connected |      512       |       10        |      -      |   -    |    -    |            |
