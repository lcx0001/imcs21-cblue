# imcs21-cblue
This is the repo of the medical dialogue dataset <imcs21> in CBLUE@Tianchi

### 背景

随着“互联网+医疗”的迅速发展，在线问诊平台逐渐兴起，在线问诊是指医生通过对话和患者进行病情的交流、 疾病的诊断并且提供相关的医疗建议。
在政策和疫情的影响之下，在线问诊需求增长迅速。然而医生资源是稀缺的， 由此促使了自动化医疗问诊的发展，以人机对话来辅助问诊过程。

### [任务1：医疗命名实体识别]（https://github.com/lemuria-wchen/imcs21-cblue/tree/main/task1)

医疗命名实体广泛存在于医患对话中，它们是理解对话意图的关键因素，也是构建智能医疗对话系统的基础任务。
本数据集对 **3,052** 个完整的医疗对话（共 **123,762** 条句子）中的命名实体进行了**字级别**的标注，共包含**5类**命名实体，
标注方式采用*BIO三位标注*（其中B-X代表实体X的开头，I-X代表实体的结尾，O代表不属于任何类型）。

### [任务2：症状识别]（https://github.com/lemuria-wchen/imcs21-cblue/tree/main/task2)

症状是医患对话中主要讨论的话题之一，病人的症状信息也是对话策略和疾病诊断的关键特征。使用BIO标注可以找出症状实体所在的位置，
然而在实际应用中，还存在两个问题：

- 症状实体未规范化，即相同的症状可能有多种表达方式，如发烧、热、发热都表示发热这一症状；
- 症状与患者的关系未知，比如某些症状实体即使出现在对话中，病人也不一定就患有这些症状。

本数据集对 **3,052** 个完整的医疗对话中的所有的症状实体进行了进一步的标注，对于每个症状实体，
我们额外标注了其**标准化的名称**，还标注了这些**症状与病人的关系**，其中每种症状都可分为三类，分别是*有*、*没有*和*不确定*。

标注方式采用**对话级标注**，即对每个医疗对话，我们标注出在该对话中出现过的症状及其与病人之间的关系，以字典的形式给出：

```json
{
  "症状1": "有",
  "症状2": "不确定",
  "症状3": "没有"
}
```

### [任务3：医疗报告生成]（https://github.com/lemuria-wchen/imcs21-cblue/tree/main/task3)

医疗报告是医生对病人健康状况的总结，是医疗诊断过程的重要环节。本数据集对 **3,052** 个完整的医疗对话手动标注了相应的医疗报告。
标注方式采用**对话级标注**，即对于每个医疗对话，分别有2个标注者阅读完整的医疗对话，并编写具有规定格式的医疗报告，即一个对话具有两个供参考的医疗报告。
