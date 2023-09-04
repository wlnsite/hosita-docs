# 统一退费查询接口

- **接口说明：** 统一退费查询接口
- **接口地址：** /api/refund_query[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | his_refund_id | string | O | 业务系统发起退费时的请求编号，`refund_trade_no`为空时此字段不能为空 |
    | refund_trade_no | string | O | 发起退费时返回的交易流水号，`his_refund_id`为空时此字段不能为空 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：退费记录详情 |
    | - trade_no | string | R | 支付时的交易流水号 |
    | - his_refund_id | string | R | 业务系统发起退费时的单号  |
    | - his_refund_time | long | R | 业务系统退费时间（Unix时间戳） |
    | - refund_trade_no | string | R | 退费时的交易流水号 |
    | - refund_trade_time | long | R | 支付平台受理退费的时间（Unix时间戳） |
    | - setl_id | string | R | 医保退款结算ID |
    | - mdtrt_id | string | O | 医保退款就诊ID |
    | - med_trans_id | string | O | 支付平台医疗订单号 |
    | - si_refund_id | string | R | 医保退款流水号 |
    | - si_refund_time | long | R | 医保退款完成时间（Unix时间戳） |
    | - cash_refund_id | string | R | 现金退款流水号 |
    | - cash_refund_time | long | R | 现金退款完成时间（Unix时间戳） |
    | - amount_si | int | R | 医保统筹退费金额，未退时为零，负数代表已退费金额（单位：分） |
    | - amount_acc | int | R | 医保个账退费金额，未退时为零，负数代表已退费金额（单位：分） |
    | - amount_cash | int | R | 现金支付退费金额，未退时为零，负数代表已退费金额（单位：分） |
    | - amount_reduction | int | R | 政策减免退费金额，未退时为零，负数代表已退费金额（单位：分） |

