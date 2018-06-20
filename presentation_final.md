
<!-- page_number: true -->

# 带有输入饱和时滞系统的局部镇定问题
## 答辩人：戴明
## 导师：周彬
 ---
# 本毕业论文取得的主要成果
* 提出了多组决策向量独立优化的思路，可显著降低带有饱和环节的吸引域估计的保守性。
* 提出了两种基于Razumikhin以及Krasovskii的方法，对带有输入饱和时滞系统的局部镇定问题进行相应分析，给出了四条定理。
* 给出上述四种定理的数值仿真，并对比，得到时滞常量与吸引域大小的定量刻画

---
# 输入饱和系统的方法改进
$\dot{x}(t)=Ax(t)+B\sigma(Fx(t))$
Hu Tingshu LMI 方法：

 $\begin{bmatrix}
\gamma &X_r^T\\
X_r&Q
\end{bmatrix}\geq 0$
 $(A+BD_iF)Q+Q(A+BD_iF)^T+BD_i^- G+(BD_i^- G)^T<0$
 $\begin{bmatrix}
1&G_i\\
G_i^T&Q
\end{bmatrix}\geq 0$

优化目标为最小化$\gamma$

---
# 输入饱和系统的方法改进
决策向量的说明
![](figures/forPPT/describeAlpha.png)
> 一个决策向量对应一个优化解

---
# 输入饱和系统的方法改进

算法:
* 在$0-\pi$上将角度$n$等分，获得$n$个决策向量$X_{ri}$。
* 对应Hu中的LMI方程组分别带入$X_{ri}$进入求解，获得吸引域估计的解$\Omega(Q_i,1)$。
* 将上述的所有的$\Omega(Q_i,1)$取并集，并将其并集作为新的吸引域估计集合。

---
# 改进结果

![](figures/forPPT/mutiDv.png) ![](figures/forPPT/multiDvSim.png)

