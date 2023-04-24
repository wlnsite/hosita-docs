# 收费项目查询


- **接口说明：** 收费项目查询
- **接口地址：** /api/hospital/charge_item
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | item_id | string | O | 收费项目编号 |
    | branch_id | string | O | 院区编号 |
    | spell_code | string | O | 助记码(拼音码) |
    | term_type_id | string | O | 术语类别ID |
    | valid_flag | string | O | 有效性标志，值为“all/true/false”,默认为ALL |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：收费项目列表 |
    | - item_id | string | R | 项目编号 |
    | - item_name | string | R | 项目名称 |
    | - unit | string | O | 计量单位 |
    | - price | double | O | 单价 |
    | - specs | string | O | 规格，如：1 g×1000 g/kg |
    | - spell_code | string | O | 助记码(拼音码) |
    | - valid_flag | int | O | [有效性标识](enums?id=valid)，0：无效，1：有效 |