# 根据处方号查询处方明细信息

- **接口说明：** 根据处方号查询处方明细信息
- **接口地址：** /api/outpatient/recipe_info
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | recipe_id | string | R | 处方号Id |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 处方信息[[对象实体]](entity/recipe.md) |