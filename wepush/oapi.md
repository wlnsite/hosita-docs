# 统一推送接口

- **接口说明：** 可按患者`pid`自动匹配接收用户信息
- **接口地址：** /push/oapi
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | pid      | string | C | 业务系统用户ID，与接收对象二选一 |
    | touser   | object | C | 接收对象，与用户ID二选一 |
    | - user_key | string | R | 接收对象：用户标识，如手机号、OpenId等 |
    | - platform | string | R | 接收对象：[平台类型](wepush/_enums?id=platform) |
    | scene_id | string | R | 推送通道编号 |
    | msg_data | object | R | 消息数据，具体定义请参考场景的参数定义 |
    | msg_link | string | O | 详情连接，点击消息可打开的页面连接 |
    | send_time | long | O | 推送时间，Unix时间戳（精确到秒），值小于当前时间立即推送，大于当前时间则定时推送 |
    | send_trade_no | string | O | 推送如需关联业务单号时需要填写 |
- **请求示例：**
```
{"pid":"2023080001","scene_id":"100001","msg_data":{"title":"挂号受理成功","trade_no":"202311221543156473207259","name":"张三","mdtrt_time":"2023-12-15 14:30 ~ 17:30","mdtrt_info":"便民门诊 轮值医生","address":"门诊一楼"},"msg_link":"https://devtest.wlniao.com/wxgzh/enter/gh","send_time":0,"send_trade_no":""}
```
- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | C | 输出数据：推送发起成功时有返回 |
    | - record_id | string | R | 消息推送记录ID |
    | - user_key | string | R | 接收对象：用户标识，如手机号、OpenId等 |
    | - platform | string | R | 接收对象：[平台类型](wepush/_enums?id=platform) |

