## [ torch 参数更多 ] torch.fft.fftn

### [torch.fft.fftn](https://pytorch.org/docs/stable/generated/torch.fft.fftn.html?highlight=fftn#torch.fft.fftn)

```python
torch.fft.fftn(input, s=None, dim=None, norm='backward', *, out=None)
```

### [paddle.fft.fftn](https://www.paddlepaddle.org.cn/documentation/docs/zh/develop/api/paddle/fft/fftn_cn.html)

```python
paddle.fft.fftn(x, s=None, axes=None, norm='backward', name=None)
```

其中，PyTorch 相比 Paddle 支持更多其他参数，具体如下：
### 参数映射

| PyTorch       | PaddlePaddle | 备注                                                   |
| ------------- | ------------ | ------------------------------------------------------ |
| input         | x            | 输入 Tensor，仅参数名不一致。                            |
| s             | s            | 输出 Tensor 在傅里叶变换轴的长度。                      |
| dim           | axes         | 傅里叶变换的轴，如果没有指定，默认是使用最后一维，仅参数名不一致。|
| norm           |norm          |傅里叶变换的缩放模式，缩放系数由变换的方向和缩放模式同时决定，完全一致。|
| out            | -            |输出 Tensor，Paddle 无此参数，需要转写。              |

### 转写示例
#### out：指定输出
```python
# PyTorch 写法
torch.fft.fftn(x, s, dim, norm, out=y)

# Paddle 写法
paddle.assign(paddle.fft.fftn(x, s, axes, norm), y)
```
