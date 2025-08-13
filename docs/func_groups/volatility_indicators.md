# 波动率指标函数
### ATR - 平均真实波幅
注意：``ATR`` 函数存在不稳定周期。  
```python
real = ATR(high, low, close, timeperiod=14)
```

### NATR - 归一化平均真实波幅
注意：``NATR`` 函数存在不稳定周期。  
```python
real = NATR(high, low, close, timeperiod=14)
```

### TRANGE - 真实波幅范围
```python
real = TRANGE(high, low, close)
```


[文档索引](../doc_index.md)

[所有函数组](../funcs.md) FLOAT_RIGHT