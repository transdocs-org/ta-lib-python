# 重叠研究函数
### BBANDS - 布林带
```python
upperband, middleband, lowerband = BBANDS(real, timeperiod=5, nbdevup=2, nbdevdn=2, matype=0)
```

### DEMA - 双重指数移动平均线
```python
real = DEMA(real, timeperiod=30)
```

### EMA - 指数移动平均线
注意：``EMA`` 函数有一个不稳定周期。  
```python
real = EMA(real, timeperiod=30)
```

### HT_TRENDLINE - 希尔伯特变换 - 瞬时趋势线
注意：``HT_TRENDLINE`` 函数有一个不稳定周期。  
```python
real = HT_TRENDLINE(real)
```

### KAMA - 考夫曼自适应移动平均线
注意：``KAMA`` 函数有一个不稳定周期。  
```python
real = KAMA(real, timeperiod=30)
```

### MA - 移动平均
```python
real = MA(real, timeperiod=30, matype=0)
```

### MAMA - MESA自适应移动平均线
注意：``MAMA`` 函数有一个不稳定周期。  
```python
mama, fama = MAMA(real, fastlimit=0, slowlimit=0)
```

### MAVP - 可变周期的移动平均
```python
real = MAVP(real, periods, minperiod=2, maxperiod=30, matype=0)
```

### MIDPOINT - 周期中点
```python
real = MIDPOINT(real, timeperiod=14)
```

### MIDPRICE - 周期中点价格
```python
real = MIDPRICE(high, low, timeperiod=14)
```

### SAR - 抛物线SAR
```python
real = SAR(high, low, acceleration=0, maximum=0)
```

### SAREXT - 抛物线SAR - 扩展版
```python
real = SAREXT(high, low, startvalue=0, offsetonreverse=0, accelerationinitlong=0, accelerationlong=0, accelerationmaxlong=0, accelerationinitshort=0, accelerationshort=0, accelerationmaxshort=0)
```

### SMA - 简单移动平均
```python
real = SMA(real, timeperiod=30)
```

### T3 - 三重指数移动平均 (T3)
注意：``T3`` 函数有一个不稳定周期。  
```python
real = T3(real, timeperiod=5, vfactor=0)
```

### TEMA - 三重指数移动平均
```python
real = TEMA(real, timeperiod=30)
```

### TRIMA - 三角形移动平均
```python
real = TRIMA(real, timeperiod=30)
```

### WMA - 加权移动平均
```python
real = WMA(real, timeperiod=30)
```

[文档索引](../doc_index.md)

[FLOAT_RIGHT所有函数组](../funcs.md)