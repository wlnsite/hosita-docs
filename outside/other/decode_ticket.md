# Ticket换取身份信息

- **接口说明：** 通过Ticket换取用户身份信息
- **接口地址：** /api/decode_ticket[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | ticket | string | R | 用户身份信息换取凭据 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：200-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 就诊人信息[[对象实体]](entity/patient.md) |


