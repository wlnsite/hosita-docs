# 微信公众号AccessToken获取接口

- **接口说明：** 三方应用使用此接口获取AccessToken（AccessToken有多个系统同时使用，会集中刷新）
- **接口地址：** /wxgzh/access_token
- **请求方式：** POST
- **请求参数：** 无

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：0-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | string | R | 成功时返回当前AccessToken |

