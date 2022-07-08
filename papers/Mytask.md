# MATLAB实验

## 距离调研

### A 28 GHz 480 elements Digital AAS using GaN HEMT Amplifiers with 68 dBm EIRP for 5G Long-range Base Station Applications

a  typical  long-range  base  station  such  as  1  km  LoS  distance  and  50  m  base  station  altitude

### Demonstrating Immersive Media Delivery on 5G Broadcast and Multicast Testing Networks

第二章给出了三个testbed，其中第一个testbed里给出的inter-site之间距离在1.8KM到19.8KM之间。

## A Comprehensive Survey on Internet of Things (IoT) Toward 5G Wireless Systems

第9面里，small cellbase stations将被安装到1-2km间隔，而macro base station将被安装在a distance of kilometers里。

These combined communication systems are termed as a dual connectivity 

## [Wireless backhaul: Why we need small cells vs macro cells | Blu Wireless](https://www.bluwireless.com/insight/wireless-backhaul-and-small-cells/)

Macro cells instead emit connections at a much higher range – kilometres compared to metres. However, their performance at the edge of the network decreases significantly. So, while small cell radio waves cover a smaller area, they provide more reliable and consistent connections within their range.

## Hassan_Noha.pdf

参数为1000m 200m

## 解决方案

设定macro基站的通信距离为1km， micro基站的通信距离很短(500m)，所以每个macro基站的通信范围为2km，然后对路段和速度缩减为一半，重新做实验

引用A Comprehensive Survey on Internet of Things (IoT) Toward 5G Wireless Systems

# 系统分析和设计目标

A Cross-Chain Trusted Reputation Scheme for a Shared Charging Platform Based on Blockchain

Blockchain-Based Adaptive Trust Management in Internet of Vehicles Using Smart Contract

## 设计目标

R-tracing包含了一个信誉模型和信誉管理系统，经过分析，我们提出了两大类需求，第一类是信誉模型对攻击的抵抗能力，第二类是信誉管理系统设计的需求。

### 对攻击的鲁棒性

1. resilience to MA：R-tracing需要对MA行为的车辆进行惩罚，并保证在尽量短的时间里将MA行为的车辆踢出网络。
2. resilience to MOA：针对MOA行为的车辆为了长时间存活而表现出的良性行为和恶意行为切换现象，R-tracing需要具有识别MOA车辆存在并将其踢出网络的能力。
3. resilience to AS：针对AS行为的车辆，R-tracing需要抑制他们在网络里表现的自私行为，并对他们的信誉值进行削减。
4. resilience to RS：针对RS行为的车辆，R-tracing需要有对RS行为的车辆进行激励的能力，使得他们积极进行消息的上报。

### 系统设计需求

1. 可靠性(reliability)：为了让良性车辆和自私车辆得到充足的动力去诚实上报消息，R-tracing里的信誉模型需要保证信誉值的计算过程是真实可靠的。
2. 有效性：R-tracing需要以较低的计算和存储负担下有效运行。因此，R-tracing必须同时满足高吞吐量和低存储负担两点。
3. 不可篡改性：上链的数据作为车辆行为的记录，需要保证恶意车辆和自私车辆无法修改。
4. 分布式管理：针对车联网环境下的信誉管理需求，处理上报消息、信誉值的更新、查询过程都需要以分布式的形式由不同组织完成，多组织分布式地进行信誉管理也提高了系统的可拓展性。

## 系统分析

### 对攻击行为的安全分析

保留4.B部分

### 对系统设计需求的分析

1. 可靠性(reliability)分析：因此只有当确定事件结果后，信誉值才会根据真实的结果进行增减。
2. 有效性分析：根据实验的结果，R-tracing可以在多组织参与信誉值管理的情况下完成车辆对信誉值的高效处理，具有较大的吞吐量和较小的存储负担。
3. 不可篡改性分析：假设攻击者想要修改存储在链上的上报信息，授权的组织节点可以根据车辆上报信息对车辆信誉值进行计算验证，攻击者无法通过身份验证因此不具备访问区块链的权利，因此无法对区块链上的信誉信息进行修改。
4. 分布式管理分析：R-tracing将车联网下信誉管理活动抽象为三种消息交易结构和四个智能合约，PD DMV和基站都可以通过调用自己所属的智能合约完成信誉管理。

# 区块链实验

## 增加指标

confirmation time

storage overhead