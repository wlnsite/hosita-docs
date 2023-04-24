# 不按计划直接挂号

- **接口说明：** 不按计划直接挂号
- **接口地址：** /api/outpatient/register_direct
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | dept_id | string | R | 挂号科室编号（唯一标识） 
    | doctor_id | string | R | 出诊医生ID，0或空为轮值医生，其它值为医生ID |
    | reg_level_id | string | R | [挂号级别](enums?id=reg_level)（可选参数） |
    | register_date | string | R | 计划就诊日期（格式：`yyyy-MM-dd`），留空为当天 |
    | register_time | string | R | 计划就诊时间（格式：`HH:mm:ss`），留空为当天 |
    | client_id | string | R | 用户Id |
    | patient_id | string | C | 挂号人就诊档案（卡）Id |
    | patient_name | string | O | 挂号人就诊档案（卡）姓名 |
    | channel_id | string | C | 缴费渠道ID |
    | channel_name | string | O | 缴费渠道名称（可选提供） |
    | operator_id | string | C | 操作员ID |
    | operator_name | string | O | 操作员姓名（可选提供） |
    | amount | decimal | R | 预缴金额 |
    | trade_no | string | R | 交易流水号 |
    | trade_time | unix | R | 交易支付时间，Unix时间戳（精确到秒） |
    | payment | string | O | [支付方式](enums?id=payment) |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：锁号结果 |
    | - result | bool | R | 是否成功，true或false |
    | - register_date | string | R | 挂号就诊日期（格式：`yyyy-MM-dd`） |
    | - register_time | string | R | 挂号就诊时间（格式：`HH:mm:ss`） |
    | - register_no | string | C | 挂号单据号 |
    | - reg_level_id | string | R | 挂号级别ID |
    | - reg_level_name | string | R | 挂号级别名称 |
    | - reg_fee | decimal | C | 挂号费用 |
    | - see_no | string | C | 看诊序号 |