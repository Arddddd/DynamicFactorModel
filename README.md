### 动态因子模型（DFM）简介

Geweke、Sargent 和 Sims (1977) 将经典因子模型进行扩展，首先在经济学领域提出了动态因子模型(DFM)。 模型的基本思想是：经济的周期波动是通过一系列经济变量的活动来传递和扩散的，任何单一经济变量的波动都不足以代表宏观经济的整体波动；存在能够解释和驱动各经济变量波动的隐含动态共同因子，且因子本身具有独立的动态演化过程。Stock 和 Watson(1991) 利用 DFM 从一系列宏观经济变量中提取出单一因子，以描述变量间的协同运动，从而解决了采用单一经济变量存在的局限性。 

![image](https://github.com/Arddddd/DynamicFactorModel/assets/43976514/5fd2f3cf-d41b-43ff-af7f-4331339ece36)


### 宏观经济指标选取：增长和通胀 

根据中国宏观经济数据的质量、时效性及在实践中的应用情况，各选取了一组增长指标和通胀指标的月度同比数据用于宏观变量：增长指标包括工业增加值 (IAV)、社会消费品零售总额 (CGTRS) 和固定资产投资完成额 (FAIC)。工业、消费和固定资产投资是我国经济增长的三大支柱，能够较好的体现经济增长；且数据为每月公布，便于更好地跟踪经济波动。 通胀指标包括消费者价格指数 (CPI)、工业生产者出厂价格指数 (PPI)。通过消费者和工业生产者这两个不同的角度，较完善地反映经济环境中的通胀情况。

#### 标准化处理

根据 Stock 和 Watson (1991) 的方法，先对各经济指标按如下方式进行了标准化处理，以消除不同经济指标波动率差异带来的影响：
![image](https://github.com/Arddddd/DynamicFactorModel/assets/43976514/5cfa7907-ba2a-44e2-a279-02f1ad5211c8)



####　1 增长因子

##### 1.1 公式
![image](https://github.com/Arddddd/DynamicFactorModel/assets/43976514/5195559c-707c-481a-9717-460f8c1101b0)

![image](https://github.com/Arddddd/DynamicFactorModel/assets/43976514/5a627f90-1566-4bca-b958-f21a36ce63ac)



####　2 通胀因子

##### 2.1 公式
![image](https://github.com/Arddddd/DynamicFactorModel/assets/43976514/2eca2cf3-2231-4f83-9e37-de0ea60b2841)



