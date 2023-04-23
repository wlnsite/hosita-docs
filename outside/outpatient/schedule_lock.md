# 按计划锁号


- **接口说明：** 将排班计划作为号源时使用此接口锁号
- **接口地址：** /api/outpatient/schedule_lock
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | schedule_id | string | R | 锁号的排班计划ID |
    | schedule_date | string | R | 计划就诊日期（格式：`yyyy-MM-dd`），留空为当天 |
    | schedule_time | string | R | 计划就诊时间（格式：`HH:mm:ss`），留空为当天 |
    | client_id | string | R | 用户Id |
    | patient_id | string | C | 挂号人就诊档案（卡）Id |
    | patient_name | string | O | 挂号人就诊档案（卡）姓名 |
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
    | - reg_fee | decimal | C | 挂号费用 |
    | - reg_level | string | C | [挂号级别](enums?id=reg_level)（可选参数） |
    | - schedule_date | string | C | 出诊日期（格式：`yyyy-MM-dd`） |
    | - schedule_time | string | C | 出诊时间（格式：`HH:mm:ss`） |
    | - pre_id | string | C | 预约单号（取消锁号时用） |
    | - see_no | string | C | 看诊序号 |
    | - dept_id | string | O | 科室编号（唯一标识） |
    | - dept_name | string | O | 科室名称 |
    | - department_code | string | C | 科室注册编码（与医保编码一致） |
    | - department_name | string | C | 科室注册名称 |
    | - dept_id | string | O | 所属科室Id |
    | - dept_name | string | O | 所属科室名称 |
    | - doctor_code | string | C | 医师注册编码（与医保编码一致） |
    | - doctor_name | string | C | 医师注册姓名 |