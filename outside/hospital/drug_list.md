# 药品信息查询

- **接口说明：** 药品信息查询
- **接口地址：** /api/hospital/drug_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | drug_id | string | O | 药品编号 |
    | branch_id | string | O | 院区编号 |
    | drug_type_id | string | O | 药品分类编号 |
    | spell_code | string | O | 助记码(拼音码) |
    | valid_flag | string | O | 有效性标志，值为“all/true/false”,默认为ALL |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：药品信息列表 |
    | - drug_id | string | R | 药品编号 |
    | - drug_name | string | R | 药品名称 |
    | - drug_type_id | string | R | 药品分类编号 |
    | - drug_type_name | string | R | 药品分类名称 |
    | - unit | string | O | 计量单位 |
    | - price | double | O | 单价 |
    | - specs | string | O | 规格，如：1 g×1000 g/kg |
    | - spell_code | string | O | 助记码(拼音码) |
    | - production_enterprises | string | O | 生产厂商名称 |
    | - rx_flag | string | R | 处方药标志，[0：否，1：是](enums?id=yesno) |
    | - valid_flag | int | O | [有效性标识](enums?id=valid)，0：无效，1：有效 |