---
# 研究系统说明
系统设定为：
$\left\{
\begin{aligned}
&\dot{x}(t)=Ax(t)+B\sigma(Fx(t-\tau)), & t>0\\
&x(s)=\phi(s),& s\in[-\tau ,0]
\end{aligned}
\right.$

考虑到如下变换：
$M^{ T} A M=\begin{bmatrix}
A^+ & 0 \\
0 & A^-
\end{bmatrix}$

> 假设所研究的系统的所有极点都在右半平面

---

# 主要研究结果

* 根据Razumikhin定理提出两种判据
* 根据Krasovskii定理提出两种判据

---
# Razumikhin 方法一

$\dot{x}(t)=Ax(t)+B\sigma(Fx(t-\tau))$


<font size="3"> 
  
* $\begin{bmatrix}
\frac{1}{\alpha^2}&X_r^{T}\\
X_r&Q
\end{bmatrix}\geq 0$

* $\begin{bmatrix}
1&G_i\\
G_i^{T}&Q
\end{bmatrix}\geq 0$
 
* $(A+BD_iF)Q+Q(A+BD_iF)^{T}+BD_i^-G+(BD_i^-G)^{T} +\tau \rho BD_iF(M_1+M_2)F^{T}D_i^{T}B^{ T}+2\tau Q \le 0$
 
* $\begin{bmatrix}
Q & (AQ+BD_i^-G)^{T}\\
*& M_1
\end{bmatrix} \geq 0$

* $\begin{bmatrix}
Q & (BD_iFQ)^{T} \\
*& M_2
\end{bmatrix} \geq 0$

</font>

<font size="5">
  
> $Q,M_1,M_2$为正定矩阵，$X_r$为决策向量
   
</font>

---

# Razumikhin 方法二

$\dot{x}(t)=Ax(t)+B\sigma(Fx(t-\tau))$

<font size="3">
  
* $\Pi^* \le 0$
* $\begin{bmatrix}
\frac{1}{\beta^2}&X_r^{T}\\
X_r&Q
\end{bmatrix}\geq 0$
* $\begin{bmatrix}
1&G_i\\
G_i^{T}&Q
\end{bmatrix}\geq 0$

</font>

<font size="4">
其中
</font>

<font size="3">

$
\Pi^*=\begin{bmatrix}
\nu^* & -BD_iFAQ &-BD_iFBD_iFQ\\
*& -\alpha_1 Q & 0\\
*& *& -\alpha_2 Q
\end{bmatrix}$

$\nu^*=\frac{1}{\tau}\left[(A+BD_iF)Q+Q(A+BD_iF)^{T}+BD_i^-G+(BD_i^-G)^{T}\right]+(\alpha_1+\alpha_2)\rho Q
$

</font>

$Q$为正定矩阵，$\alpha_1$,$\alpha_2$,$\beta$为正数，且$\rho>1$，$X_r$为决策向量


---

# Krasovkii 方法一

$\dot{x}(t)=Ax(t)+B\sigma(Fx(t-\tau))$

<font size="3">
  
* $\begin{bmatrix}
S_*-R_*+AQ+QA^{T}+BD_i^-G+(BD_i^-G)^{T}&P_*+QA^{T}-Q&R_*+BD_iFQ\\
*& \tau^2R_*-Q-Q^{T} &  BD_iFQ\\
*& * & -(S_*+R_*)
\end{bmatrix}\le 0$

* $\begin{bmatrix}
P_*+\tau S_*+\frac{\tau^3}{2} R_* (A^{T}A+F^{T}B^{T}BF) & G_i^{T} \\
 *& 1
\end{bmatrix} \geq 0$

* $\begin{bmatrix}
\chi_Q I & \epsilon I \\
*& I + \epsilon(Q+Q)
\end{bmatrix}\geq 0,\forall \epsilon \ge 0$

* $P_*+\tau S_* + \frac{\tau ^3}{2} R_* ( A^{T} A + F^{T} B^{T} BF)\leq \chi_y I$

</font>

其中
$P_*$，$R_*$，$S_*$为正定矩阵，$\chi_y$，$\chi_Q$为正数。

> 优化目标为$\chi_y+\chi_Q$最小时，所求得的吸引域估计最大。

---

# krasovskii 方法二

$\dot{x}(t)=Ax(t)+B\sigma(Fx(t-\tau))$

<font size="3">
  
* $\Xi^*\le 0$
* $\begin{bmatrix}
Q+\frac{\tau^2}{2}(S_1^*+S_2^*) & G_i^{T}\\
*& 1
\end{bmatrix} \geq 0$
* $\begin{bmatrix}
\chi_Q I & \epsilon I \\
*& I + \epsilon(Q+Q)
\end{bmatrix}\geq 0,\forall \epsilon \ge 0$
* $Q+\frac{\tau^2}{2}(S_1^*+S_2^*) \leq \chi_y I$

<font size="5">

其中  

</font>

$\Xi^*=\begin{bmatrix}
\nu &  BD_iFAQ &  BD_iFBD_iFQ\\
*& -S_1^* & 0\\
*& * & -S_2^*
\end{bmatrix}$

$\nu=\frac{1}{\tau}((A+BD_iF)Q+Q(A++BD_iF)^{T}+BD_i^-G+(BD_i^-G)^{T})+S_1^*+S_2^*$

$Q$，$S_1^*$，$S_2^*$均为正定矩阵，$\chi_Q$为正数

</font>

---

# 数值仿真

![](figures/forPPT/contrast.png) ![](figures/forPPT/delay_Nodelay.png)

---

# 椭圆面积公式

### 命题：
矩阵$P$为$2\times 2$的正定矩阵，对于广义椭圆方程$x^{T}Px=1$所表示的椭圆，其椭圆面积计算公式为：

$S=\pi \sqrt{\frac{1}{\lambda_1 \lambda_2}}$

其中$\lambda_1$，$\lambda_2$为矩阵$P$的特征值。

---

# 吸引域大小与时滞常数的关系

![](figures/forPPT/area_for_delay_constant.png)

> NOTE: 所选取的吸引域估计的计算方法为Krasovskii方法一

---
THANKS :+1: