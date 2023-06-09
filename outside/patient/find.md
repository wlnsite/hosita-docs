# 通过姓名和生日查找患者信息

- **接口说明：** 通过姓名和生日查找患者信息
- **接口地址：** /api/patient/find
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | name | string | R | 姓名 |
    | birthday | string | R | 生日，日期格式：`yyyy-MM-dd` |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 就诊人信息[[对象实体]](entity/patient.md) |