# 来源资料约定

人口与服务内部明细及公开申请，用于公开表物化流程。

所有人员、机构、地址、业务事件及数值均为合成，不来自真实企业或个人。UTF-8 编码，日期为 ISO 8601，时间附明确时区。有效区间左闭右开，空结束值为尚无结束记录，不据此推断未来。金额使用整数分，非整数数量用十进制字符串；未知不是零。

persons为格内人员去重，services为来源行去重，amount_fen可加。阈值5人，1到4人为原始受保护格，真正为零可公开；金额随受保护人数隐藏。相同群体版本内村及年龄互斥、服务类不互斥。抑制需保证受保护格人数不能由本轮与历史披露精确数值、公开总计、互斥关系与非负整数条件唯一确定。可保守隐藏或拒绝细化，须解释原因；安全且资料齐全的独立合计仍应可获得，不能全部拒绝代替处理。群体成员版本未证明相同时拒绝跨期细分差分申请。公开目录未预置披露值，历史记录由实际发布产生。

## service_details

一人可以有多次多类服务。

- row_id：行键
- person_id：人员
- village：村
- age_band：年龄组
- service：类别
- month：业务月
- amount_fen：分

## requests

待预览请求，不代表已经披露。

- request_id：申请
- group_by：分组维度
- filters：筛选集合
- measures：度量
- cohort：群体
- month：月

## coverage

资料不齐不是零。

- village：村
- month：月
- complete：是否完整

## cohort_stability

跨期群体相同性须有明确证明。

- cohort：群体
- month：月
- membership_version：成员版
- stable_with：成员相同月份

## corrections

原始更正事件。

- change_id：事件
- row_id：来源行
- new_village：新村
- received_at：收到

同一人员在同月的村和年龄属于成员属性，同一次收到的C1与C2共同更正P1的全部服务行；独立行到达产生互斥属性冲突时，该群体应待核，不能把同一个人当两村互斥成员。一个received_at内的更正构成来源声明的完整更正包。
