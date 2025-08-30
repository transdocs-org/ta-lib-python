# 统计函数
### BETA - 贝塔系数
```python
real = BETA(real0, real1, timeperiod=5)
```

### CORREL - 皮尔逊相关系数 (r)
```python
real = CORREL(real0, real1, timeperiod=30)
```

### LINEARREG - 线性回归
```python
real = LINEARREG(real, timeperiod=14)
```

### LINEARREG_ANGLE - 线性回归角度
```python
real = LINEARREG_ANGLE(real, timeperiod=14)
```

### LINEARREG_INTERCEPT - 线性回归截距
```python
real = LINEARREG_INTERCEPT(real, timeperiod=14)
```

### LINEARREG_SLOPE - 线性回归斜率
```python
real = LINEARREG_SLOPE(real, timeperiod=14)
```

### STDDEV - 标准差
```python
real = STDDEV(real, timeperiod=5, nbdev=1)
```

### TSF - 时间序列预测
```python
real = TSF(real, timeperiod=14)
```

### VAR - 方差
```python
real = VAR(real, timeperiod=5, nbdev=1)
```


[文档目录](../doc_index.md)

[FLOAT_RIGHT所有函数组](../funcs.md)