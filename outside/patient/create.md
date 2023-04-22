# 就诊信息建档


- **接口说明：** 根据用户信息创建就诊卡
- **接口地址：** /api/patient/create
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | name | string | R | 就诊人姓名 |
    | idcard | string | R | 就诊人证件号 |
    | mobile | string | R | 就诊人手机号 |
    | sex | int | O | [性别](enums?id=sex)：0-未知,1-男,2-女 |
    | age | string | O | 年龄 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：就诊人（卡）信息 |
    | - patient_id | string | R | 成功时返回就诊人（卡）ID |