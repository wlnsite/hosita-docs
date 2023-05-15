# 查询患者预缴费记录

- **接口说明：** 查询患者预缴费记录
- **接口地址：** /api/inhospital/prepay_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | id | string | C | 就诊档案（卡）ID |
    | zyh | string | C | 住院档案号 |
    | inhops_no | string | C | 住院流水号 |
    `说明：以上参数至少要有一个，zyh不为空时优先使用此条件`
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：预缴记录列表（按时间排序） |
    | - zyh | string | R | 住院档案号 |
    | - inhosp_no | string | R | 住院流水号（第几次住院） |
    | - dept_id | string | R | 所属科室Id |
    | - dept_name | string | R | 所属科室名称 |
    | - patient_id | string | R | 所属就诊档案（卡）Id |
    | - patient_name | string | R | 所属就诊档案（卡）姓名 |
    | - amount | decimal | R | 预缴金额 |
    | - trade_no | string | O | 交易流水号 |
    | - trade_time | unix | R | 预缴费时间，Unix时间戳（精确到秒） |
    | - trade_channel_code | string | O | 缴费渠道编码 |
    | - trade_channel_name | string | O | 缴费渠道名称 |
    | - reconciliation_no | string | C | HIS单据号 |