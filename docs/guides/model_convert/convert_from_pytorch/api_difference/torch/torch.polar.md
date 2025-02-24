## [ 组合替代实现 ]torch.polar

### [torch.polar](https://pytorch.org/docs/stable/generated/torch.polar.html#torch.polar)
```python
torch.polar(abs, angle, *, out=None)
```


构造一个复数张量，其元素为与绝对值 abs 和角 angle 对应的极坐标所对应的笛卡尔坐标，公式为：

$ out= abs ⋅ cos(angle) + abs ⋅ sin(angle) ⋅ j $

PaddlePaddle 目前无对应 API，可使用如下代码组合实现该 API。

###  转写示例
#### out：指定输出
```python
# PyTorch 写法
torch.polar(abs, angle, out=y)

# Paddle 写法
y = paddle.complex(abs * paddle.cos(angle), abs * paddle.sin(angle))
```
