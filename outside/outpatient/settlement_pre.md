# 处方预结算


- **接口说明：** 处方预结算
- **接口地址：** /api/outpatient/settlement_pre
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | patient_id | string | R | 所属就诊档案（卡）Id |
    | recipe_list | array | R | 预结算的处方ID列表 |
    | channel_id | string | C | 缴费渠道ID |
    | channel_name | string | O | 缴费渠道名称（可选提供） |
    | operator_id | string | C | 操作员ID |
    | operator_name | string | O | 操作员姓名（可选提供） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：锁号结果 |
    | - result | bool | R | 是否成功，true或false |
    | - total_fee | decimal | R | 预结算总费用 |
    | - diagnose_list | array | R | 诊断信息列表[[对象实体]](entity/diagnose.md) |    
    | - feedetail_list | array | R | 费用明细列表[[对象实体]](entity/feedetail.md) |