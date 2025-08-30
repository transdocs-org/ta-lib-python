# 所有支持的指标和函数

* [重叠研究](func_groups/overlap_studies.md)
* [动量指标](func_groups/momentum_indicators.md)
* [成交量指标](func_groups/volume_indicators.md)
* [波动率指标](func_groups/volatility_indicators.md)
* [价格转换](func_groups/price_transform.md)
* [周期指标](func_groups/cycle_indicators.md)
* [形态识别](func_groups/pattern_recognition.md)
* [统计函数](func_groups/statistic_functions.md)
* [数学转换](func_groups/math_transform.md)
* [数学运算符](func_groups/math_operators.md)

#### [重叠研究](func_groups/overlap_studies.md)

```
BBANDS               布林带
DEMA                 双重指数移动平均线
EMA                  指数移动平均线
HT_TRENDLINE         希尔伯特变换 - 瞬时趋势线
KAMA                 考夫曼自适应移动平均线
MA                   移动平均
MAMA                 MESA自适应移动平均线
MAVP                 可变周期移动平均线
MIDPOINT             周期内中点
MIDPRICE             周期内中点价格
SAR                  抛物线转向指标
SAREXT               抛物线转向指标 - 扩展
SMA                  简单移动平均线
T3                   三重指数移动平均线 (T3)
TEMA                 三重指数移动平均线
TRIMA                三角形移动平均线
WMA                  加权移动平均线
```

#### [动量指标](func_groups/momentum_indicators.md)

```
ADX                  平均趋向指数
ADXR                 平均趋向指数评级
APO                  绝对价格震荡器
AROON                阿隆
AROONOSC             阿隆震荡器
BOP                  力量平衡
CCI                  商品通道指数
CMO                  钱德动量震荡器
DX                   动向指数
MACD                 移动平均收敛/发散
MACDEXT              可控MA类型的MACD
MACDFIX              固定12/26的移动平均收敛/发散
MFI                  资金流量指数
MINUS_DI             负向指标
MINUS_DM             负向动量
MOM                  动量
PLUS_DI              正向指标
PLUS_DM              正向动量
PPO                  百分比价格震荡器
ROC                  变化率：((价格/前一价格)-1)*100
ROCP                 变化百分比：(价格-前一价格)/前一价格
ROCR                 变化比率：(价格/前一价格)
ROCR100              100尺度变化比率：(价格/前一价格)*100
RSI                  相对强弱指数
STOCH                随机指标
STOCHF               快速随机指标
STOCHRSI             随机相对强弱指数
TRIX                 三重平滑EMA的1天变化率（ROC）
ULTOSC               终极震荡器
WILLR                威廉指标 %R
```

#### [成交量指标](func_groups/volume_indicators.md)

```
AD                   查克累积/派发线
ADOSC                查克累积/派发震荡器
OBV                  平衡成交量
```

#### [周期指标](func_groups/cycle_indicators.md)

```
HT_DCPERIOD          希尔伯特变换 - 主导周期周期
HT_DCPHASE           希尔伯特变换 - 主导周期相位
HT_PHASOR            希尔伯特变换 - 相量组件
HT_SINE              希尔伯特变换 - 正弦波
HT_TRENDMODE         希尔伯特变换 - 趋势与周期模式
```

#### [价格转换](func_groups/price_transform.md)

```
AVGPRICE             平均价格
MEDPRICE             中位价格
TYPPRICE             典型价格
WCLPRICE             加权收盘价
```

#### [波动率指标](func_groups/volatility_indicators.md)

```
ATR                  平均真实波幅
NATR                 标准化平均真实波幅
TRANGE               真实波幅
```

#### [形态识别](func_groups/pattern_recognition.md)

