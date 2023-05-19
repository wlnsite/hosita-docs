# 挂号缴费提交

- **接口说明：** 挂号缴费提交
- **接口地址：** /api/outpatient/register_commit
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | mzh | string | R | 患者门诊号 |
    | index | string | R | 门诊流水号 |
    | patient_id | string | R | 所属就诊档案（卡）Id |
    | patient_name | string | O | 所属就诊档案（卡）姓名 |
    | trade_no | string | R | 平台交易流水号 |
    | trade_channel_payid | string | O | 支付通道交易流水号 |
    | channel_id | string | C | 缴费渠道ID |
    | channel_name | string | O | 缴费渠道名称（可选提供） |
    | operator_id | string | C | 操作员ID |
    | operator_name | string | O | 操作员姓名（可选提供） |


- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：挂号提交结果 |
    | - see_no | string | R | 看诊序号 |
    | - reconciliation_no | string | R | HIS单据号 |