# 电子技术基础课程整理（未完待续）

### 这里是助教cx（

---

## 关于本指北

> 这是我一个人整理的简易版笔记，是站在我自己的角度对课程内容的梳理，可能有所偏向，不一定适合所有人。如果你只看这一个文档复习，可能部分知识点会有所欠缺。建议同学们还是以书本和老师讲义or课件为准。参考了一些资料（见文末）。如有疑问，请及时联系我。

## 关于课程

> 《电子技术基础》（3学分）是今年新改的课程，主要讲授电路分析的基本理论和模拟电子线路也就是模电两个部分，课程上大致按照1+2来上，课时应该说是***非常紧张***的。以前在物院是2+2，也就是2学分理论2学分模电，被公认为是物院培养方案里最屑的必修课 ~~（虽然现在可能还是）~~ 。但是要学完这些模电的基本内容，3学分的课时也未必是足够的，1学分的分析理论更是一带而过（看到那两本白皮了吧，可能五六个星期就讲完了）。如果你想要学好模电，那么课内的学习大抵是不够的，课下还需要多花时间，不要只是当成是一门3学分的课来学。如果你每节课都能跟上老师的节奏，课后辅以适当的练习，悟到了这门课的精髓，我想模电还是比较有意思的，前前后后看似无关的电路里有着紧密的联系（好像有点扯，但是你真的学懂了可能会发现记忆量大大下降了）。如果你只是想水过这门~~屑~~课，那么你可以选择考前突击（`可以但不建议`，突击过的人都说模电的突击难度很大），疯狂背结论之类的，考试的分析套路应该还是相对固定的。个人认为本课程的单个知识点难度不大（相比一些数学、物理课），难度在于课程体量，大量灌输新的概念，需要大家有预先准备。

## 关于助教

> 助教本人陈翔，是20级少年班学院本科生，现在就读于光学系。我在21秋修的《电子线路》课程（不是顾里的电子线路），当时我们是1+3。当时在学习模电的时候我也遇到过一些困惑，也遇到不知所措被整破防的时候。但是最后还是挺过来了，在一次次训练中也逐渐加深了对模电的理解，感觉能朦胧地体会到了一点逻辑。这门课深得物批讨厌（x，而且助教通常是研究生（个人感觉研究生助教通常比不上本科生助教，可能是由很多因素导致的），一般助教和班上的同学交流很少，课程群很沉默很少讨论，当然这也可能是课程的原因，这样对这门课的学习就更加的不利，从而陷入恶性循环。我希望能对这样这样的局面做出一点改变，当然也不好说我能做到多少，只能说尽力而为吧。也或许是因为这些原因 ~~（也或许是以后进电子厂打工要用到模电）~~，我申请了这门课的助教，有缘和同学们在这个课堂相见，我们共同勉励，一起进步。

不多言，我们进入正题。

---

# 电路基本理论部分

> 电路基本理论主要是介绍分析集总参数电路的一些常用方法，为我们后续学习模电做铺垫。

> 电路分析的典型问题：给定电路结构，元件特性以及各独立源（输入），求解电路中未知的电流电压。

## 第一章 电阻电路分析基本理论

### 1.1 集总参数
- **集总参数**，指<u>器件的尺寸 $L$ 远小于工作信号的波长 $\lambda$</u>，即
  $$L\ll\lambda=\frac{c}{f}$$
