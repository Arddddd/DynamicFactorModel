### 动态因子模型（DFM）简介

Geweke、Sargent 和 Sims (1977) 将经典因子模型进行扩展，首先在经济学领域提出了动态因子模型(DFM)。 模型的基本思想是：经济的周期波动是通过一系列经济变量的活动来传递和扩散的，任何单一经济变量的波动都不足以代表宏观经济的整体波动；存在能够解释和驱动各经济变量波动的隐含动态共同因子，且因子本身具有独立的动态演化过程。Stock 和 Watson(1991) 利用 DFM 从一系列宏观经济变量中提取出单一因子，以描述变量间的协同运动，从而解决了采用单一经济变量存在的局限性。 

动态因子模型的基本形式如下：
$$
y_t = \Lambda f_t+Bx_t+u_t
\\f_t=A_1 f_{t-1}+···+A_p f_{t-p}+\eta_t
\\其中𝑓_𝑡即为隐含动态因子矩阵；𝑦_𝑡为内生变量矩阵；𝑥_𝑡为外生变量矩阵；\Lambda为因子载荷矩阵；\eta_t和u_𝑡为白噪声过程；\\𝑝为动态因子的自回归滞后阶数，可利用信息准则法确定具体阶数。采用了极大似然法来估计模型参数。
$$
令模型中隐含因子数量为 1 ，通过对宏观经济变量进行合理的分组，可使隐含共同因子具有明确的经济学含义。如输入一组增长指标，则隐含因子为增长因子；输入一组通胀指标，则隐含因子为通胀因子。



### 宏观经济指标选取：增长和通胀 

根据中国宏观经济数据的质量、时效性及在实践中的应用情况，各选取了一组增长指标和通胀指标的月度同比数据用于宏观变量：增长指标包括工业增加值 (IAV)、社会消费品零售总额 (CGTRS) 和固定资产投资完成额 (FAIC)。工业、消费和固定资产投资是我国经济增长的三大支柱，能够较好的体现经济增长；且数据为每月公布，便于更好地跟踪经济波动。 通胀指标包括消费者价格指数 (CPI)、工业生产者出厂价格指数 (PPI)。通过消费者和工业生产者这两个不同的角度，较完善地反映经济环境中的通胀情况。

#### 标准化处理

根据 Stock 和 Watson (1991) 的方法，先对各经济指标按如下方式进行了标准化处理，以消除不同经济指标波动率差异带来的影响：
$$
I_{norm}=\frac{I_{raw}-mean(I_{raw})}{std(I_{raw})}
$$


####　1 增长因子

##### 1.1 公式

$$
公式① \ \ \ \begin{pmatrix}y_1\\y_2\\y_3\\\end{pmatrix} = \begin{pmatrix}z_1\\z_2\\z_3\\\end{pmatrix}*
\begin{pmatrix}x_1\end{pmatrix}_t+\begin{pmatrix}a_1\\a_2\\a_3\\\end{pmatrix}+\begin{pmatrix}v_1\\v_2\\v_3\\\end{pmatrix}_t\\\begin{pmatrix}v_1\\v_2\\v_3\\\end{pmatrix}_t\sim MVN[0,\begin{pmatrix}r_{11}&r_{12}&r_{13}\\r_{21}&r_{22}&r_{23}\\r_{31}&r_{32}&r_{33}\\\end{pmatrix}]\\
\begin{align*}
& \begin{pmatrix}y_1\\y_2\\y_3\\\end{pmatrix} 为可观测的目标变量,包括IAV、CGTRS和FAIC,其中存在缺失数据；\\
& \begin{pmatrix}x_1\end{pmatrix}为不可观测的虚拟变量（隐含因子），可理解为驱动\begin{pmatrix}y_1\\y_2\\y_3\\\end{pmatrix} 变化的主要因子；\\
& \begin{pmatrix}z_1\\z_2\\z_3\\\end{pmatrix}为系数矩阵，表示\begin{pmatrix}x_1\end{pmatrix}对\begin{pmatrix}y_1\\y_2\\y_3\\\end{pmatrix}的直接影响；\\
& \begin{pmatrix}a_1\\a_2\\a_3\\\end{pmatrix}为不可观测的虚拟变量，可理解为\begin{pmatrix}y_1\\y_2\\y_3\\\end{pmatrix} 的截距；\\
&\begin{pmatrix}v_1\\v_2\\v_3\\\end{pmatrix}为残差，服从期望值为0的多元正态分布。
\end{align*}
$$

