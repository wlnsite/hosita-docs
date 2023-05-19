# 患者待缴费明细清单

- **接口说明：** 患者待缴费明细清单
- **接口地址：** /api/outpatient/unpaidfees_details
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
    | - recipe_fee | decimal | R | 处方费用金额 |
    | - billing_time | string | R | 开单时间 |    
    | - project_code | string | R | 所属项目编码（item_code） |
    | - project_name | string | R | 所属项目名称（item_name） |
    | - count | decimal | R | 数量 |
    | - price | decimal | R | 单价 |
    | - specs | string | R | 规格 |
    | - billing_dept_code | string | R | 开单科室编号（唯一标识） |
    | - billing_dept_name | string | R | 开单科室名称 |
    | - billing_doctor_codg | string | R | 开单医生编码 |
    | - billing_doctor_name | string | R | 开单医生姓名 |
    | - acrod_dept_code | string | R | 受单科室编码 |
    | - acrod_dept_name | string | R | 受单科室名称 |
    | - acrod_doctor_code | string | R | 受单医生编码 |
    | - acrod_doctor_name | string | R | 受单医生名称 |
    | - fee_category_code | string | C | [费用类别](enums?id=fee_category) |
    | - fee_category_name | string | C | 费用类别名称 |
    | - med_type | string | C | 医疗类别 |