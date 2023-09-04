# 发起退费接口

- **接口说明：** 发起退费接口
- **接口地址：** /api/refund_apply[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | trade_no | string | R | 支付时的交易流水号 |
    | his_refund_id | string | R | 业务系统退费请求唯一编号 |
    | his_refund_time | string | long | R | 业务系统退费时间（Unix时间戳） |
    | amount_si | int | C | 医保统筹退费金额，不退时为零（单位：分） |
    | amount_acc | int | C | 医保个账退费金额，不退时为零（单位：分） |
    | amount_cash | int | C | 现金支付退费金额，不退时为零（单位：分） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | string | R | 退费发起成功时返回退费流水号，后续可使用此流水号查询退费状态 |