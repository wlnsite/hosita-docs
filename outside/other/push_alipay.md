# 支付宝模板消息推送透传接口

- **接口说明：** HIS侧通过此接口直接推送支付宝模板消息（无需公共参数）
- **接口地址：** /api/push_alipay[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：** 直接透传业务参数，请参考：[支付宝官方文档](https://opendocs.alipay.com/mini/6430ce5a_alipay.open.app.mini.templatemessage.send?scene=common&pathHash=18c2bf3e)

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：0-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | string | R | 支付宝官方返回的消息 |

