# 现金支付下单

- **接口说明：** 为终端提供下单服务，基于终端提交的支付订单，生成并返回支付订单号，用于后序支付服务
- **接口地址：** 暂无
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | order_no | string | R | 终端预结算单号 |
    | channel_id | string | R | 结算方渠道ID |
    | terminal_no | string | O | 结算终端号 |
    | total_amount | int | R | 订单金额，单位：分 |
    | efficient_time | unix | O | 订单有效期，Unix时间戳（精确到秒）,最大值为当前时间15分钟内，留空则为最大值 |
    | notify_url | string | O | 业务通知地址 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：支付订单信息（按时间排序） |
    | - channel_id | string | R | 渠道号 |
    | - out_order_no | string | R | 终端预结算单号 |
    | - order_create_time | string | R | 订单创建时间 |
    | - order_efficient_time | string | R | 订单有效时间 |
    | - pay_order_no | string | R | 支付流水号，后续支付使用 |