$$
\\公式② \ \ \ \begin{pmatrix}\begin{pmatrix}x_1\end{pmatrix}_t^{'}\\ \begin{pmatrix}x_1\end{pmatrix}_{t-1}^{'}\\\begin{pmatrix}x_1\end{pmatrix}_{t-2}^{'}\end{pmatrix} = \begin{pmatrix}b_{11}&b_{12}&b_{13}\\1&0&0\\0&1&0\end{pmatrix} \begin{pmatrix}\begin{pmatrix}x_1\end{pmatrix}_{t-1}^{'}\\ \begin{pmatrix}x_1\end{pmatrix}_{t-2}^{'}\\ \begin{pmatrix}x_1\end{pmatrix}_{t-3}^{'}\end{pmatrix}+\begin{pmatrix}u_1\\0\\0\end{pmatrix}+\begin{pmatrix}\begin{pmatrix}w_1\end{pmatrix}_{t}\\0\\0\end{pmatrix}\\
 \begin{pmatrix}\begin{pmatrix}w_1\end{pmatrix}_{t}\\0\\0\end{pmatrix}\sim MVN[0,\begin{pmatrix}q_{11}&0&0\\0&0&0\\0&0&0\end{pmatrix}]，\begin{pmatrix}\begin{pmatrix}x_1\end{pmatrix}_0^{'}\\ \begin{pmatrix}x_1\end{pmatrix}_{-1}^{'}\\ \begin{pmatrix}x_1\end{pmatrix}_{-2}^{'}\end{pmatrix}\sim MVN(\pi,\Lambda)\\
\begin{align*}
& 该公式表示因子\begin{pmatrix}x_1\end{pmatrix}之间在各时间点的交互作用，x_1为三阶自回归，其中：\\
& \begin{pmatrix}x_1\end{pmatrix}_t为t时间点的因子数值，\begin{pmatrix}x_1\end{pmatrix}_{t-1}为t-1时间点的因子数值；\\
& \begin{pmatrix}b_{11}&b_{12}&b_{13}\\1&0&0\\0&1&0\end{pmatrix}是因子之间的转化系数矩阵；\\
&\begin{pmatrix}u_1\\0\\0\end{pmatrix}为因子向量的截距，可理解为增长（大于0）或下降（小于0）趋势；\\
&\begin{pmatrix}\begin{pmatrix}w_1\end{pmatrix}_{t}\\0\\0\end{pmatrix}为残差项服从期望值为0的多元正态分布。
\end{align*}
$$



####　2 通胀因子

##### 2.1 公式

$$
公式① \ \ \ \begin{pmatrix}y_1\\y_2\\\end{pmatrix} = \begin{pmatrix}z_1\\z_2\\\end{pmatrix}*
\begin{pmatrix}x_1\end{pmatrix}_t+\begin{pmatrix}a_1\\a_2\\\end{pmatrix}+\begin{pmatrix}v_1\\v_2\\\end{pmatrix}_t
\\
\begin{pmatrix}v_1\\v_2\\\end{pmatrix}_t\sim MVN[0,\begin{pmatrix}r_{11}&r_{12}\\r_{21}&r_{22}\\\end{pmatrix}]
\\
\begin{pmatrix}y_1\\y_2\\\end{pmatrix} 为可观测的目标变量,包括CPI、PPI，其中存在缺失数据；其他同上。
$$

$$
公式② \ \ \ \ 同上。
$$



