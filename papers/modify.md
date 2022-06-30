# 审稿人1

1. 论文缺少安全性分析，在引入机制后，作者只分析了性能，作者应该描述方法的安全需求，给出一个安全分析。
2. 相关工作里应该介绍的更加详细和论文机制的不同。作者应该饮用一些近来的结果。
3. 性能分析只分析了吞吐量，应该更多的指标

# 审稿人2

1. 作者应该讨论最新的安全模型和他们的缺陷
2. 攻击者模型应该被清楚的讨论
3. 提出的技术如何解决给定的攻击模型应该被讨论
4. 设计目标应该被出来，例如透明性、安全性、隐私等，还应该叙述作者如何满足这些目标
5. MATLAB模型应该考虑移动性和通信模型参数？

# 审稿人3

## 区块链模型

1. 为什么需要在可信环境下使用区块链？
2. 为什么使用HLF？方法适用于哪个版本的HLF？我们的方法在其他的HLF版本上也能工作吗？
3. HLF结构的映射需要更清楚，特别是车辆，车辆属于哪个组织？他们有账本的副本吗？可以访问账本吗？
4. 第八面的部分写，授权用户可以查询信誉值并且追溯。这里的用户是什么？车辆吗？还是MO DMV PD？
5. 我们是怎么用到区块链大量的优势的？

## 可拓展性

验证信息发生在数据上链后？那么存放了这么多垃圾信息，是否对可拓展性有影响？

## 验证和背书

1. verification是什么？PD通过检查签名和车辆ID去运行验证？那么report的机密性和完整性呢？
2. endorsement和verification描述了两件事。在HLF里，背书过程涉及链上的数据，它只检查账本和签名。在verification里，似乎会涉及链下数据去验证车辆信息的真实性。从表格1里可以看出，模型是entity-centric，但是数据也很重要，验证会涉及链下数据吗？请阐述它。**（我们的问题在于，智能合约的执行结果变成了verification result）**
3. 可信元数据缺乏解释

## 其他

公式1的参数需要去掉

阐明Matlab模型与HLF实现之间的关系。它们是相互独立的吗?

INTRODUCTION部分可以用chaincode或者smart contracts





# 我们的修改

## 宋哥的解释

verification过程是确保你提交的消息是之前你背书的消息，是背书的一部分，因为fabric是client自己收集背书节点的背书结果并提交给orderer节点的，这期间client可能用非法交易替代背书时候的合法交易。

## 我的任务

### 系统目标和安全分析

REPLACE: A Reliable Trust-Based Platoon Service Recommendation Scheme in VANET

SIRC: A Secure Incentive Scheme for Reliable Cooperative Downloading in Highway VANETs

### 可能增加的指标

Master-slave chain based trusted cross-domain authentication mechanism in IoT

#### 存储负担

随着验证信息的增加，分析了主链的存储负担。论文里即使主链信息达到了2000，存储大小也就2000KB

#### 吞吐量

每秒处理的认证次数

#### 错误节点比例

出错的区块链节点占总区块链节点的比例

#### 时间延迟

区块发布时间减去共识请求时间





## 关于通信参数和距离的添加

使用Constant Speed Propagation Delay Model，即距离除以光速可以获得延迟。        可以添加一个道路和基站的实验图，以说明通信的延迟在实验里对实验结果没有影响。

![实验道路图](https://github.com/enzeyu/notesForRecord/tree/main/pictures/roadFigure.jpg)

