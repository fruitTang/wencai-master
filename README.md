# wencai

wencai是i问财的策略回测接口的Pythonic工具包，满足量化爱好者和数据分析师在量化方面的需求。

[i问财](http://www.iwencai.net/)是同花顺旗下专业的机器人智能选股问答平台,致力于为投资者提供宏观数据、新闻资讯、A股、港美股、新三板、基金等各类理财方案。

![](https://graysliver.oss-cn-shenzhen.aliyuncs.com/iwcpage.jpg)

![](https://graysliver.oss-cn-shenzhen.aliyuncs.com/iwc_strategy.JPG)

### Dependencies

- Python 2.x/3.x
- requests>=2.14.2
- pandas>=0.18.1
- beautifulsoup4>=4.5.1

### Installation

- 方式1：pip install wencai
- 方式2：python setup.py install
- 方式3：访问<https://pypi.python.org/pypi/wencai>下载安装

### Upgrade

```shell
pip install wencai --upgrade
```

### API

具体API接口请点击这里：[Wiki](https://github.com/GraySilver/wencai-master/wiki/API)

### Quick Start

**Example 1**.获取回测分析

```python
import wencai as wc
report = wc.get_scrape_report("上市天数大于60天；筹码集中度90小于20%；非停牌；非st；")
print(report)
```

> ​     开始时间        结束时间     回测收益   最大回撤      胜率   周胜率     平均涨跌幅   平均损失比率 策略持有期     最大涨跌幅     最小涨跌幅   夏普比率 总交易天数
>
> 0  2017-10-28  2017-11-27  440.85%  5.16%  58.33%  0.25  0.028162  5.10927   3.0  0.157728 -0.049141  11.41  10.0



**Example 2**. 获取策略

```python
import wencai as wc
strategy = wc.get_strategy("上市天数大于60天；筹码集中度90小于20%；非停牌；非st；")
print(strategy)
```

> 日期    股票代码  股票简称   涨跌幅  当日收盘价(元)  dde大单净量（%）  股本规模   换手率
>
> 0  2017-11-27  000002   万科A -0.88     31.52       -0.02  超大盘股  0.54
> 1  2017-11-27  000004  国农科技 -5.10     26.05       -0.19   小盘股  3.89



**Example 3**.历史交易查询

```python
import wencai as wc
transaction = wc.get_scrape_transaction("上市天数大于60天；筹码集中度90小于20%；非停牌；非st；")
print(transaction)
```

> 股票代码        买入日期   买入价格        卖出日期   卖出价格 持有期   单次收益
>
> 0   000001  2017-10-31  11.55  2017-11-02  11.54   3  -0.1%
>
> 1   000005  2017-10-31   4.66  2017-11-02   4.62   3  -0.9%
>
> 2   000001  2017-11-03  11.49  2017-11-07  11.92   3   3.7%
>
> 3   000002  2017-11-03  29.23  2017-11-07  27.85   3  -4.7%
>
> 4   000001  2017-11-08  12.00  2017-11-10  12.30   3   2.5%
>
> 5   000002  2017-11-08  27.75  2017-11-10  27.51   3  -0.9%
>
> 6   000001  2017-11-13  12.35  2017-11-23  14.33   3    16%
>
> 7   000002  2017-11-13  27.45  2017-11-15  28.44   3   3.6%
>
> 8   000002  2017-11-16  28.35  2017-11-20  28.90   3   1.9%
>
> 9   000002  2017-11-21  28.54  2017-11-23  31.10   3     9%
>
> 10  000002  2017-11-24  31.18          持仓  31.80   3     2%
>
> 11  000004  2017-11-24  28.18          持仓  27.45   3  -2.6%



### Change Logs

### 0.1.5 2018/3/5

- 修正：调用问财策略接口失败问题

### 0.1.3 2017/11/27

- 创建第一个版本

### Others
Welcome to Star and Follow~
