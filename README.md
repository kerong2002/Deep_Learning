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
