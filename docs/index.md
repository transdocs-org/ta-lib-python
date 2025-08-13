# 关于

这是一个基于 Cython 而非 SWIG 的 [TA-LIB](https://ta-lib.org) Python 封装。摘自其官网：

> TA-Lib 被交易软件开发者广泛使用，用于对金融市场数据进行技术分析。

> * 包含150多个指标，如 ADX、MACD、RSI、随机指标、布林带等。
> * 支持蜡烛图模式识别
> * 提供 C/C++、Java、Perl、Python 和 100% 托管 .NET 的开源 API

原始的 Python 绑定使用 [SWIG](https://swig.org)，但其安装困难且效率不高。因此，本项目使用 Cython 和 Numpy 来高效而简洁地绑定到 TA-Lib —— 产生的结果比 SWIG 接口快 2-4 倍。

#### [安装 TA-Lib](install.md) 或 [阅读文档](doc_index.md)

## 示例

与 TA-Lib 类似，函数接口为公开的 TA-Lib 指标提供了一个轻量级封装。

每个函数返回一个输出数组，并对其参数具有默认值，除非指定为关键字参数。通常，这些函数会有一个初始的“回望”期（在生成输出之前所需的观察数），该值被设置为 ``NaN``。

以下所有示例都使用函数 API：

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

计算收盘价的动量，时间周期为 5：

```python
output = talib.MOM(close, timeperiod=5)
```

## 抽象 API 快速入门

如果您已经熟悉使用函数 API，那么使用抽象 API 也会感到很熟悉。每个函数接受相同的输入，作为 Numpy 数组的字典传递：

```python
import numpy as np
# 注意：所有的 ndarray 必须长度相同！
inputs = {
    'open': np.random.random(100),
    'high': np.random.random(100),
    'low': np.random.random(100),
    'close': np.random.random(100),
    'volume': np.random.random(100)
}
```

函数可以直接导入或通过名称实例化：

```python
from talib import abstract
sma = abstract.SMA
sma = abstract.Function('sma')
```

从那之后，调用函数与函数 API 基本相同：

```python
from talib.abstract import *
output = SMA(input_arrays, timeperiod=25) # 默认计算收盘价
output = SMA(input_arrays, timeperiod=25, price='open') # 计算开盘价
upper, middle, lower = BBANDS(input_arrays, 20, 2, 2)
slowk, slowd = STOCH(input_arrays, 5, 3, 0, 3, 0) # 默认使用 high, low, close
slowk, slowd = STOCH(input_arrays, 5, 3, 0, 3, 0, prices=['high', 'low', 'open'])
```

了解更多关于 TA-Lib 的高级用法 [点击此处](abstract.md)。

## 支持的指标

我们可以列出 TA-Lib 支持的所有 TA 函数，可以是 ``list`` 或按组（例如 "Overlap Studies"、"Momentum Indicators" 等）排序的 ``dict``：

```python
import talib

print talib.get_functions()
print talib.get_function_groups()
```

### 函数组

* [重叠研究](func_groups/overlap_studies.md)
* [动量指标](func_groups/momentum_indicators.md)
* [成交量指标](func_groups/volume_indicators.md)
* [波动率指标](func_groups/volatility_indicators.md)
* [价格转换](func_groups/price_transform.md)
* [周期指标](func_groups/cycle_indicators.md)
* [形态识别](func_groups/pattern_recognition.md)
* [统计函数](func_groups/statistic_functions.md)
* [数学变换](func_groups/math_transform.md)
* [数学运算符](func_groups/math_operators.md)

#### [重叠研究](func_groups/overlap_studies.md)

```
BBANDS               布林带
DEMA                 双重指数移动平均
EMA                  指数移动平均
HT_TRENDLINE         希尔伯特变换 - 即时趋势线
KAMA                 考夫曼自适应移动平均
MA                   移动平均
MAMA                 MESA 自适应移动平均
MAVP                 可变周期移动平均
MIDPOINT             周期内中点
MIDPRICE             周期内中位价格
SAR                  抛物线转向指标
SAREXT               抛物线转向指标扩展版
SMA                  简单移动平均
T3                   三重指数移动平均 (T3)
TEMA                 三重指数移动平均
TRIMA                三角移动平均
WMA                  加权移动平均
```

#### [动量指标](func_groups/momentum_indicators.md)

```
ADX                  平均趋向指数
ADXR                 平均趋向指数评级
APO                  绝对价格震荡器
AROON                阿隆
AROONOSC             阿隆震荡器
BOP                  力度指标
CCI                  商品通道指数
CMO                  查德动量震荡器
DX                   方向性运动指数
MACD                 移动平均收敛/发散
MACDEXT              具有可控移动平均类型的 MACD
MACDFIX              固定移动平均收敛/发散 (12/26)
MFI                  资金流量指数
MINUS_DI             负方向指标
MINUS_DM             负方向变动
MOM                  动量
PLUS_DI              正方向指标
PLUS_DM              正方向变动
PPO                  百分比价格震荡器
ROC                  变化率：((价格/前一价格)-1)*100
ROCP                 变化率百分比：(价格-前一价格)/前一价格
ROCR                 变化率比率：(价格/前一价格)
ROCR100              变化率比率 100 比例：(价格/前一价格)*100
RSI                  相对强弱指数
STOCH                随机指标
STOCHF               快速随机指标
STOCHRSI             随机相对强弱指数
TRIX                 三重平滑 EMA 的 1 天变化率 (ROC)
ULTOSC               终极震荡器
WILLR                威廉指标 %R
```

#### [成交量指标](func_groups/volume_indicators.md)

```
AD                   嘉路兰 A/D 线
ADOSC                嘉路兰 A/D 震荡器
OBV                  平衡成交量
```

#### [波动率指标](func_groups/volatility_indicators.md)

```
ATR                  平均真实波幅
NATR                 标准化平均真实波幅
TRANGE               真实波幅范围
```

#### [价格转换](func_groups/price_transform.md)

```
AVGPRICE             平均价格
MEDPRICE             中间价格
TYPPRICE             典型价格
WCLPRICE             加权收盘价
```

#### [周期指标](func_groups/cycle_indicators.md)

```
HT_DCPERIOD          希尔伯特变换 - 主导周期期数
HT_DCPHASE           希尔伯特变换 - 主导周期相位
HT_PHASOR            希尔伯特变换 - 相量组件
HT_SINE              希尔伯特变换 - 正弦波
HT_TRENDMODE         希尔伯特变换 - 趋势与周期模式
```

#### [形态识别](func_groups/pattern_recognition.md)

```
CDL2CROWS            两只乌鸦
CDL3BLACKCROWS       三只乌鸦
CDL3INSIDE           三内部上涨/下跌
CDL3LINESTRIKE       三线打击
CDL3OUTSIDE          三外部上涨/下跌
CDL3STARSINSOUTH     南方三星
CDL3WHITESOLDIERS    三白兵
CDLABANDONEDBABY     弃婴形态
CDLADVANCEBLOCK      前进受阻形态
CDLBELTHOLD          腰带形态
CDLBREAKAWAY         脱离形态
CDLCLOSINGMARUBOZU   收盘光头光脚
CDLCONCEALBABYSWALL  隐藏的吞没形态
CDLCOUNTERATTACK     反击形态
CDLDARKCLOUDCOVER    乌云盖顶
CDLDOJI              十字星
CDLDOJISTAR          十字星形态
CDLDRAGONFLYDOJI     蜻蜓十字星
CDLENGULFING         吞没形态
CDLEVENINGDOJISTAR   暮星十字星
CDLEVENINGSTAR       暮星
CDLGAPSIDESIDEWHITE  上/下跳空并列阳线
CDLGRAVESTONEDOJI    墓碑十字星
CDLHAMMER            锤头
CDLHANGINGMAN        上吊线
CDLHARAMI            孕线形态
CDLHARAMICROSS       十字孕线形态
CDLHIGHWAVE          高波烛形态
CDLHIKKAKE           反转型态
CDLHIKKAKEMOD        改进型反转型态
CDLHOMINGPIGEON      归巢鸽形态
CDLIDENTICAL3CROWS   相同三只乌鸦
CDLINNECK            颈内形态
CDLINVERTEDHAMMER    倒锤头
CDLKICKING           跳空并列阳线
CDLKICKINGBYLENGTH   根据较长光头光脚确定多空的跳空并列形态
CDLLADDERBOTTOM      梯底形态
CDLLONGLEGGEDDOJI    长腿十字星
CDLLONGLINE          长线烛形态
CDLMARUBOZU          光头光脚
CDLMATCHINGLOW       匹配低点形态
CDLMATHOLD           持有形态
CDLMORNINGDOJISTAR   晨星十字星
CDLMORNINGSTAR       晨星
CDLONNECK            颈上形态
CDLPIERCING          刺透形态
CDLRICKSHAWMAN       推车夫形态
CDLRISEFALL3METHODS  上升/下降三法
CDLSEPARATINGLINES   分离线形态
CDLSHOOTINGSTAR      射击之星
CDLSHORTLINE         短线烛形态
CDLSPINNINGTOP       纺锤形态
CDLSTALLEDPATTERN    停滞形态
CDLSTICKSANDWICH     棒形三明治
CDLTAKURI            探水形态（带有极长下影线的蜻蜓十字星）
CDLTASUKIGAP         跳空缺口
CDLTHRUSTING         插入形态
CDLTRISTAR           三星形态
CDLUNIQUE3RIVER      独特三河形态
CDLUPSIDEGAP2CROWS   向上跳空双乌鸦
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