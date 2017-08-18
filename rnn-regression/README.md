### 1.项目介绍

探索企业征信回归模型。由于数据包含私人信息，暂不提供。该项目主要提供对csv文件数据的处理过程。

### 2.数据情况

- 企业征信数据记录每个企业12个月的财务相关数据，一个月一行。其中前4列:第一列是org_id, 第二列是accountbook, 第三列是period，以及第四列是审批的金额。
- 目前数据总量：126037。其中，正常数据：125052，包含10421家企业（含全部12个月）。
- 其中6923家企业审批金额大于2万，剩余的3498家企业审批金额为2万

### 3.模型训练情况

- 由于数据不均衡，直接考虑二分类（>2万，=2万）会存在问题
- 先考虑使用回归来直接预测金额

指标 | all | 大于2万
--- | --- | ---
max test loss |231.159 |292.057
min test loss | 183.929| 239.936

### 4.结论

经过了调优，效果仍然不理想。可能有三种情况：
（1）数据可能有问题，需要从原始数据重新开始进行预处理
（2）模型不适合采用rnn来进行回归，可以考虑 LR 或者 DNN来预测
（3）可能数据不存在一定的规律

