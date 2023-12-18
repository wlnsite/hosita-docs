# 微信模板消息推送透传接口

- **接口说明：** HIS侧通过此接口直接推送微信模板消息（无需AccessToken）
- **接口地址：** /api/push_weixin[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：** 直接透传业务参数，请参考：[微信官方文档](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#%E5%8F%91%E9%80%81%E6%A8%A1%E6%9D%BF%E6%B6%88%E6%81%AF)

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：0-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | string | R | 微信官方返回的消息 |

