# 医生列表查询

- **接口说明：** 查询医生列表
- **接口地址：** /api/hospital/doctor_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | dept_id | string | O | 科室Id |
    | branch_id | string | O | 院区Id。为空时查询所有院区下属医生 |
    | staff_type | string | O | 人员类型。为空时查询所有类型人员 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：医生信息列表 |
    | - doctor | object | A | 医生信息[[对象实体]](entity/doctor.md) |