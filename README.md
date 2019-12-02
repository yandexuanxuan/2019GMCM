# 2019GMCM
第十六届华为杯数学建模竞赛F题数模之星论文附代码

比赛出结果之后，很多人联系我们希望能参考我们的论文和代码，投稿版面费实在是太贵，因此我们把论文和代码直接共享到GITHUB上，希望能帮助到有需要的同学。

## 下面附上参加完这道赛题的学术讨论之后个人对这篇论文的不足之处的思考：
### 第二小题
#### 在飞行轨迹的分析上，我们存在一定的问题，给出的并不是最优的轨迹，最优的轨迹应当是将修正点包含在圆弧内部，而非圆弧的端点。
#### 在问题的求解中使用的近似和线性规划这个方法上，我认为我们的做法都是合理的。赛题组长老师提到可以验证第一题的结果，给出飞行轨迹的做法我们是不能认同的。首先无法给出理论性的证明，这种飞行轨迹一定是最优的；其次倘若使用第一题中所有大于第二题计算结果的次优解加以一一验证，其理论计算量是指数级的，模型失去鲁棒性。综上两点，这种验证性解法的理论性和实际求解的效果都不会太好，因此我们不能认同这种解法。

### 第三小题
#### 在和国防科大的同学讨论过后，我们发现这个模型在数据集的求解为到达终点的概率100%的情况下是没有问题的。但是当数据集到达终点的概率不是100%的情况，我们求得的只是一个快速的近似解，而非最优解。主要原因在于我们没有考虑到在飞行路径上是否存在两个点，这两个点只有在都不成功的前提下，才会使得飞行器无法到达终点，反之任一点失效，都不影响飞行器的飞行。当然这种两个点的情况还可以拓宽到N个点来思考，那么倘若使用规划，他会是一个高阶非线性的规划，难以求解。因此模型在这种无法100%到达终点的情况下，还可以再作改进，看看能否将模型做的更加精细，从而求解出精确的解。

### 关于GUROBI
#### 学术交流会上，很多人似乎都没听过这类商业求解器，一直在问我们是什么，能否共享代码。首先GUROBI是一种快速求解规划问题的商业求解器，其次GUROBI教育网可以申请免费使用，同时GUROBI还有使用手册，支持包括Python、C++等在内的主流语言，有兴趣的同学可以学习一下。同时，我们也附上了我们的求解代码，希望能帮助到大家。

## 未经许可，严禁转载，如需在文献中引用，请在文中附上github链接
