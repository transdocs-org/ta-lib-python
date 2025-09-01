# 抽象API快速入门

如果你已经熟悉函数API的使用方式，那么使用抽象API也会感觉非常相似。每个函数接收相同的输入，以Numpy数组的字典形式传递：

```python
import numpy as np
# 注意：所有的ndarray必须长度相同！
inputs = {
    'open': np.random.random(100),
    'high': np.random.random(100),
    'low': np.random.random(100),
    'close': np.random.random(100),
    'volume': np.random.random(100)
}
```

函数可以直接导入，也可以通过名称实例化：

```python
from talib import abstract
sma = abstract.SMA
sma = abstract.Function('sma')
```

自此，调用函数的方式与函数API基本一致：

```python
from talib.abstract import *
output = SMA(inputs, timeperiod=25) # 默认在收盘价上计算
output = SMA(inputs, timeperiod=25, price='open') # 在开盘价上计算
upper, middle, lower = BBANDS(inputs, 20, 2, 2)
slowk, slowd = STOCH(inputs, 5, 3, 0, 3, 0) # 默认使用high, low, close
slowk, slowd = STOCH(inputs, 5, 3, 0, 3, 0, prices=['high', 'low', 'open'])
```

## 高级用法

对于TA-Lib更高级的用例，抽象API还提供了更多的灵活性。你甚至可以子类化 ``abstract.Function`` 并重写 ``set_input_arrays`` 方法，以自定义函数接受的输入数据类型（例如pandas的DataFrame）。

可以通过info属性访问每个函数的详细信息：

```python
print Function('stoch').info
{
  'name': 'STOCH',
  'display_name': '随机指标',
  'group': '动量指标',
  'input_names': OrderedDict([
    ('prices', ['high', 'low', 'close']),
  ]),
  'parameters': OrderedDict([
    ('fastk_period', 5),
    ('slowk_period', 3),
    ('slowk_matype', 0),
    ('slowd_period', 3),
    ('slowd_matype', 0),
  ]),
  'output_names': ['slowk', 'slowd'],
}
```

或者以人类可读的格式：

```python
help(STOCH)
str(STOCH)
```

``Function`` 的其他有用属性：

```python
Function('x').function_flags
Function('x').input_names
Function('x').input_arrays
Function('x').parameters
Function('x').lookback
Function('x').output_names
Function('x').output_flags
Function('x').outputs
```

除了直接调用函数之外，函数还保持状态，并会在设置后记住它们的参数/输入数组。你可以使用run()设置参数并使用新的输入数据重新计算：

```python
SMA.parameters = {'timeperiod': 15}
result1 = SMA.run(input_arrays1)
result2 = SMA.run(input_arrays2)

# 或者设置input_arrays并更改参数：
SMA.input_arrays = input_arrays1
ma10 = SMA(timeperiod=10)
ma20 = SMA(20)
```

更多详细信息，请查看 [代码](https://github.com/ta-lib/ta-lib-python/blob/master/talib/abstract.pyx#L46)。

[文档索引](doc_index.md)