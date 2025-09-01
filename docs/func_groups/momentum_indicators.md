# 动量指标函数
### ADX - 平均趋向指数
注意：``ADX`` 函数具有不稳定周期。  
```python
real = ADX(high, low, close, timeperiod=14)
```

### ADXR - 平均趋向指数评级
注意：``ADXR`` 函数具有不稳定周期。  
```python
real = ADXR(high, low, close, timeperiod=14)
```

### APO - 绝对价格振荡器
```python
real = APO(real, fastperiod=12, slowperiod=26, matype=0)
```

### AROON - 阿隆
```python
aroondown, aroonup = AROON(high, low, timeperiod=14)
```

### AROONOSC - 阿隆振荡器
```python
real = AROONOSC(high, low, timeperiod=14)
```

### BOP - 均势指标
```python
real = BOP(open, high, low, close)
```

### CCI - 商品通道指数
```python
real = CCI(high, low, close, timeperiod=14)
```

### CMO - 查德动量振荡器
注意：``CMO`` 函数具有不稳定周期。  
```python
real = CMO(real, timeperiod=14)
```

### DX - 方向运动指数
注意：``DX`` 函数具有不稳定周期。  
```python
real = DX(high, low, close, timeperiod=14)
```

### MACD - 移动平均收敛/发散
```python
macd, macdsignal, macdhist = MACD(real, fastperiod=12, slowperiod=26, signalperiod=9)
```

### MACDEXT - 可控制移动平均类型的MACD
```python
macd, macdsignal, macdhist = MACDEXT(real, fastperiod=12, fastmatype=0, slowperiod=26, slowmatype=0, signalperiod=9, signalmatype=0)
```

### MACDFIX - 固定12/26的移动平均收敛/发散
```python
macd, macdsignal, macdhist = MACDFIX(real, signalperiod=9)
```

### MFI - 资金流量指数
注意：``MFI`` 函数具有不稳定周期。  
```python
real = MFI(high, low, close, volume, timeperiod=14)
```

### MINUS_DI - 负方向指标
注意：``MINUS_DI`` 函数具有不稳定周期。  
```python
real = MINUS_DI(high, low, close, timeperiod=14)
```

### MINUS_DM - 负方向运动
注意：``MINUS_DM`` 函数具有不稳定周期。  
```python
real = MINUS_DM(high, low, timeperiod=14)
```

### MOM - 动量指标
```python
real = MOM(real, timeperiod=10)
```

### PLUS_DI - 正方向指标
注意：``PLUS_DI`` 函数具有不稳定周期。  
```python
real = PLUS_DI(high, low, close, timeperiod=14)
```

### PLUS_DM - 正方向运动
注意：``PLUS_DM`` 函数具有不稳定周期。  
```python
real = PLUS_DM(high, low, timeperiod=14)
```

### PPO - 百分比价格振荡器
```python
real = PPO(real, fastperiod=12, slowperiod=26, matype=0)
```

### ROC - 变动率：((price/prevPrice)-1)*100
```python
real = ROC(real, timeperiod=10)
```

### ROCP - 变动率百分比：(price-prevPrice)/prevPrice
```python
real = ROCP(real, timeperiod=10)
```

### ROCR - 变动率比率：(price/prevPrice)
```python
real = ROCR(real, timeperiod=10)
```

### ROCR100 - 变动率比率100刻度：(price/prevPrice)*100
```python
real = ROCR100(real, timeperiod=10)
```

### RSI - 相对强弱指数
注意：``RSI`` 函数具有不稳定周期。  
```python
real = RSI(real, timeperiod=14)
```

### STOCH - 随机指标
```python
slowk, slowd = STOCH(high, low, close, fastk_period=5, slowk_period=3, slowk_matype=0, slowd_period=3, slowd_matype=0)
```

### STOCHF - 快速随机指标
```python
fastk, fastd = STOCHF(high, low, close, fastk_period=5, fastd_period=3, fastd_matype=0)
```

### STOCHRSI - 随机相对强弱指数
注意：``STOCHRSI`` 函数具有不稳定周期。  
```python
fastk, fastd = STOCHRSI(real, timeperiod=14, fastk_period=5, fastd_period=3, fastd_matype=0)
```

### TRIX - 三重光滑EMA的1日变动率(ROC)
```python
real = TRIX(real, timeperiod=30)
```

### ULTOSC - 终极振荡器
```python
real = ULTOSC(high, low, close, timeperiod1=7, timeperiod2=14, timeperiod3=28)
```

### WILLR - 威廉指标%R
```python
real = WILLR(high, low, close, timeperiod=14)
```

[文档索引](../doc_index.md)

[FLOAT_RIGHT所有函数组](../funcs.md)