- **集总电路**：<u>由集总参数元件构成的电路</u>。分为**电阻性电路**和**动态电路**。
  
  这意味着我们不需要考虑能量传送的过程。

  对应的，有**分布参数**，即远小于关系不满足时，此时需要考虑能量的传输和电磁场沿着传播方向导线分布等。（[这里放一个视频，感兴趣的同学可以看看](http://b23.tv/k0UowSe)）

本课程只需考虑集总参数情况下电路的分析。本章讨论电阻性电路的分析。

### 1.2 电压，电流及功率$\star$
- 注意电流的**参考方向**和电压的**参考极性**！`没有定义方向的电流和没有定义极性的电压是没有意义的`。如果没有正确理解这一概念，接下来的学习可能会产生较大的困难。
- **关联参考方向**：<u>电流方向与电压降方向一致</u>。
- **功率参考方向**代表<u>能量的传输方向</u>，`与电流电压是否关联有关`。如选择关联参考方向，则吸收功率为正，即
  $$p(t)=+u(t)i(t)$$
  如功率为负，则表示提供功率。（实在记不住或者容易绕晕了，就画一个电流通过一个电阻，这样你自然会选择关联参考方向，并且知道此时吸收功率是正值）

### 1.3 基尔霍夫定律$\star\star\star$
- **基尔霍夫电流定律（KCL）**（即流入等于流出）是电流的线性约束。
  
  这里可以把节点延伸为任意封闭面（超节点）。

- **基尔霍夫电压定律（KVL）** 是电压的线性约束。

  - <u>每个二端元件</u>为一个**支路**，<u>支路的连接点</u>为**节点**，<u>电路中任意闭合路径</u>为**回路**，<u>回路内部不另含有支路的回路</u>（与实际电路画法相关）称为**网孔**。
  - 基尔霍夫定律的前提假设是集总电路。
  - 支路电压的**双下标记法**（<u>电压降方向</u>）

### 1.4 一些元件
- **电阻元件** 提供元件上电流电压关系的约束。
  - <u>遵循欧姆定律的电阻元件</u>，称为**线性电阻元件**。
  - 伏安特性曲线（$U-I$ 曲线）
  - 电阻元件具有无记忆性，与动态元件相对应。
  - 电阻的两个分类（线性/非线性，时变/时不变）
  - 电阻的单向性/双向性
- **电压源和电流源** 
  - 电压源和电流源合成**激励源**，与**受控源**相对。
  - 我们总是默认是理想源，即没有内阻。
  - 我们一般总是规定<u>直流量大写</u>即 $U_S,I_S$，<u>交流量小写</u>即 $u_S(t),i_S(t)$。之后也一样！
  - `注意电压源并联的部分和电流源串联的部分对其他部分电路没有贡献！`这一点有助于我们化简对电路的分析过程。
- **受控源**
  - 受控源是<u>双口元件，包含控制支路和受控支路</u>。用菱形表示。只是我们一般为了方便把两个支路分开画。
  - 四种受控源：VCVS，CCVS，VCCS，CCCS。（控制支路不是开路就是短路）
  - **转移特性**，是<u>输出量和输入量之间的关系，也是一种元件约束关系</u>。我们一般只讨论线性受控源。

### 1.5 分压与分流
- 分压分流公式不难，主要是习惯分压电路的节点画法，以后会经常碰到。

### 1.6 两类约束与方程独立性
- **拓扑约束**：<u>只取决于互联形式的约束</u>。
  - 基尔霍夫定律，即 KCL，KVL 等。
- **元件约束**：<u>只取决于元件本身性质的约束</u>。
  - 如伏安特性，传输特性等。
- 关于约束的独立性和完备性
  - <u>两类约束是解决集总电路分析问题的基本依据。</u>
  - $n$ 个节点的 KCL 方程中任意 $n-1$ 个是独立的。
  - $b-n+1$ 个内网孔的 KVL 方程是独立的。
  - $b$ 个支路上的元件约束
  - **2b法**

## 第二章 电阻电路分析方法和定律

### 2.1 支路分析
- **1b 法**：只设支路电流/电压，直接将元件约束代入，减少方程数量。
- **支路电流法**和**支路电压法**

### 2.2 网孔分析
- **网孔电流法**：假设出各网孔电流，<u>*该假设已经利用 KCL*</u>，减少方程数量至 $b-n+1$。
- ⚠️`网孔电流法写 KVL 时，绕行方向最好与电流假设方向一致，一定要留意相邻网孔电流的方向，方程右边电压源`**`电压升`**`为正方向！`
- **自电阻**和**互电阻**
- *注意网孔选择需要避开电流源*！（或*直接利用电流源设网孔电流*）

### 2.3 节点分析$\star\star$
- **节点电压法**：假设各节点电压，<u>*该假设已经利用 KVL*</u>，减少方程数量至 $n-1$。
- 注意*节点间的互电导为负*，方程右端为`输入节点的电流`代数和。
- 节点电压法可以用于非平面结构的电路，而网孔电流法不太好办。
- 节点电压法和网孔电流法遇到受控源时都可以代入对应约束方程当作独立源处理。

### 2.4 **叠加原理**$\star\star\star\star$
- **激励**和**响应**
- **叠加原理**：<u>在`线性网络电路`中，每一处响应总可以看成激励单独作用于电路时产生的响应之和。</u>
  - 这里有一个重要的假设：**线性性**
  - 叠加性是线性电路的根本属性。（线性对应可叠加，在所有地方都普适！）
  - 注意：*电压源置零为零电压即短路，电流源置零为零电流即开路*。
  - 注意：电流和电压可以叠加，*功率一般不能叠加*。
  - 注意：*受控源不是激励*，不需要置零。
  - 记忆方法：把圆框擦掉。
- 我认为，*叠加原理是我们线性模拟电路分析的重要基础之一*。我们在模电里会利用这一原理进行直流交流分解分析。晶体管的小信号模型，就是在做网络线性化。

### 2.5 分解方法和等效定理
- 分解方法可以化繁为简，将结构复杂的电路分解为结构简单的电路进行求解。可适用于非线性电路。
- **单口网络**（又叫**二端网络**）与**双口网络**
- 确定**单口网络的电流电压约束关系 VCR**（伏安特性曲线）or 等效电路
  
  可以采用*外加电流源或者电压源*的方法求解。

  一般我们求解的都是线性网络，这时网络的 VCR 可以表示为
  $u=A+Bi$
  的形式。
- **等效**：<u>网络对*任意*外电路等效，即 VCR 全等。</u>
- **置换**：<u>网络对特定的电路下，置换为一个简单源而不改变当前的内电路状态，即工作点相同的替换。</u>
- **单口网络的置换定理**，将两个网络分别用电压源（或电流源）置换，从而分别求解。可以置换非线性电路，只要工作点相同。
- 电压源串联和电流源并联。再次注意`与电压源并联部分和与电流源串联部分如果不是研究对象，是`*`多余元件`*。这里我们可以从等效的观点来看。
  
  下面是两个重要的等效定理$\star\star\star$
- **戴维南定理**
- **诺顿定理**
- **含源线性单口网络**总是可以等效为一个戴维南等效电路或者是诺顿等效电路。我们可以直接利用求`开路电压、短路电流和等效内阻`中的任意两个来确定网络的 VCR 关系，进而确定等效电路。注意`求等效内阻时，独立源全部置零，受控源要保留`。注意参考方向不能改变。
- 最大功率传输定理。外阻等于内阻时输出功率最大，但是功率传输效率不是最大。
-  $T$ 型 - $\Pi$ 型网络等效变换（$Y$-$\Delta$ 等效变换）观察变换式的对称性比较容易记忆。

## 第三章 动态电路的分析方法

### 3.1 动态元件
- 动态性，**记忆性**（就不详细写了，就是积个分的事情，注意`依赖于初始条件`）
- **电容元件**
  - VCR（*关联参考方向下*）
  $$i(t)=C\frac{\mathrm{d}u}{\mathrm{d}t}$$
  - **电容电压连续性**：$u_C(t_-) = u_C(t_+)$
  - 记忆性使得电容上的初始电压可以等效为一个无状态电容串联一个等压的电压源。
  - 电容储能：$w_C(t) = \frac{1}{2}Cu(t)^2$

- **电感元件**（说明参考电容）
  - VCR（*关联参考方向下*）
  $$u(t)=L\frac{\mathrm{d}i}{\mathrm{d}t}$$
  - **电感电流连续性**
  - 记忆性等效
  - 电感储能：$w_L(t) = \frac{1}{2}Li(t)^2$
- 电容电感的**对偶性**
- **状态变量**：<u>电容电压 $u_C(t)$ 和电感电流 $i_L(t)$</u>
  
  他们是最少的能确定电路状态的变量。
- 电容电感的串并联

### 3.2 时域分析法：一阶电路
- *求解一阶电路的本质就是解一阶线性常微分方程！* 这边建议先回去复习一下一阶线性常微分方程怎么解。我们在这里碰到的大概率是常系数的方程，可以说是最简单的一种微分方程了。
  
  我们以电容方程为例（电感方程有同样的形式）
  $$\tau\frac{\mathrm{d}u_C(t)}{\mathrm{d}t}+u_C(t)=u_{OC}(t)$$
  这里**时间常数** $\tau=RC$。这个方程在 $u_C(0)=u_0$ 的初始条件下的解为
  $$u_C(t) = \left(u_0 + \frac{1}{\tau} \int_0^t u_{OC}(\xi)e^{\xi/\tau} \,\mathrm{d}\xi\right)e^{-t/\tau}$$

- 既然是线性方程，我们又可以请出我们最喜欢的`叠加原理`来了。叠加原理告诉我们，我们可以把这样一个方程的解写成初始条件归零的解和非齐次项归零的解的叠加，也就是**零状态响应**和**零输入响应**。这两种响应之和称为**全响应**。
- 叠加原理！！！注意初始状态不能叠加。
- **时间常数** $\tau=RC$ 或 $\tau=L/R$ 表征了响应衰减的速度，是一阶电路中的重要参数（是全局的）。
- 经典的零状态响应 $u_C(t) = U_S(1 - \mathrm{e}^{-t/\tau})$，零输入响应 $u_C(t) = u_C(0) \mathrm{e}^{-t/\tau}$
- **阶跃函数** $\varepsilon(t)$ 和**冲击函数** $\delta(t)$
- 注意零状态响应和输入才有线性关系，*全响应没有直接的叠加原理*。零状态响应和零输入响应各自满足叠加原理。（对谁线性？）
- **三要素法**：$y(0_+),y(\infty),\tau$ 
  - 电容变 $u_C(0)$ 的电压源，电感变 $i_L(0)$ 的电流源，即得初态电路，求解 $y(0_+)$
  - 电容开路，电感短路，即得稳态电路，求解 $y(\infty)$
  - 直接写出结果 $y(t) = y(\infty) + [y(0_+) - y(\infty)] \mathrm{e}^{-t/\tau},\; t>0$
- **瞬态响应**和**稳态响应**：前者是随时间指数衰减的项，后者是随时间不变的项，分别对应三要素法中的第二项和第一项。

### 3.3 相量分析法
- **正弦波激励**：正弦交流电压/电流。一般写作`余弦` $u(t)=U_m\cos(\omega t+\phi)$。更一般的激励都可以通过傅立叶展开分解为正弦波的叠加，从而进行分析。所以下面我们只需讨论正弦波激励都情况，也就是**正弦稳态电路**。
- 变换的概念：频域分析
- **相量**，即**振幅相量**，<u>是一个与时间无关的常数 $\dot{U}_m$ 或 $\dot{I}_m$</u>。
  
  我们知道，电路中一个正弦的激励，对应的响应也是正弦的，并且应当是同频的。那么我们就可以用两个参数来描述这样一个正弦信号：振幅 $U_m$ 或 $I_m$ + 相位 $\theta$。更简单一些，我们用一个复参数来描述，也就是相量 
  $$ \dot{U}_m = U_m \mathrm{e}^{\mathrm{j} \theta} = U_m \angle\underline{\theta} $$

- 相量的运算
- 我们这里变换的方法，其实是在相量和正弦量之间建立了对应关系，即 $\dot{U}_m \Leftrightarrow u(t)$。这里要注意相量和正弦量是不一样的，他们只是同构表示，*不能直接划等号！*
- 相量同样具有线性性，<u>基尔霍夫方程组（KCL 和 KVL）可以直接拓展到相量形式</u>。
- 通过相量我们可以把三种基本电路元件的 VCR 方程统一起来。
  
  引入**阻抗**，表示<u>元件在正弦稳态时电压相量和电流相量之比</u>
  $$ \dot{Z} = \frac{\dot{U}_m}{\dot{I}_m} $$
  VCR 被统一为**欧姆定律的相量形式** $\dot{U}_m = \dot{I}_m \dot{Z}$。其中
  $$ \dot{Z}_R = R,\; \dot{Z}_C = \frac{1}{\mathrm{j} \omega C},\; \dot{Z}_L = \mathrm{j} \omega L $$
  至此，所有内容全部划归为纯电阻网络分析/静态分析。

- 我们有时候为了方便会使用**有效值相量**，尤其是在讨论功率的时候。注意有效值相量没有下标 $m$，和振幅相量差了 $\sqrt2$ 倍，即 $\dot{U}_m = \sqrt2 \dot{U}$。

---

# 模拟电子线路（模电部分）

> 然后我们就来到了~~好玩的~~痛苦的模电部分。我们课程的模电部分主要讲授**放大电路**（*非常重要*，可能要占主要课时，包括三大电路，差分放大，集成运放等），**反馈电路**（重要），后面的振荡电路，信号发生，整流滤波，功率放大等课程内不做要求，我也就没写。（摆

> 这里我不打算按照课本顺序讲，而是按照我觉得更舒服更合理的顺序讲。~~（个人感觉课本顺序比较垃圾）~~

### 什么事模电？
在学习模电之前，首先要知道我们在学什么。
- **模拟信号**：<u>时间和幅值上都连续的信号</u>。与之相对的数字信号在时间和取值上都离散。
- **模拟电路**：<u>处理模拟信号的电子电路</u>。

放大电路是模电的核心。模拟电路经常需要把一个比较小的物理量（的变化）检测出来，并进行处理，比如粒子探测器。如果没有直接进行放大，很可能会直接被噪声淹没。

我们会碰到的模拟电路（分析，甚至可能是设计，不过本课程不做要求，但是某些方向的实验人是会在科研中碰到的）通常是一个大的集成电路。我们去做拆解，通常把这样的模拟电路分解成小的电路功能模块。而为了分析电路模块的功能，我们又需要从简单器件着手。这样我们把整个电路的架构一点点拆开，再通过学习的过程不断搭建起来，就会比较有框架感。


## 第四章 半导体与器件

### 4.1 半导体
需要了解器件的性质，我们就需要从半导体的性质开始讲起。我们通常采用的都是硅基半导体，在硅上掺杂其他元素。我们知道硅是四价元素，我们在硅中掺杂三价元素（如硼）或者五价元素（如磷）就可以分别得到 **P 型半导体**和 **N 型半导体**。~~不要以为P型是掺杂磷的~~

- **多子**，即多数载流子；**少子**，即少数载流子。
- P 型半导体多子是空穴，少子是电子；N 型半导体多子是电子，少子是空穴（ P 即 positive，多子带正电；N 即 negative，多子带负电）

### 4.2 PN 结与二极管
#### 4.2.1 PN 结
PN 结的形成来自于载流子的漂移运动和扩散运动。其实漂移和扩散只不过是载流子运动的分解，分成了定向的运动和无规则的运动。
- **漂移**：<U>电场作用下载流子的运动</U>。注意这里的电场是内电场+外电场。
- **扩散**：<u>载流子高浓度向低浓度的扩散运动</u>。

现在我们把 P 型半导体和 N 型半导体贴在一起，交界处的电子和空穴复合，形成了**空间电荷区**（**耗尽层**）。此时内部形成由 N 区指向 P 区的内电场，促进少子漂移。最终漂移和扩散达到平衡，形成 PN 结。其中 P 为正极，N 为负极。

- PN 结的单向导电特性
  - 外加正向电压，抵消内电场的作用，漂移作用减弱，平衡向着耗尽层变窄的方向移动，加到特定电压时耗尽层消失，PN 结正向导通。
  - 外加反向电压，增强内电场的漂移作用，平衡向着耗尽层变宽的方向移动，PN 结反向截止，此时只有微弱的少子漂移产生的**反向饱和电流** $I_\mathrm{S}$。
  - 再加反向电压到**反向击穿电压** $V_\mathrm{BR}$，PN 结会被**反向击穿**。分为不可控的**雪崩击穿**和可控的**齐纳击穿**。
- PN 结的 $I-V$ 特性。在没有反向击穿的情况下可以表示为 
  $$ i_\mathrm{D} = I_\mathrm{S} (\mathrm{e}^{v_\mathrm{D} / n V_T} - 1) $$
  通常，$n=1,V_T=26\,\mathrm{mV}$。

  *PN 结的 $I-V$ 特性图需要牢记，~~我比较懒这里就不放上来了~~*

#### 4.2.2 二极管
大可以直接认为二极管就是个 PN 结。
- 二极管分为面接触型和点接触型。面接触型常用于大功率的，比如整流；点接触型一般用于高频和数字电路。
- 二极管的 $I-V$ 特性，还是那个图（
- 特殊二极管
  - 齐纳二极管，即**稳压管**。特点：面接触，能通过大电流；只工作在反向击穿区域（齐纳击穿）。利用反向击穿特性 $V_Z$ 稳压，在电路中只反接，有一定的工作区间（$I_\mathrm{Zmin}-I_\mathrm{Zmax}$）。（记住稳压二极管的符号，图略）

#### 4.2.3 二极管简化模型与分析方法
动机：为了线性化，以适应我们的分析理论！
- **理想模型**，简单好用，但是比较粗糙
- **恒压降模型**，在二极管电路里面非常常用。一般硅管的恒压降取 $0.7\,\mathrm{V}$
- **折线模型**，考虑了动态电阻，但是略复杂

二极管电路的分析方法和三极管几乎没区别，学完三极管的回来看二极管感觉太 trival 了，这里就直接不讲了。这里只讲二极管在开关电路中的分析方法。

二极管开关的分析至关重要，分析出电路中二极管是导通or截止，电路分析就已经完成了大半。记住我们总是*先假设二极管断开*。这时候看二极管两端的压降，再判断二极管有没有导通（和开启电压即压降比较）。

二极管电路的应用：整流，开关，限幅钳位，保护，稳压……


### 4.3 双极结型三极管 BJT
我们更多用到的器件是三极管而非二极管。简单的说，三极管就是两个背靠背的 PN 结接起来的。三极管在模电和数电里都是非常基本的器件，但是因为用途不同，要求的性质就不一样，制作的工艺也会有所不同。（底层逻辑就是制作方法决定器件性质，器件性质决定用途。）在模电里，我们通常更关心的指标是 BJT 的放大倍数 $\beta$。

三极管分为 BJT 和 MOSFET。现在后者的应用更广泛，但是本课程对前者的要求更高。我们先从 BJT 开始讲起。

#### 4.3.1 BJT 基本构造
- BJT 分为 PNP 型（两个 P 夹一个 N）和 NPN 型（两个 N 夹一个 P）。*以下除非特殊说明，我们下面讨论默认以 NPN 型管为例*（这个箭头是朝外的），*但是考试有可能出 PNP*（这个箭头是朝里的）*！*。
- 三个半导体区引出电极分别为**发射极**e，**基极**b，**集电极**c，对应区域为**发射区**，**基区**，**集电区**。三个区域构成的两个 PN 结分别为**发射结**和**集电结**。
- 三个区域的工艺特点：<u>集电结面积远大于发射结；基区掺杂浓度低，发射区掺杂浓度高。</u>这一内部结构特点决定了 BJT 的外部特性。

#### 4.3.2 BJT 的放大原理
放大的具体过程，哪个电流哪个电流不需要掌握，只需要知道一个大概的物理过程，为什么会有放大这一回事就行了。
- NPN 管的发射结（作为一个 PN 结）加正向偏置时，高掺杂的发射区的会向基区发射大量电子。但是基区薄，掺杂浓度低，只能复合少量的电子，大量电子穿过基区。反偏的集电结使得电子能够到达集电极，最终输出。
- BJT 起放大作用的前提是<u>发射结正偏，集电结反偏</u>！
- 最终三极电流关系满足 $ I_\mathrm{B} + I_\mathrm{C} = I_\mathrm{E},\; I_\mathrm{C} = \beta I_\mathrm{B} $。

#### 4.3.3 BJT 的 $I-V$ 特性
我们之前讨论伏安特性的时候，总是讨论的是二端元件。二端元件只有一个电流和电压的概念。但是 BJT 是一个三端元件。我们需要用多个关系来刻画这样的器件的伏安特性。

通常我们用输入输出特性来刻画 BJT 的 $I-V$ 特性。这里我们只讨论共射的 $I-V$ 特性（连接方式见课本）。两个特性曲线也需要大家翻到课本仔细看看。
- **输入特性**曲线 $ i_\mathrm{B} = f(v_\mathrm{BE})|_{v_\mathrm{CE}} $
  
  注意这是以 $v_\mathrm{CE}$ 为参变量的一族曲线。在 $v_\mathrm{CE} = 0$ 时这其实就是两个并联的 PN 结的特性曲线。随着 $v_\mathrm{CE}$ 增大，集电结反偏，曲线右移。当 $v_\mathrm{CE} = 1\,\mathrm{V}$ 时，发射的电子几乎都被集电区收集，电流几乎不再减小。这里其实就变成了发射结一个 PN 结的特性曲线。一般我们默认采用硅管的数据，直接取 $V_\mathrm{BE} = 0.7\,\mathrm{V}$，即认为这里都是 0.7 处垂直的线。

- **输出特性**曲线 $ i_\mathrm{C} = f(v_\mathrm{CE})|_{i_\mathrm{B}} $
  
  输出特性曲线的图比输入特性曲线更重要一点。我们可以看到，这个图非常直观的把 BJT 的工作区分成了三个部分：**放大区，饱和区，截止区**。在模电里，我们只用到放大区用作放大器件。在数电里我们会使用饱和区和截止区来做开关器件。
  - 当 $i_\mathrm{B} \leqslant 0$ 时，发射结截止，集电极电流 $i_\mathrm{C}$ 很小，BJT 处于**截止区**。
  - 放大区又叫**恒流区**，在这里我们近似认为曲线平行于横轴（书上这个图应该是故意画陡了，别的书上看到好像更平一点），不管电压怎么变化，电流几乎都不变。这也就是说我们的 $V_\mathrm{CE}$ 是不能通过 BJT 元件方程本身确定的，而是需要外部的 KVL 方程。
  - 如果 $v_\mathrm{CE}$ 太小，集电极不能完全收集电子，那么电流 $i_\mathrm{C}$ 就达不到恒流区的大小，称为**饱和区**。
  
  `这个曲线非常重要，需要大家在脑子里有这个概念。`总结起来，还是那句话：放大区要求发射结正偏，集电结反偏！

### 4.4 场效应管 FET
本课程对场效应管的要求比较低，不要求掌握场效应管的具体放大电路的分析，但是一些基本的概念是需要了解的。（其实跟 BJT 也是比较相似）

首先我们需要知道场效应管的分类。
- **金属-氧化物-半导体场效应管** MOSFET，也叫**绝缘栅型场效应管**，简称 MOS 管
  - N 沟道 NMOS 管
    - 沟道型 D 型
    - 增强型 E 型
  - P 沟道 PMOS 管
    - 沟道型 D 型
    - 增强型 E 型
- **结型场效应管** JFET 
  - N 沟道耗尽型
  - P 沟道耗尽型

下面讨论 MOSFET。JFET 好像不考，不写了（）

#### 4.4.1 MOSFET
一开始上来这么多名词肯定直接晕了。我们先来解释一下命名规则，其实不过是排列组合罢了。
- N 型，多子是电子；P 型，多子是空穴。
- 增强型/耗尽型，描述在器件本身没有外加电压的情况下沟道是否存在。如果源极（S）和漏极（D）本身就存在导电沟道，就是耗尽型的，符号中间是实线。如果本身没有导电沟道，就是增强型的，符号中间是虚线。

我们将看到，与 BJT 不同，MOSFET 只有一种电荷导电，所以又称为**单极型**器件。

#### 4.4.2 MOSFET 的构造和工作原理
- 我们以 **N 沟道增强型 MOS 管**为例（图参考课本 P90）。我们在<u>低掺杂的</u> P **衬底**B 上生成两个<u>高掺杂</u>的 N 区（两个 PN 结由此产生），上面接金属电极，分别为**源极**S，**漏极**D。这里源和漏其实是对称的，不过我们习惯上认为D极电压高于S极（即上高下低）。再在衬底生长一层<u>二氧化硅绝缘层</u>，加电极，为**栅极**G。
- 当 $v_\mathrm{GS} = 0$ 时，没有导电沟道，DS 间相当于背对背的 PN 结，断开。当 $v_\mathrm{GS} > 0$ 时，金属吸引少子电子到表面。增大到**阈值电压** $V_\mathrm{TN}$，形成**反型层**，此时这里的 P 型半导体反转为 N 型半导体，这样就和两极连接成 N 型导电沟道。
  - 沟道是栅极电压电场感应产生的，所以又叫**感生沟道**。
  - 如果是耗尽型的，那么就是一开始导电沟道就存在，加了反向电压以后才会消失，*相当于在 $I-V$ 特性图上沿着 $v_\mathrm{GS}$ 平移*。
- 沟道产生以后，我们在 DS 上加电压。当 $v_\mathrm{DS}$ 增大时，导电沟道对电子来说是一个电阻，电流也随着电压增大。但是 $v_\mathrm{DS}$ 增大还会导致 $v_\mathrm{GD}$ 减小，这样 D 这一边的反型层会变窄。因为 D 和 S 对称，所以同样的，在 $v_\mathrm{GD} = V_\mathrm{TN}$ 时，导电沟道被**夹断**。夹断后再增大电压，电流 $i_\mathrm{D}$ 几乎不再增加。
- 夹断前为**可变电阻区**，夹断后为**恒流区**。临界夹断为 $v_\mathrm{DS} = v_\mathrm{GS} - V_\mathrm{TN}$。
- 恒流区，又叫**饱和区**，*注意和 BJT 不一样！*（因为饱和的东西不一样）

之所以称之为绝缘栅型，是因为栅极g 有二氧化硅绝缘层，$i_\mathrm{G} \approx 0$，故<u> MOSFET 的输入电阻很高</u>。

#### 4.4.3 MOSFET 的 $I-V$ 特性
与 BJT 相同，MOSFET 的伏安特性同样需要双口网络来刻画。因为有 $i_\mathrm{G}=0,\,i_\mathrm{D} = i_\mathrm{S}$，所以刻画方法与 BJT 有所不同，因为这里没有输入特性了。我们一般用输出特性和转移特性来描述。下面我们同样以 N 沟道增强型 MOS 管为例。
- **输出特性**曲线 $ i_\mathrm{D} = f(v_\mathrm{DS})|_{v_\mathrm{GS}} $

  同样需牢记。可以参考书上的图，我们可以看到 MOSFET 有着和 BJT 极其相似的输出特性曲线，同样有类似的三个区，所以我们同样可以让它工作在恒流区，来实现放大的功能。定性分析其实已经基本上在上面原理部分了，大家可以参考上面对 BJT 输出特性的分析和 MOSFET 原理的分析。

- **转移特性**曲线 $ i_\mathrm{D} = f(v_\mathrm{GS})|_{v_\mathrm{DS}} $
  
  是一个半抛物线。首先 $v_\mathrm{GS}$ 需要达到开启电压 $V_\mathrm{TN}$，然后才有导电沟道。在恒流区，$i_\mathrm{D}$ 基本上与 $v_\mathrm{DS}$ 无关，只取决于 $v_\mathrm{GS}$。

如果事耗尽型，那么只需要将出现 $v_\mathrm{GS}$ 的地方做一个平移，其他保持不变即可。如果是 P 沟道，只需要将坐标反向（图像反转180度）。

MOSFET 的放大电路不考，我们就不多介绍了，其实原理都是一样的，只不过细节上处理起来有些区别。但是他和 BJT 有一个重要的不同点，BJT 是电流控制电流，而 MOSFET 是电压控制电流。


## 第五章 基本放大电路

放大就是要把一个微小的交流信号放大变成一个比较大的我们更容易运算和控制的信号的过程，也就是输入一个比较小的信号，输出一个比较大的信号。我们通常放大都是**线性放大**，也就是我们的信号简单的做一个倍乘，波形保持原来的形状不变。如果输出得到的波形发生了形变，就叫做**失真**。

> 这里推荐大家稍微再翻一下课本的第四章，这里可能涉及了不少重要概念，但是我们是在第五章讲的，大家书上应该基本上没有笔记。大家可以特别留意着色加粗字体部分，通常是比较重要的概念。

### 5.1 放大电路基本概念
`注意下面几个概念都需要在微变等效电路下定义。`也就是说，这些电阻都是交流电阻（动态电阻）
- 增益
  
  一般我们的放大都是**电压放大**，放大倍数称为**电压增益**，通常用 $A_v = v_\mathrm{o}/v_\mathrm{i}$ 来表示，其中 $A$ 表示增益 (Amplification)，下标 $\mathrm{v}$ 表示电压，$v$ 的下标 $\mathrm{i}$ 和 $\mathrm{o}$ 表示输入和输出。这里我们注意到我们讲到了符号系统，这是因为工程上通常会固定下来一套习惯的记法。当然放大电路还有**电流放大**，**互阻放大**和**互导放大**。

  有时增益会用分贝来表示，$20\lg|A|\,\mathrm{dB}$。注意这里底数是10。比如强度衰减到原来的 $1/10$，就说增益是 $-20\,\mathrm{dB}$，$-3\,\mathrm{dB}$ 就是衰减到原来的一半。

  这里我们还会提到的一个概念就是**源放大倍数** $A_\mathrm{vs} = v_\mathrm{o}/v_\mathrm{s} = v_\mathrm{o}/v_\mathrm{i} \cdot v_\mathrm{i}/v_\mathrm{s} = A_v R_\mathrm{i}/(R_\mathrm{si} + R_\mathrm{i})$。他们的关系是 $v_\mathrm{i}$ 是把电源和源内阻看成输入，而 $v_\mathrm{s}$ 纯粹是源上的电压。

- 输入电阻
  
  $R_\mathrm{i} = v_\mathrm{i}/i_\mathrm{i}$

  `注意输入电阻中不会出现信号源内阻` $R_\mathrm{i}$，但是有可能出现负载 $R_\mathrm{L}$。

- 输出电阻
  
  $R_\mathrm{o} = v_\mathrm{o}/i_\mathrm{o} |_{v_s=0}$

  这里公式看着和上面的几乎一样。但是在做的时候，我们需要把电源断开，把负载拿掉，从输出端加上电压 $v_\mathrm{o}$，这样才是输出端看到的电流。

  `注意输出电阻中不会出现负载` $R_\mathrm{L}$

### 5.2 放大电路的分析方法
解决放大电路问题，其实本质上是需要解一个复杂的非线性方程，而且还是时变的。我们不可能去做严格求解。模电的精髓就在于估算（实则是没有精确计算的必要，在满足设计误差范围内可以使用就行了）。我们知道要防止信号失真，需要把工作点放在一个相对线性的区域，通过小信号近似让系统得以线性化，从而容易分析。除了我们在上面讲过的二极管的等效模型的分析，我们通常对放大电路的分析方法有**图解法**和**小信号模型**法。但是下面我们先了解一下放大电路通常进行的分解。

#### 5.2.1 直流分析和交流分析
我们在分析电路的时候，需要先将电路的激励分为直流部分和交流部分。根据叠加原理，我们知道这是合法的操作。这样的两步分析分别为**直流分析**和**交流分析**。

直流分析要求我们找到直流通路。**直流通路**就是指直流信号看到的电路。作出直流通路，首先我们把所有交流信号置零，即 $v_s=0$。然后把电容断开。最终得到了直流通路。我们围绕三极管求解就得到了静态工作点。
- 直流分析的目的是确定**静态工作点Q**。
- 注意我们直流分析的时候输入回路和输出回路都需要分析。一般先分析输入再分析输出，$I_\mathrm{BQ}$ 是输入输出的桥梁。

交流分析要求我们先找到交流通路。**交流通路**就是指交流信号能看到的电路。对于变化量来说，直流量都是0。我们要把所有直流量置零，包括恒压源恒流源。然后把（显示）电容短路。这样我们就得到了交流通路。得到交流通路是为了进一步分析放大电路的性质，包括增益，输入输出电阻等。最麻烦的事情出现了，我们发现交流通路里的 BJT 没法处理。这个时候我就需要下面的方法。

#### 5.2.2 图解法
图解法非常简单友好。它本质就是把方程分为线性部分和非线性部分联立求解，也就是把元件的伏案特性和外接电路的负载线画在一起，交点就是解。图解法的优点在于避免计算。图解法本身其实应该是直流分析交流分析一体的。

图解法有一个很大的好处就是在于可以帮助我们理解放大的物理过程，尤其是理解为什么说*动态是建立在静态之上的*。这里我们借助图解法理解几个概念。
- **直流负载线**，描述元件外接电路的特性（单口网络的 VCR）。因为他是线性的，所以应该是一条直线。其 $v$ 轴截距为电源电压，斜率为 $-1/R$
- **工作点**Q，指特性曲线和负载线的交点，也是电路的工作点。如果输入是一个直流量，那么这就是**静态工作点**，是在特性曲线上对应的一个点。
- 在我们的静态工作点上叠加我们的小信号，也就是在 Q 点附近震荡。注意这里不再是沿着直流负载线移动了，而是**交流负载线**。这里的原因是直流通路里的电阻和交流通路不一样，比如很多情况下直流通路是 $R_\mathrm{C}$，而交流通路是 $R_\mathrm{C}//R_\mathrm{L}$。也就是说，*交流负载线比直流负载线更陡*。所以*动态工作点是沿着交流负载线震荡的*。
- 当我们作图时发现静态工作点不合适，即偏低或偏高，很容易用图解法理解为什么会产生失真。因为此时的工作点已经偏离理想放大的线性区，产生非线性失真。Q 点过高产生**饱和失真**，Q 点过低产生**截止失真**。

#### 5.2.3 小信号模型法
小信号模型其实是交流分析时定量分析最常用的方法。注意他只能做交流分析。这里我们必须先知道，为什么会有小信号模型，小信号模型什么时候能用？

> 我们回忆电路分析理论部分。我们知道，我们会处理的电路模型是线性的。处理线性的电路模型，我能够使用我们学过的知识。非线性是非常麻烦的一个事情，这意味着我们可能要解方程组。（在很多其他领域也是这样，喜欢线性的系统，常常把非线性的问题线性化）
> 这时候我们要干的事情，就是想办法做系统的线性化。这里我们的电路里只有一个非线性元件，那就是 BJT。所以我们要做的就是在小信号近似下把 BJT 变成一个线性模型。

- 本身 BJT 作为一个三端元件，应该用 4 个参数来描述。这就是 H 参数小信号模型。但是这个模型显然太复杂了，使用起来非常不方便。我们突出主要矛盾，作一定的近似，只保留两个参数。这就是我们常用的小信号模型。但是我们不能忘记，这样的模型必须要在放大区下才能使用。<u>如果 BJT 不工作在放大区，小信号模型就不成立！ </u>（还是那句话，*动态建立在静态上*）

简化后的小信号模型一共两个参数：$r_\mathrm{be}, \beta$。其中 
$$ r_\mathrm{be} = r_\mathrm{bb'} + (1+\beta) \frac{V_\mathrm{T}}{I_\mathrm{EQ}} \approx 200\,\Omega + (1+\beta)\frac{26\,\mathrm{mV}}{I_\mathrm{EQ}} $$
我们也可以看到这里的动态电阻 $r_\mathrm{be}$ 还是和静态偏置电流 $I_\mathrm{EQ}$ 有关。

接下来就是从交流通路画微变等效电路。我们直接替换交流通路中对应的 BJT 的 B C E 三极为小信号模型的三极即可。

> 个人不太建议随便套公式（至少考试的时候最好能从小信号模型开始画）不过如果和三个基本放大电路一样的话，其实是可以直接写的（尤其是输入输出电阻是容易用👀瞪出来的（

当然我们还是应该掌握按照定义怎么做。我把上面的公式再抄一遍。
- 电压放大倍数 $A_\mathrm{v} = v_\mathrm{o} / v_\mathrm{i}$ 
  
  这告诉我们画等效电路的时候就要保留 $v_\mathrm{o},v_\mathrm{i}$ 等信息。一般从受控源着手，最多列一个方程就可以解得电流 $i_\mathrm{b}$。将输入电压和输出电压都用 $i_\mathrm{b}$ 表示即可求得增益。

- 输入电阻 $R_\mathrm{i} = v_\mathrm{i}/i_\mathrm{i}$ 
  
  注意什么情况下会出现 $1+\beta$ 的系数（出现射极电阻 $R_\mathrm{E}$）。如果不确定，就按照定义去写。

- 输出电阻 $R_\mathrm{o} = v_\mathrm{o}/i_\mathrm{o}$ 
  
  注意这里的输出电阻的计算，本身并没有电源在起作用。我们求的是输出网络的戴维南等效电阻，即输出端口看到放大网络的内阻。也就是说，我们应该把输出网络的负载拿掉，接上一个电源；独立源直接置零，BJT 的受控源电阻一般可以直接认为是∞（$r_\mathrm{ce}$ 很大）。这样算出来的“输入”电流作为 $i_o$ 计算输出电阻 $R_o$。

再次提醒：`输入电阻不含信号源内阻，输出电阻不含负载！`

### 5.3 三种基本放大电路
这三种接法，也就是放大电路的三种组态，分别为**共发射极放大电路**，**共集电极放大电路**和**共基极放大电路**。这三种电路的区别就在于 BJT 在电路中的接法不一样，共什么极就是把哪一极同时接在输入回路和输出回路中。换句话说，判断输入和输出分别是哪一极，然后选剩下那一极就对了。

> 这里我没有时间写了，大家看看课本和课件学吧（悲）

> 但是，这不意味着这一部分内容不重要，相反，很重要。只不过因为他很重要，所以书上和讲义上都写得比较详细，所以我就懒得写了。

- *建议*：自己合上书推一下三个基本放大电路，包括画小信号模型到求增益，输入输出电阻，熟悉一下基本功。

三种组态的放大电路的比较（课本 P174-175 表5.2.1）下表是为了大家对各个放大电路的功能有个基本概念，算出来的时候也大概能知道是不是错的太离谱了。
| 放大组态 | 共射极放大电路 | 共集电极放大电路 | 共基极放大电路 |
| --- | --- | --- | --- |
| 电压增益 | $A_v<0$，通常$\|A_v\|>1$ | $0<A_v<1$ | $A_v>0$，通常$>1$ |
| 输入电阻 | 较小 | 较大 | 小 |
| 输出电阻 | 较大 | 较小 | 较大 |
| 特点 | 电压反相放大 | 电压跟随 | 电流跟随 |

### 5.4 关于放大电路的讨论
放大的主要结构其实就差不多了。这里还剩几个小的问题需要讨论一下。
- 三极管工作区的判断
  - 截止区：$I_\mathrm{B} \leqslant 0$，发射结和集电结均反偏；
  - 饱和区：$V_\mathrm{CE} < V_\mathrm{BE}$，集电结正偏；
  - 放大区：$V_\mathrm{CE} > V_\mathrm{BE}$，发射结正偏，集电结反偏。

  电路里要看三极管是否处于放大区，所以放大电路需要合理的工作点的设置！

- 温度 $T$ 对放大的影响？
  
  $T$ 升高，电子空穴热激发更加激烈，载流子变多，放大倍数 $\beta$ 等参数增大，使得电流 $I_\mathrm{CQ}$ 增大。我们的电路通常不可能放在一个恒温的环境下，所以电路的各种参数都会受到温度的影响（也叫**温漂**）。

- **基极分压偏置电路**

  在基极设置*大电阻*分压使得基极电位 $V_\mathrm{BQ}$ 比较稳定，从而当温度升高，电流 $I_\mathrm{EQ}$ 增大，使得发射极电位 $V_\mathrm{E}$ 抬高，反过来使得 $V_\mathrm{BEQ}$ 减小，抑制了电流的增大。这样的负反馈机制能够比较好的抑制电路的温漂。

- 发射极电阻的负反馈作用
  
  我们看到分压偏置电路里面也有一个射极电阻 $R_e$。我们后面会知道，这是直流负反馈。负反馈使得放大倍数降低，但提高了电路的稳定性。

  这里注意有个**旁路电容**的问题。旁路电容就是指在一个电阻上并联一个电容，这并不会改变直流通路，但是会在交流通路中把这个电阻短路。

### 5.5 多级放大电路
多级放大电路的本质上就是一级一级一级的放大电路连接而成（）因为单级放大电路的能力有限，比如增益不够，输入输出电阻不能匹配，达不到我们的放大要求，所以我们需要把多级放大连起来作为一个整体的放大电路。

这样的放大电路很显然，总增益为各个电路增益的乘积，输入电阻为第一级输入电阻，输出电阻为最后一级输出电阻。但是这里需要注意，这不意味着我们只需要得到前后的两个电阻，中间级就不需要了。实际上，我们做拆分的时候，我们是`需要把后一级的输入电阻作为前一级的负载来计算增益`的。因为我们的增益本身是和负载有关的。

在小信号模型画出后，我们也常常把不同级之间切开算增益。再次提醒切开以后，仍然要注意*前一级的负载是后一级的输入电阻*。

## 第六章 差分放大电路

> 理想对称是一个有意思的 idea。我们的电路在实际工作和应用中，会受到大量的信号的干扰（电子干扰），这随时可能会把我们原来想要的信号给淹没。差分通过一个对称的构造，能够大大消除干扰和噪声的影响，有效克服零点漂移。

### 6.1 直流偏置（电流源电路）
我们在第一章就已经接触过了恒流源。三极管可以提供一个恒流源的实现方案。**镜像电流源**

两个参数完全相同的 BJT 的基极相连，发射极同时接地（或低电源）。这样也是一种理想对称。这样两个 BJT 的 $V_\mathrm{BEQ}$ 完全相同，那么电流 $I_\mathrm{BQ}$ 也完全相同。电流直接由电压关系得出，即 $I_\mathrm{REF} = (V_\mathrm{CC} - V_\mathrm{EE} - V_\mathrm{BE})/R$。故输出
$$ I_\mathrm{O} = I_\mathrm{C2} = \beta I_\mathrm{B} = \frac{I_\mathrm{REF}}{1+2/\beta} $$
与外界无关，是恒流输出。输出电阻 $r_\mathrm{o} = r_\mathrm{ce}$ 很大。

利用这个特点，它可以在电路中可以取代大电阻，提高集成度。更多的时候，作为**有源负载**接在电路中，`需要我们辨认出这一电流源结构。`

> 微电流源不考，不写了。

### 6.2 差分放大电路
先引入几个概念。下面的角标应该写1和2的，因为在差分里没有P和N。但是其实道理是一样的。

共模信号和差模信号（注意系数）
- **差模信号**即两输入端信号差，$v_\mathrm{id} = v_\mathrm{P} - v_\mathrm{N}$
- **共模信号**即两输入端信号算术平均，$v_\mathrm{ie} = (v_\mathrm{P} + v_\mathrm{N}) / 2$

我们把信号分为共模信号和差模信号同样是根据叠加原理。我们接着定义增益
- **差模电压增益**，即仅有差模信号输入时的电压增益 $A_\mathrm{vd} = v_\mathrm{od} / v_\mathrm{id}$
- **共模电压增益**，即仅有共模信号输入时的电压增益 $A_\mathrm{ve} = v_\mathrm{oe} / v_\mathrm{ie}$

那么总电压输出就为
$$ v_\mathrm{o} = v_\mathrm{od} + v_\mathrm{oe} = A_\mathrm{vd} v_\mathrm{id} + A_\mathrm{ve} v_\mathrm{ie} = A_\mathrm{vd} (v_\mathrm{P} - v_\mathrm{N}) + A_\mathrm{ve} \frac{v_\mathrm{P} + v_\mathrm{N}}{2} $$

反应差分放大电路的抑制共模放大差模的能力的指标**共模抑制比**
$$ K_\mathrm{CMR} = \left| \frac{A_\mathrm{vd}}{A_\mathrm{ve}} \right| $$

差分放大电路比较特殊的地方在于它的两个输入端都是有效输入端，不像很多电路一个输入端是地。这其实也引出了下面的双端输入和单端输入的问题，这个后面再讲。差分的整体结构非常对称，是两个 BJT 背对背接在一起的结构。这样做是的道理其实就是消除了各种各样的干扰和噪声。比如温漂，比如传输干扰，零点漂移等等，把这些不要的信号变成共模信号，把我们要的信号变成差模信号，然后狠狠的放大（）

这里我们的理想对称，是希望两个管子工作在同一个静态工作点 Q 下。通常两个管子的发射极会接在同一个恒流源上，当然这个恒流源也可以是镜像电流源，这样这个电路可能会看起来有很多管子，其实分解一下就知道并不复杂。

注意我们讨论差分的输入信号都是交流小信号，这里没有直流部分的输入，直流分析的时候直接将两个基极接地就行。因为发射极接了恒流源，我们的直流分析并不困难。但交流分析就不那么容易了，这里我们通常需要将共模和差模分开讨论。

### 6.3 差分放大电路的具体分析
我们差分放大电路的输入和输出都可以有单端和双端两种，那么排列组合一下就是4种。

下面简单列一些性质，具体可能需要自己琢磨推导才行。至少，需要能写得出来式子。建议大家看到这里还是跟放大电路一样，具体写一写增益，输入输出电阻。

在差模分析时，注意理想对称，对称轴上电压为0，相当于全部接地。
- 双端输出的差模电压增益是单端输出的2倍。虽然他的差模增益更高，但是没有对地输出使得它不如单端输出稳定。
- 差模下单端输入和双端输入其实一样（

在共模分析时，注意理想对称，
- 在单端输入单端输出的时候共模增益不为0，此时有有限的共模抑制比 $K_\mathrm{CMR}$。除此之外，由于理想对称，共模增益为0，共模抑制比为∞。
- 注意共模信号输入分析的时候一定要考虑恒流源的内阻 $r_\mathrm{o}$。（为什么？）
- 双端输出的输出电阻是单端输出的两倍。

最后再次提醒，我们的电路中一定要识别出有源负载和差分结构。其实还是比较明显的，电流源的基极是接在一起的，而差分的两个基极是朝外的。把这两个结构找出来，电路的大概功能基本上就能看明白了。


## 第七章 集成运放电路

**集成电路运算放大器**，简称**集成运放**或者**运放**，是非常常见的一个集成放大器，内部一般是三级放大。它也是深度负反馈中最常见的充当放大电路的部分。我这里放在后面讲，是因为这个时候我们已经对放大电路有了比较多的认识，能够比较好的理解集成运放是个什么东西了，也能够知道他为什么有这样的性质，不至于觉得非常突兀。

### 7.1 集成运放的性质
集成运放通常由三级放大电路构成。比较常见的构成是，第一级为 CMOS 差分输入，第二级为共射放大，第三级为功率放大输出（这里课程被砍掉了所以我们也不讲）。第一级使得电路的两个输入端口作差，第二级让信号放大，第三级再次放大并且提供比较好的输出匹配。这样我们可以理解为什么得到了这样一个输入电阻非常高而输出电阻非常低，增益系数很大的放大电路模块。

我们知道这个内部结构其实是比较复杂的，但是我们包装起来就简单了。我们看书上的两个符号，我们更常见的是后者。运放一般就画3个端口，**同项输入端**$+$，**反相输入端**$-$和输出端。`但是一定不要忘记，运放还有上拉电源和下拉电源，`只是我们通常省略不画了。

因为我们有差分在前，运放的有效输入其实是 $v_\mathrm{P} - v_\mathrm{N}$，我们的电压传输特性通常画 $v_\mathrm{O} - (v_\mathrm{P} - v_\mathrm{N})$ 图。在线性区，我们有 $v_\mathrm{O} = A_\mathrm{vo}(v_\mathrm{P} - v_\mathrm{N})$。但是集成运放的增益其实是非常大的，一般只有很小的线性区，之后就因为电源电压的限制达到饱和区了。所以图上看到的是一条非常陡的直线，然后是两条水平的线。

集成运放同样有差模共模，共模抑制比这些定义，参考差分电路。我们可以看到，输出电压只与差模信号有关，故共模电压增益为0，共模抑制比为无穷。

### 7.2 理想运算放大器
我们知道这样的运算放大器分析起来还是比较复杂的。我们引入一个**理想运放**，它的（开环）增益 $A_\mathrm{vo} = \infty$，输入电阻 $r_\mathrm{i} = \infty$，输出电阻 $r_\mathrm{o} = 0$。此时的电压传输特性就相当于是一个符号函数。但我们实际使用的时候（在本课程范围内），电路中的运放并不是开环工作的，通常是闭环工作的。我们希望运放工作在线性区。我们注意到理想运放的线性区无限窄，只有当 $v_\mathrm{P} = v_\mathrm{N}$ 时才成立。这样我们就得到了第一个性质：**虚短**，即<u>运放两输入端电压相等</u>，好像短路了一样。另外无穷的输入电阻使得输入电流 $i_\mathrm{P} = _\mathrm{N} = 0$，这就是**虚断**，即没有输入电流，好像断路了一样。但运放通常是有输出电流的。

在任何的运放电路的分析中，我们都必须牢记“虚短虚断”的性质，也是运放分析的最核心的方法。

### 7.3 运放的应用电路和模拟运算电路
这个部分其实不难，只要掌握了运放的性质，熟练运用“虚短虚断”的分析方法，应该还是比较套路的。

> 这里我没有时间写了，大家看看课本和课件学吧（悲）

- 电压跟随器（缓冲器、隔离器）
- 同相放大和反相放大
- 比例运算
- 求和求差
- 仪用放大器
- 积分微分


## 第八章 反馈电路

> 反馈本身是一个非常常见的东西，应用也十分广泛。比如老师给我们上课，我们的表现（听课or摸鱼）就是给老师的一个反馈。老师会根据大家的反馈来调整自己上课的内容或者速度。再比如人类大量排放二氧化碳，产生了温室效应，这是自然给人类的反馈。人类会知道碳排放超标了，需要调整排放。在自动控制系统里面，（负）反馈就是控制的一个最常见的手段。一个开环的控制最大的缺点就是不稳定，很容易受到干扰。我把空调温度调到 26 度（假设制冷），他并不知道设定一个多大的功率能把温度控制在 26 度。但是我加上闭环的反馈，温度低于 26 度的时候空调就休息，温度高于 26 度的时候电机就工作，这样就能比较好的达到我的目标设定。这就是反馈的作用。

> 在模电里面，我们通常引入负反馈使得电路更加稳定。电路中有用到正反馈的地方，那就是波形发生，我要把一个小的扰动放大变成一个大的波形信号。但是大部分情况下我们还是使用负反馈。

### 8.1 反馈的基本概念
**反馈**，是指<u>将电路中的输出量（电压or电流）通过反馈网络返回输入回路，从而影响输入的过程</u>。常见的反馈是引入反馈的放大电路。课本图 8.1.1 比较清楚的展示了反馈的过程。从图上我们可以直接读出，$X_\mathrm{id} = X_\mathrm{i} \pm X_\mathrm{f}$（这里加号表示正反馈，减号表示负反馈）。我们注意到，放大电路此时的输入变成了 $X_\mathrm{id}$，也就是增益（**开环增益**） $A = X_\mathrm{o}/X_\mathrm{id}$。这里我们定义**闭环增益**为整个电路的增益 $A_\mathrm{f} = X_\mathrm{o}/X_\mathrm{i}$，**反馈系数** $F = X_\mathrm{f}/X_\mathrm{o}$。
- 注意这里 $X_\mathrm{o}$ 是反馈的输入量，$X_\mathrm{f}$ 是反馈的输出量，即*反馈网络右输入左输出*。

反馈需要掌握的几个判断。

反馈第一个判断：判断这里是否存在反馈。如果这里没有反馈，那么就没有下文了。当然这个直接考比较少，因为太 trival 了。
- 看输出回路有没有连接回输入回路。如果没有，那就不用看了。
- 注意看连接是否是接地。如果是看似连起来了，但实际上是接地的。也就是要注意*把接地和接电源的导线拆开*。

### 8.2 反馈的分类

#### 8.2.1 级间反馈和级内反馈
级内反馈就是在一级放大内部有反馈，比如射极电阻 $R_E$ 其实就有负反馈的作用。但是这个没什么意思，基本上也不会考。我们关心的是级间反馈，也就是不在一级之内的反馈。说白了，就是你看着不属于放大电路的部分，有根导线横在你面前了。

反馈第二个判断：判断是级间反馈还是级内反馈。

#### 8.2.2 直流反馈和交流反馈
这就是说在你直流通路里存在的反馈就是直流反馈，在交流通路里存在的反馈就是交流反馈。当然大部分情况下是两者兼有。如果*出现了电容*，那么就要小心了，这个地方很可能直流通路和交流通路长得很不一样。通常情况下通过电容会把反馈回路在交流通路里拆开，那么就只有直流反馈了。

反馈第三个判断：判断是直流反馈还是交流反馈。

#### 8.2.3 正反馈和负反馈
这个其实没什么好解释的，反馈量如果抵消了输入量的作用，就是负反馈；反馈量如果使得输入量更大了，那就是正反馈。主要是判断。

反馈第四个判断：判断是正反馈还是负反馈。这里我们通常采用**瞬时极性法**。
- 瞬时极性法其实就是标正负。在输入端先标上$+$，然后沿着放大电路和反馈回路绕一圈返回这个点，是$+$就是正反馈，是$-$就是负反馈。
- 标注规则：穿过导线和电阻不改变相位。穿过集成运放，正端穿过不变，负端穿过变号。穿过 BJT，B进E出不变，C出变号。NMOS 同理。（那个图你们脑补一下x）

#### 8.2.4 串联反馈和并联反馈
大的来了。最重要的就是串并联的判断和电压电流的判断。

反馈第五个判断：判断是串联反馈还是并联反馈。
- 串联/并联取决于反馈网络的输出端口（这个在左边）怎么接入输入回路的。
- 简单的说，直接接入输入端的是并联反馈，接入输入回路但没有接入输入端的（比如隔着 BJT 或者运放）是串联反馈。

#### 8.2.5 电压反馈和电流反馈
反馈第六个判断：判断是电压反馈还是电流反馈。
- 输出 $X_\mathrm{o}$ 是电压/电流的是电压/电流反馈。
- 一个简单的判断方法，你把输出的两端直接短接。通常只有一个输出端，另一个是地，那就把输出接地。如果此时反馈回路被接地（即反馈消失了），那么就是电压反馈，否则是电流反馈。其实串联/并联也有这个判断方法，只不过是作用在输入端。（想想这是为什么？）
- 其实电压/电流反馈和并联/串联反馈是对应的，判断方法也类似，不过一个在输出端，一个在输入端。电压/电流反馈也可以看反馈回路是不是直接接在输出端。

### 8.3 负反馈放大电路

#### 8.3.1 负反馈放大电路的基本概念
我们说**反馈组态**，一般情况下指的就是<u>负反馈下的电压并联，电压串联，电流并联和电流串联</u>。对于这四种反馈组态，书上分别进行了详尽的讨论，这里不多赘述。

我们来讨论一下负反馈放大电路的特点。其实从上面 8.1 的几个式子中我们已经可以得到负反馈放大电路的闭环增益。
$$ A_\mathrm{f} = \frac{X_\mathrm{o}}{X_\mathrm{i}} = \frac{X_\mathrm{o}}{X_\mathrm{id} + X_\mathrm{f}} = \frac{X_\mathrm{o}}{X_\mathrm{o}/A + FX_\mathrm{o}} = \frac{A}{1+AF} $$
其中 $AF$ 称为**环路增益**，$1+AF$ 称为**反馈深度**。我们可以看到，引入负反馈后电路增益降低，倍数与反馈深度有关。
> 这里我们不讨论频率响应（因为没讲），本身这些系数是复数，在讨论的时候是需要取模的，下略。

我们上面的讨论全部使用的是 $X$。这个 $X$ 表示的是电压 $v$ 或电流 $i$，视具体电路而定。比如在电压/电流反馈中，输出 $X_\mathrm{o}$ 是电压/电流。在串联/并联反馈中，$X_\mathrm{i},X_\mathrm{id},X_\mathrm{f}$ 是电压/电流。相应的系数 $A,F$ 也有对应的具体化。

#### 8.3.2 负反馈对放大电路的影响
- 提高增益的稳定性
  
  当放大电路的开环增益变化时，闭环增益变化量比较小。
  $$ \frac{\mathrm{d}A_\mathrm{f}}{A_\mathrm{f}} = \frac{1}{1+AF} \frac{\mathrm{d}A}{A} $$
  当达到深度负反馈时，$\mathrm{d}A_\mathrm{f}=0$，因为此时闭环增益 $A_\mathrm{f} = 1/F$。（反馈网络通常是无源的，大部分情况下甚至都是电阻网络，稳定性好）

- 对输入输出电阻的影响
  
  这里的影响总是往有利的方向变化。
  - 串联负反馈增大输入电阻 $R_\mathrm{if} = (1+AF)R_\mathrm{i}$
  - 并联负反馈减小输入电阻 $R_\mathrm{if} = R_\mathrm{i}/(1+AF)$
  - 电压负反馈减小输出电阻 $R_\mathrm{of} = R_\mathrm{o}/(1+AF)$
  - 电流负反馈增大输出电阻 $R_\mathrm{of} = (1+AF)R_\mathrm{o}$

- 减小非线性失真（增大线性区），抑制噪声

### 8.4 深度负反馈
当 $1+AF \gg 1$ 时，称为**深度负反馈条件**。深度负反馈条件下有 $A_\mathrm{f} \approx 1/F$，即*增益已经与放大电路本身无关，只由反馈网络决定*。此时你可以理解为放大电路部分都看成是一个集成运放，不改变深度负反馈调节下电路的分析。*故可以直接使用虚短虚断的分析方法*，大大化简了分析方法。

后面的……应该不需要多说了，按照上面第七章的运放的电路的分析方法来做就行了。剩下的就是计算了，这个交给大家自己练习巩固。

---

### 写在最后

> 由于本课程课时删减等原因，很多内容今年都直接删掉不讲了，比如二阶电路，振荡电路，频率响应，功放电路，直流滤波等等。这些内容没讲不代表不重要，但是由于本人精力有限，本指南中没有把这些内容写进来。后续如果有别的同学补充续写或完善这一指南，我会非常欢迎。

> 最后，希望大家都能顺利学会模电，取得一个满意的成绩！

#### 附：课程进度及作业

| 日期 | 课程进度 | 课程作业 |
| --- | --- | --- |
| 8.31 | 绪论-1.4 | 无 |
| 9.7 | 1.5-2.2 | 习题一 1 4 6 7 12 16 21 23 32 |
| 9.14 | 2.2-4.7 | 习题二 5 9 13 21 习题三 9 习题四 6 10 19 26 28 |
| 9.21 | 4.8-6.5 | 习题五 3 8 10 习题六 2b 3 14 21 33 38 |
| 9.28 | 6.6-8.6 | 习题八 4（使用有效值相量） 5 19 20 |
| 10.12 | 绪论 | 1.4.1 1.5.2 1.5.6 |
| 10.19 | 2.1-3.1 | 2.3.2 2.4.7 2.4.8 |
| 10.26 | 3.2-3.4 | 无 |
| 11.2 | 3.4-3.5  | 3.2.1 3.4.1 3.4.3 3.4.7 3.4.8 3.4.9 |
| 11.9 | 5.1-5.2.2 | 无 |
| 11.16 | 5.2-5.3 | 无 |
| 11.23 | 5.3-5.5, 4 | 5.2.1 5.2.4 5.2.5 5.2.11 5.2.12 5.4.1 |
| 11.30 | 7.1-7.2.1 | 无 |
| 12.7 | 7.2-8.1 | 7.1.5 7.2.7 7.2.10 |
| 12.14 | 8.1-8.6 | 8.1.1 8.1.3 8.2.1 8.2.3 8.3.1 8.3.3 8.4.1 |

期末考：2023.2.23 上午 8:30 - 10:30，5204

#### 参考资料

1. 曹老师的课件
2. 三本课本
3. 顾里《模拟电子线路》
4. myp的电基整理资料
5. ~~你们错误百出的作业~~
6. 6

<p align="right">本文使用Markdown书写

<p align="right">最近更新：2023.2.16

<p align="right">22Fall 课程助教 cx

