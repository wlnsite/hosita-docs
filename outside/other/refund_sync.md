# 业务系统退费结果同步接口

- **接口说明：** HIS侧退费时，退费结果同步接口
- **接口地址：** /api/refund_sync
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | trade_no | string | R | 支付时的交易流水号 |
    | his_refund_id | string | R | 业务系统退费请求唯一编号 |
    | his_refund_time | string | long | R | 业务系统退费时间（Unix时间戳） |
    | amount_si | int | C | 医保统筹退费金额，未退时为零（单位：分） |
    | amount_acc | int | C | 医保个账退费金额，未退时为零（单位：分） |
    | amount_cash | int | C | 现金支付退费金额，未退时为零（单位：分） |
    | setl_id | string | R | 医保结算单号 |
    | setl_type | string | O | 结算类型 ALL:医保自费全部，CASH:只结现金 HI:只结医保 |
    | mdtrt_id | string | O | 医保就诊ID |
    | med_trans_id | string | O | 支付平台医疗订单号 |
    | med_refund_id | string | O | 发起交易时的报文ID |
    | si_refund_id | string | R | 医保退款流水号 |
    | si_refund_time | long | R | 医保退款完成时间（Unix时间戳） |
    | cash_refund_id | string | R | 现金退款流水号 |
    | cash_refund_time | long | R | 现金退款完成时间（Unix时间戳） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | string | R | 同步成功时返回同步后的交易流水号 |

