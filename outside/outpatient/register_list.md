# 查询就诊人（卡）挂号记录

- **接口说明：** 查询就诊人（卡）挂号记录
- **接口地址：** /api/outpatient/register_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | patient_id | string | C | 所属就诊档案（卡）Id |
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：排班计划列表 |
    | - state | int | R | /状态：0-新增 1- 已使用 9-删除注销 |
    | - operator_time | string | R | 操作挂号时间（格式：`HH:mm:ss`） |
    | - register_date | string | R | 挂号就诊日期（格式：`yyyy-MM-dd`） |
    | - register_time | string | R | 挂号就诊时间（格式：`HH:mm:ss`） |
    | - reg_level_id | string | R | 挂号级别ID |
    | - reg_level_name | string | R | 挂号级别名称 |
    | - reg_fee | decimal | C | 挂号费用 |
    | - see_no | string | C | 看诊序号 |
    | - see_flag | bool | R | 是否已就诊，true或false |
    | - trade_no | string | O | 交易流水号 |
    | - invoice_no | string | C | 小票单据号 |
    | - dept_id | string | R | 科室编号（唯一标识） |
    | - dept_name | string | R | 科室名称 |
    | - dept_id | string | O | 所属科室Id |
    | - dept_name | string | O | 所属科室名称 |