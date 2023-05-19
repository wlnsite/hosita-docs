# 查询用户电子发票列表

- **接口说明：** 查询用户电子发票列表，可按档案Id及时间区间查询或单独按所属处方单据查询
- **接口地址：** /api/other/invono_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | patient_id | string | C | 所属就诊档案（卡）Id |
    | recipe_id | string | C | 所属处方单据ID |
    | type_flag | string | C | 发票类型标志：1-正常发票 2-冲红发票 |
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：发票记录列表（按时间排序） |
    | - id | string | R | 发票记录Id |
    | - no | string | R | 电子票据号码 |
    | - code | string | R | 电子票据代码 |
    | - verify | string | R | 电子票据校验码 |
    | - qrcode | string | R | 电子票据二维码 |
    | - amount | string | R | 发票金额 |
    | - recipe_id | string | R | 所属处方单据ID |
    | - patient_id | string | R | 所属就诊档案（卡）Id |
    | - down_url | string | R | 发票下载地址 |
    | - bill_time | string | R | 开票时间 |
    | - type_code | string | R | 费用类型编码 |
    | - type_name | string | R | 费用类别名称 |
    | - type_flag | string | R | 发票类型标志：1-正常发票 2-冲红发票 |
    | - state_code | string | O | 发票状态编码 |
    | - state_name | string | O | 发票状态名称 |