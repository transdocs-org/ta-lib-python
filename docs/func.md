# 函数 API 示例

与 TA-Lib 类似，函数接口为其公开的 TA-Lib 指标提供了一个轻量级的封装。

每个函数都会返回一个输出数组，并且它们的参数都具有默认值，除非以关键字参数的形式另行指定。通常，这些函数会有一个初始“回看”周期（生成输出之前所需的观察值数量），该周期的值被设为 ``NaN``。

以下所有示例均使用函数 API：

```python
import numpy
import talib

close = numpy.random.random(100)
```

计算收盘价的简单移动平均：

```python
output = talib.SMA(close)
```

使用三重指数移动平均计算布林带：

```python
from talib import MA_Type

upper, middle, lower = talib.BBANDS(close, matype=MA_Type.T3)
```

计算收盘价的动量指标，时间周期设为 5：

```python
output = talib.MOM(close, timeperiod=5)
```

所有函数的文档：

* [重叠研究](func_groups/overlap_studies.md)
* [动量指标](func_groups/momentum_indicators.md)
* [成交量指标](func_groups/volume_indicators.md)
* [波动率指标](func_groups/volatility_indicators.md)
* [形态识别](func_groups/pattern_recognition.md)
* [周期指标](func_groups/cycle_indicators.md)
* [统计函数](func_groups/statistic_functions.md)
* [价格变换](func_groups/price_transform.md)
* [数学变换](func_groups/math_transform.md)
* [数学运算符](func_groups/math_operators.md)

[文档索引](doc_index.md)
[FLOAT_RIGHT 下一步：使用抽象 API](abstract.md)