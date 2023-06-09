# 查询挂号预约记录

- **接口说明：** 查询挂号预约记录
- **接口地址：** /api/outpatient/register_pre
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | pre_id | string | C | 所属就诊档案（卡）Id |
    | patient_id | string | C | 所属就诊档案（卡）Id |
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：预约记录列表 |
    | - pre_id | string | R | 预约单号 |
    | - see_no | string | C | 看诊序号 |
    | - reg_fee | decimal | C | 挂号费用 |
    | - operator_time | string | R | 预约挂号时间（格式：`HH:mm:ss`） |
    | - register_date | string | R | 挂号就诊日期（格式：`yyyy-MM-dd`） |
    | - register_time | string | R | 挂号就诊时间（格式：`HH:mm:ss`） |
    | - reg_level_id | string | R | 挂号级别ID |
    | - reg_level_name | string | R | 挂号级别名称 |
    | - dept_id | string | R | 挂号科室编号（唯一标识） |
    | - dept_name | string | R | 挂号科室名称 |
    | - doctor_id | string | R | 出诊医生ID，0或空为轮值医生，其它值为医生ID |
    | - doctor_name | string | R | 出诊医生名称，留空为轮值医生 |