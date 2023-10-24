# 结算记录查询

- **接口说明：** 结算记录查询
- **接口地址：** /api/trade_list[调用说明](srvapi?id=start)
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | day | string | R | 结算日期，日期格式：`YYYY-HH-MM` |
    | offset | int | R | 偏移量，必须大于等于零 |
    | length | int | R | 获取数据列表长度 |


- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：结算记录信息详情 |
    | - total | int | R | 符合条件的记录总数 |
    | - offset | int | R | 结果偏移量 |
    | - length | int | R | 结果数据集长度 |
    | - list | string | R | 记录数据列表 |
    | 	- id | string | R | 结算单号  |
    | 	- amount | int | R | 结算记录总金额，负数代表退费金额（单位：分） |
    | 	- amount_si | int | R | 医保统筹结算金额，负数代表退费金额（单位：分） |
    | 	- amount_acc | int | R | 医保个账结算金额，负数代表退费金额（单位：分） |
    | 	- amount_cash | int | R | 现金支付结算金额，负数代表退费金额（单位：分） |
    | 	- amount_reduction | int | R | 政策减免金额，负数代表退费金额（单位：分） |
    | 	- time_payed | long | R | 支付系统结算时间（Unix时间戳） |
    | 	- time_trade | long | R | 业务系统结算时间（Unix时间戳） |
    | 	- setl_id | string | O | 医保结算ID（未通过医保结算时此字段值为空） |
    | 	- mdtrt_id | string | O | 医保就诊ID（未通过医保结算时此字段值为空） |
    | 	- med_trans_id | string | O | 支付平台医疗订单号（未通过医保结算时此字段值为空） |
    | 	- cash_pay_id | string | O | 现金在线支付结算单号（未通过现金在线支付时此字段值为空） |
    | 	- terminal_type | string | R | 支付终端/渠道类型：weixin微信,alipay支付宝,client自助机,siapp医保APP |
    | 	- reconciliation_no | string | R | 业务系统结算单号 |
    | 	- trade_channel_payid | string | O | 支付落地平台单号 |



