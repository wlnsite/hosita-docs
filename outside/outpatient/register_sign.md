# 门诊签到

- **接口说明：** 门诊签到
- **接口地址：** /api/outpatient/register_sign
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | pre_id | string | C | 预约单号 |
    | register_no | string | C | 挂号单据号 |
    `说明：以上参数至少要有一个，register_no不为空时优先使用此条件`

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：门诊签到结果 |
    | - result | bool | R | 是否成功，true或false |