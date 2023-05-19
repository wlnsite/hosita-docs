# 患者待缴费处方单

- **接口说明：** 患者待缴费处方单
- **接口地址：** /api/outpatient/unpaidfees
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | patient_id | string | C | 所属就诊档案（卡）Id |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：挂号记录列表 |
    | - recipe_id | string | R | 处方ID |
    | - should_money | decimal | R | 应付金额 |
    | - actual_money | decimal | R | 实付金额 |
    | - billing_time | string | R | 开单时间 |    
    | - dept_id | string | R | 挂号科室编号（唯一标识） |
    | - dept_name | string | R | 挂号科室名称 |
    | - register_no | string | C | 挂号单据号 |
    | - fee_category_code | string | C | [费用类别](enums?id=fee_category) |
    | - fee_category_name | string | C | 费用类别名称 |
    | - pay_merge | bool | R | 是否可合并缴费 |
    | - med_type | string | C | 医疗类别 |