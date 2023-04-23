# 住院患者预交金充值

- **接口说明：** 住院患者预交金充值
- **接口地址：** /api/inhospital/prepay
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | zyh | string | R | 住院档案号 |
    | index | string | R | 本次交易总的结算序号 |
    | amount | decimal | R | 预缴金额 |
    | trade_no | string | R | 交易流水号 |
    | trade_time | unix | R | 交易支付时间，Unix时间戳（精确到秒） |
    | payment | string | O | [支付方式](enums?id=payment) |
    | patient_id | string | R | 所属就诊档案（卡）Id |
    | patient_name | string | O | 所属就诊档案（卡）姓名 |
    | channel_id | string | C | 缴费渠道ID |
    | channel_name | string | O | 缴费渠道名称（可选提供） |
    | operator_id | string | C | 操作员ID |
    | operator_name | string | O | 操作员姓名（可选提供） |
    | operator_time | unix | O | 操作时间，Unix时间戳（精确到秒），默认为当前 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：预缴充值结果 |
    | - zyh | string | R | 住院档案号 |
    | - amount | decimal | R | 本次预缴金额 |
    | - trade_no | string | R | 交易流水号 |
    | - balance | decimal | R | 预缴款余额（负数为欠费） |
    | - reconciliation_no | string | R | HIS单据号 |