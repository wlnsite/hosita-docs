# 挂号已缴费退号

- **接口说明：** 挂号已缴费退号，流程：生成退费单 => 退号 => 实际退费
- **接口地址：** /api/outpatient/register_refund
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | mzh | string | R | 患者门诊号 |
    | index | string | R | 门诊流水号 |
    | return_trade_no | string | R | 退费交易流水号 |
    | return_trade_time | string | R | 退费交易时间 |
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
    | - result | bool | R | 退号是否成功 |
    | - reconciliation_no | string | R | HIS单据号 |