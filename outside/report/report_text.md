# 查询检查文字报告单

- **接口说明：** 查询检查文字报告单
- **接口地址：** /api/report/report_text
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | report_id | string | C | 报告单Id |
    | patient_id | string | C | 所属就诊档案（卡）Id |
    `说明：以上参数至少要有一个，report_id不为空时优先使用此条件`

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：报告记录列表（按时间排序） |
    | - report_id | string | R | 报告Id |
    | - report_time | string | R | 发起时间，Unix时间戳（精确到秒） |
    | - client_id | string | O | 所属检查人Id |
    | - client_name | string | O | 所属检查人姓名 |
    | - client_type | string | O | 患者类型，如：住院 |
    | - result_code | string | O | 结果值，如：0-阴性 1-阳性|
    | - result_name | string | O | 结果名称，如：阳性 |
    | - result_image | string | O | Base64编码后的报告图片 |