# 事务补偿查询检查接口

- **接口说明：** 住院充值、挂号提交、门诊缴费等事务出现无返回等异常情况时进行补充查询
- **接口地址：** /api/other/trade_check
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | trade_no | string | R | 提交时的交易流水号 |
    | business | string | R | [业务类型编码](enums?id=business)：register-挂号 charge-门诊缴费 prepay-住院费预缴 |


- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：补偿业务检查结果 |
    | - reconciliation_no | string | R | 交易流水号存在时，返回HIS系统对应的凭据号，失败时返回：notfound |
    | - trade_time | string | O | 交易流水号存在时，返回HIS系统对应的交易时间 |