```
CDL2CROWS            两只乌鸦
CDL3BLACKCROWS       三只黑乌鸦
CDL3INSIDE           三内上/下
CDL3LINESTRIKE       三线打击
CDL3OUTSIDE          三外上/下
CDL3STARSINSOUTH     南方三星
CDL3WHITESOLDIERS    三个前进的白兵
CDLABANDONEDBABY     弃婴形态
CDLADVANCEBLOCK      前进受阻
CDLBELTHOLD          腰带形态
CDLBREAKAWAY         脱离形态
CDLCLOSINGMARUBOZU   收盘秃线
CDLCONCEALBABYSWALL  掩藏的婴儿吞没形态
CDLCOUNTERATTACK     反击形态
CDLDARKCLOUDCOVER    乌云盖顶
CDLDOJI              十字星
CDLDOJISTAR          十字星K线
CDLDRAGONFLYDOJI     蜻蜓十字星
CDLENGULFING         吞没形态
CDLEVENINGDOJISTAR   傍晚十字星
CDLEVENINGSTAR       傍晚之星
CDLGAPSIDESIDEWHITE  上升/下降跳空并列白线
CDLGRAVESTONEDOJI    墓碑十字星
CDLHAMMER            锤子
CDLHANGINGMAN        吊颈
CDLHARAMI            孕线形态
CDLHARAMICROSS       十字孕线形态
CDLHIGHWAVE          高浪线
CDLHIKKAKE           Hikkake形态
CDLHIKKAKEMOD        修正Hikkake形态
CDLHOMINGPIGEON      归巢鸽形态
CDLIDENTICAL3CROWS   相同三只乌鸦
CDLINNECK            颈内形态
CDLINVERTEDHAMMER    倒锤头
CDLKICKING           反转突破形态
CDLKICKINGBYLENGTH   通过较长秃线判断牛市/熊市的反转突破形态
CDLLADDERBOTTOM      梯底形态
CDLLONGLEGGEDDOJI    长腿十字星
CDLLONGLINE          长线K线
CDLMARUBOZU          秃线
CDLMATCHINGLOW       相同低价形态
CDLMATHOLD           帐篷形态
CDLMORNINGDOJISTAR   十字晨星
CDLMORNINGSTAR       晨星
CDLONNECK            颈上线形态
CDLPIERCING          刺透形态
CDLRICKSHAWMAN       人力车夫形态
CDLRISEFALL3METHODS  上升/下降三法
CDLSEPARATINGLINES   分离线形态
CDLSHOOTINGSTAR      流星
CDLSHORTLINE         短线K线
CDLSPINNINGTOP       纺锤顶
CDLSTALLEDPATTERN    停滞形态
CDLSTICKSANDWICH     棍棒三明治形态
CDLTAKURI            探水形态（具有极长下影线的蜻蜓十字星）
CDLTASUKIGAP         跳空镊子形态
CDLTHRUSTING         刺入形态
CDLTRISTAR           三星形态
CDLUNIQUE3RIVER      独特三河形态
CDLUPSIDEGAP2CROWS   向上跳空两只乌鸦
CDLXSIDEGAP3METHODS  向上/向下跳空三法
```

#### [统计函数](func_groups/statistic_functions.md)

```
BETA                 贝塔系数
CORREL               皮尔逊相关系数 (r)
LINEARREG            线性回归
LINEARREG_ANGLE      线性回归角度
LINEARREG_INTERCEPT  线性回归截距
LINEARREG_SLOPE      线性回归斜率
STDDEV               标准差
TSF                  时间序列预测
VAR                  方差
```

#### [数学转换](func_groups/math_transform.md)

```
ACOS                 向量三角函数反余弦
ASIN                 向量三角函数反正弦
ATAN                 向量三角函数反正切
CEIL                 向量向上取整
COS                  向量三角函数余弦
COSH                 向量三角函数双曲余弦
EXP                  向量算术指数
FLOOR                向量向下取整
LN                   向量自然对数
LOG10                向量以10为底的对数
SIN                  向量三角函数正弦
SINH                 向量三角函数双曲正弦
SQRT                 向量平方根
TAN                  向量三角函数正切
TANH                 向量三角函数双曲正切
```

#### [数学运算符](func_groups/math_operators.md)

```
ADD                  向量算术加法
DIV                  向量算术除法
MAX                  指定周期内的最高值
MAXINDEX             指定周期内最高值的索引
MIN                  指定周期内的最低值
MININDEX             指定周期内最低值的索引
MINMAX               指定周期内的最低和最高值
MINMAXINDEX          指定周期内最低和最高值的索引
MULT                 向量算术乘法
SUB                  向量算术减法
SUM                  求和
```

[文档索引](doc_index.md)