# Reviewer 1

## **Reviewer#1, Concern # 1:**

**Author response:**这是一个很好的质询，我们从抗攻击的能力和信誉管理系统设计需求两个方面给出了设计目标，并对R-tracing如何满足这两个目标给出了解释。

**Author action:** 我们已经更新了手稿，增加了系统分析和设计目标两个部分。

## **Reviewer#1, Concern # 2:**

**Author response:**这是一个很好的建议，我们添加了一篇2022年发表在TITS的信誉管理方法和一篇2022年发表在IOTJ的信誉模型进行对比，如表格所示，我们重写了本文和其他方法的区别。

**Author action:** 我们在motivation里更详细的介绍了R-tracing和相关方法的不同，涉及对表格里相关项目的解释。

在TITS的论文里(https://ieeexplore.ieee.org/document/9210587)，车辆的信任值计算依据是邻居包转发率，每辆车汇总正确接收的controll package比例和正确接受data package的比例，通过linear aggregation方法计算得到车辆信誉值。

在IOTJ的论文里(https://ieeexplore.ieee.org/document/9372310)，车辆信誉值根据历史信息和参与程度来进行评估。通过时间间隔的划分和时间衰减函数来获得信任rating，再根据车辆的参与匿名区域构建的次数计算participation trust。信任rating和参与信任会汇总得到comprehensive信任值。

## **Reviewer#1, Concern # 3:**

**Author response:**这是一个非常好的意见。我们在 VI. B. Performance of Vehicle Reputation  Management System 部分增加了对车辆消息上链的延迟，对节点运行时的存储空间占用的测量。

**Author action:** 我们测量了从车辆发送消息给基站到该消息被区块链记录的延迟和区块链节点运行时的存储空间消耗情况。增加了统计图表示新增的实验结果。结果显示该系统能满足车联网场景下的低延迟和低存储需求。



# Reviewer 2

## **Reviewer#2, Concern # 1:**

**Author response:**这是一个很好的讨论，我们增加了两篇2022年的信任管理参考文献，并将这些文献的缺点写在了相关工作的最后部分。

**Author action:** 我们修改了手稿，将相关最新的信誉模型缺陷写在了相关工作的最后。

## **Reviewer#2, Concern # 2:**

**Author response:**这是一个很好的讨论，我们将attack model单独作为3.D部分叙述，给出了4种常见的攻击类型。

**Author action:** 我们更新了手稿，将attack model作为3.D章节列出来，并给出了4种攻击行为MA、MOA、RA、RS的介绍。

## **Reviewer#2, Concern # 3:**

**Author response:**这是一个很好的提议，我们将安全分析单独挑选出来，对攻击模型里出现的4种攻击方法进行阐述，给出我们的方法如何解决了这4种攻击的叙述。

**Author action:** 我们修改了手稿，增加了设计目标部分，并将对4种攻击的抵抗性作为设计目标之一，对每个攻击行为是如何R-tracing防御的进行了介绍。

## **Reviewer#2, Concern # 4:**

**Author response:**这是一个很好的提议，增加设计目标部分可以让R-tracing的工作变得更加清晰。我们从攻击的防御和系统设计两个方面给出了R-tracing的设计需求。

**Author action:** 我们修改了手稿，增加了系统分析部分，其包括了两个内容，其一是对攻击行为的安全分析，阐述了R-tracing如何有效防御4种攻击。其二是对系统设计需求的分析，给出了系统需要满足可靠性、有效性、不可篡改性和分布式管理的特性。

## **Reviewer#2, Concern # 5:**

**Author response:**这是一个很好的提议，由于我们的疏忽，我们只列举了实验里车辆速度参数而遗漏了通信范围的距离，为了使得我们的实验更加贴近实际，我们引用了2020年发表于IOTJ的文献[A Comprehensive Survey on Internet of Things (IoT) Toward 5G Wireless Systems](https://ieeexplore.ieee.org/document/8879484/)，在其中介绍了SBS的覆盖范围为1-2km，而MBS的覆盖范围为2km。因此我们重新设置了实验，将道路的区域变成20km*20km的路段，并将车辆的速度设置为36km/h，在一条道路上有两个MBS和两个SBS，令他们的通信覆盖半径都为1km，这样就使得车辆在4km的路段上可以感知当前道路上发生的事件并及时将消息上报给MBS，这样使得论文的信誉模型更具有说服力。

**Author action:** 我们使用新的参数对信誉模型的实验进行了重做，发现结果和之前的几乎没有区别。我们修改了手稿，给出了最新的实验结果以替代了旧的实验结果。



# Reviewer 3

## **Reviewer#3, Concern # 1.1:**

**Author response:**这是一个很好的质询，根据[On Public and Private Blockchains | Ethereum Foundation Blog](https://blog.ethereum.org/2015/08/07/on-public-and-private-blockchains/)和论文Blockchain challenges and opportunities: a survey[Microsoft Word - FM 1.doc (henrylab.net)](https://www.henrylab.net/wp-content/uploads/2017/10/blockchain.pdf)，我们给出联盟链的形式化定义：联盟区块链是一种区块链，其中共识过程由一组预先选择的节点控制。

联盟链并不保证所有的组织都是互信的，在R-tracing里，MO DMV PD是可信的，而车辆是不可信的，不具备维护区块链的权利。R-tracing使用联盟链的原因主要有三个方面，首先只有属于MO DMV PD的节点才有权利维护区块链，和公链相比，这过滤了普通的非授权用户，提高了管理效率，也使得恶意用户想要篡改数据几乎是不可能的。其次，由于节点数目有限，因此使用联盟链可以提高区块产生速度，这使得车辆的上报信息和信誉值更新情况可以快速上链。最后，联盟链的数据只限于联盟内部的各个节点共享，普通的车辆用户需要对MO发出申请才可以查询到其他车辆的信誉值，这保护了其他用户的隐私不会泄露，且所有的数据的访问有迹可循。

**Author action:** 我们对手稿进行了修改，对Motivation进行了重写，添加了我们使用区块链的原因。

## **Reviewer#3, Concern # 1.2:**

**Author response:**这是我们的疏忽。在基于 5G 的智能交通场景下，我们认为 DMV，PD， MO 三方共同参与车辆信誉管理。这三个管理组织之间相互独立，因此不能使用集中式平台，但是该平台的参与方又相对固定，不像公链那样允许参与节点自由加入和退出，因此需要使用联盟链。而HLF 是一种支持高吞吐量的，使用严格成员管理策略的联盟链平台。 HLF 使用 execute-order-validate 顺序对交易达成共识，相比常见的 order-execute 顺序能提 升更多的吞吐量，适合车联网环境下大规模的消息处理。HLF 引入 member service 用于对参与者的认证和授权，分层的成员管理策略能实现更细粒度的背书策略，适合 DMV，PD 和 MO 和他们的子部门（如 MO 下具体的基站节点）在信誉管理系统中扮演不同的角色。 以上两点成为我们选择 HLF 作为本系统实现平台的主要原因。HLF 具有高度的可扩展性， 使用通用编程语言（C/C++/Java 等）编写智能合约，通过部署不同的智能合约，设置不同 的背书策略能在复杂场景下实现丰富的功能，不会限制本系统的功能实现。在实验中，我 们使用了常用的 HLF v2.2.0，代码可以支持 HLF v2.2.0 即以上版本。

**Author action:** 我们在 I. Introduction 末尾部分引入了对 HLF 的介绍，阐明 HLF 与本系统的 契合关系。在 VI. B. Performance of Vehicle Reputation Management System 部分增加了对 HLF 版本的描述信息，指明使用了 HLF v2.2.0。

## **Reviewer#3, Concern # 1.3:**

**Author response:**这是一个很好的质询，我们在图3给出了HLF structure的结构，所有的节点（主节点、peer节点、排序节点）共同维护了区块链，整个区块链由4个组织进行维护。排序节点提供共识服务，负责对区块进行排序以将区块上传，peer节点是MBS，持有账本实例，在图3里，MBS分属于两个不同的组织。车辆不属于任何的组织，他们是作为信息上报的重要一环，提供信息上报并享受车联网带来的便利，车辆不是区块链的维护方，因此不存有账本，但可以通过向基站发出信誉值查询的请求，基站将作为MO组织的一个部分对信誉值进行查询并返回。

**Author action:** 我们修改了手稿，在实验部分增加了HLF里节点的解释。

## **Reviewer#3, Concern # 1.4:**

**Author response:**这是我们对授权用户的解释不清楚，这里的授权用户指的是MO DMV PD三个组织下的节点，他们作为区块链的维护者，具备对信誉值进行查询和追溯的能力。在通过证书的身份校验后，授权用户可以查询到信誉值和对应产生当前信誉值的车辆历史行为。

**Author action:** 我们修改了手稿，在Section V.B里对授权用户添加了解释。

## **Reviewer#3, Concern # 1.5:**

**Author response:**这是一个很好的质询。在设计目标里，我们认为我们和其他使用区块链的工作不同在于可靠性和有效性、以及多组织分布式管理三点。

首先，论文18和论文30并没有考虑多组织进行信誉管理的需求，而使用联盟链是可以满足这一需求的。

其次，论文17和论文31无法保证信誉模型里计算的信誉值的可靠性，因为31依赖于其他车辆的Local Opinions和Recommended Opinions产生信誉值，而这些opinions完全可能是虚假的。而论文17缺少一个信誉模型，只是将信誉值进行了存储，因此，上传到区块链上的信誉值并不是可靠的，也就可能会导致了区块链上存储了不可信的数据，这就在一定程度上违反了区块链可信的性质。

最后，我们的R-tracing通过使用联盟链，并将信誉管理抽象为三种数据结构和四个智能合约，通过较小的存储负担和confirmation time完成了比其他方法更高的高吞吐量

综上所述，我们认为我们较为充分的利用了联盟链的优势，并通过实验验证了这一点。

**Author action:** 在相关工作里，我们添加了R-tracing里如何更充分的利用区块链优势的解释。

## **Reviewer#3, Concern # 2:**

**Author response:**感谢您的宝贵意见。我们将从两方面分别回应 verification 和 rubbish information 的问题。首先，是我们对 verification 的表述不够清楚。这里的 verification 指的 是 PD 根据实际发生的情况对 MO 记载上链的消息进行真实性检验，而不是 HLF 里对交易 的 execute-order-validate 中的 validate 环节。后者发生在每一次账本更新之时，是对区块中 交易是否满足背书策略，是否和背书内容一致的检验，确保所有账本的一致性，是一种链上验证，这种 validation 是 HLF 自身的功能，不是本文需要实现的内容。在我们的信誉管 理系统中，validation 是一种链外验证，PD 将现实情况和链上的消息对比，检查虚假的消 息，修改车辆信誉，将结果通过智能合约写入区块链。其次，对于账本上的 rubbish information 问题，我们使用信誉管理机制对车辆行为进行约束，激励车辆发送合法信息。 如果车辆持续发送垃圾信息，那么它的信誉将维持在较低水平，我们可以通过拒绝接收该 车辆信息等方式减少垃圾信息，但这不是本文讨论的重点，本文主要目的在于实现一种车 联网场景下量化的信誉管理机制。

**Author action:** 在Rtracing里，链上数据包含了车辆上报的消息以及车辆的信誉值更新记录。前者作为车辆行为的凭证，记录了车辆在网络里的行为，上链后供PD去更新信誉值信息。后者由PD验证在线下验证消息真实性后，通过从区块链上获得车辆在网络里的行为，再对信誉值进行更新。因此，区块链系统记录的并不是无用信息。

## **Reviewer#3, Concern # 3.1:**

**Author response:**verification是背书过程里对签名的检查，HLF里client自己收集背书节点的背书结果并提交给order节点的，因此order节点需要对签名进行verification，而背书是区块上链的必备过程。我们对算法的verification进行修正，改为了execution。

**Author action:** 我们在 III.A System Overview 中对于 PD 职责的描述部分增加了 PD 对消息 的 off-chain verification 功能，强调其与 HLF 自身 validation 功能的区别。我们在 V.C Smart  Contract 中对 Algorithm 3 的描述中增加了对输出内容的描述，强调其不更改车辆消息的原始记录。

## **Reviewer#3, Concern # 3.2:**

**Author response:**这是一个很好的问题，这里的 verification 指的是 PD 根据实际发生的情况对 MO 记载上链的消息 进行真实性检验，而不是 HLF 里对交易的 execute-order-validate 中的 validate 环节。在论文9里，我们给出entity-trust和data-trust的定义，entity-trust利用不同的工具，例如密码学、博弈论、模糊逻辑、社交网络，而器学习、数据分析和基于证据的方法用于建立data-trust。在R-tracing里，我们使用了信号模型建立奖惩机制，我们认为信号模型是一种经济学的工具，因此在表格1里将R-tracing称为entity-trust。R-tracing里涉及的verification是由PD线下赶往事发地得出确定结果，进而由PD节点对车辆的发送信息进行奖惩。我们认为线下的verification并不涉及机器学习、数据分析和基于证据的方法，它是由PD线下得到的ground truth，因此没有归类为data trust。

**Author action:** 我们在 III.A System Overview 中对于 PD 职责的描述部分增加了 PD 对消息 的 off-chain verification 功能，强调其与 HLF 自身 validation 功能的区别。

## **Reviewer#3, Concern # 3.3:**

**Author response:**可信的元数据是指信誉值更新的依据，在PD进行线下的事件verification后，PD根据verification结果对车辆上报信息进行检查，如果车辆诚实上报则进行奖励，否则进行惩罚。因此整个信誉值计算过程是基于确定的可信元数据数据进行的。

**Author action:** 我们增加了对confirmed metadata的解释在motivation里。

## **Reviewer#3, Concern # 4.1:**

**Author response:**这是我们的疏忽，\theta是车辆的信誉值，它和R表示了一个意思，车辆发送消息的成本主要取决于信号量e和信誉值R。

**Author action:** 我们对手稿里的公式1进行改正，并对论文其他出现\theta的地方进行了修正，将其修改为R。    

## **Reviewer#3, Concern # 4.2:**  

**Author response:**这是很好的评论，我们想要通过Matlab仿真实验去证明我们的信誉模型在较大规模的交通场景下可以很好地抑制4种攻击，仿真只证明了信誉模型的有效性，不涉及具体的区块链过程。而HLF的系统实现弥补了这一缺陷，我们实现了一个5G车联网原型系统，并将信誉模型的计算过程融合到智能合约里，再对系统的性能进行分析，去证明我们的信誉管理系统具有低负担和高吞吐量。

**Author action:**  我们补充了HLF实现和MATLAB模拟的关系在5.实验部分。

## **Reviewer#3, Concern # 5:**

**Author response:**感谢您的建议。在 HLF 中，智能合约被称为链码，是在 execute 阶段运行 的，用来实现应用逻辑的程序。链码是分布式应用的核心，极大地拓展了分布式账本的功 能。链码分为系统链码和用户链码，前者永久存在于区块链系统中，用于系统管理，后者 由用户编写，用于实现应用层的特定功能。本文通过在 HLF 上开发链码实现信誉管理系统 的功能模块。

**Author action:** 我们在 I. Introduction 部分增加了对智能合约/链码的介绍。