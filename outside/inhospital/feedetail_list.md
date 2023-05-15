# 查询住院患者费用明细

- **接口说明：** 查询住院患者费用明细
- **接口地址：** /api/inhospital/feedetail_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | zyh | string | C | 住院档案号 |
    | inhops_no | string | C | 住院流水号 |
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |
    | tarde_flag | string | O | 交易类型(1-正交易 2-反交易) 不传值为全查询  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：住院患者日清单列表（按时间排序） |
    | - zyh | string | R | 住院档案号 |
    | - inhops_no | string | R | 住院流水号 |
    | - dept_id | string | R | 住院科室Id |
    | - dept_name | string | R | 住院科室名称 |
    | - patient_id | string | R | 所属就诊档案（卡）Id |
    | - patient_name | string | R | 所属就诊档案（卡）姓名 |
    | - recipe_dept_id | string | R | 开单科室Id |
    | - recipe_dept_name | string | R | 开单科室名称 |
    | - fee_date | unix | R | 费用时间，Unix时间戳（精确到秒） |
    | - fee_type | string | R | 费用类别，如：护理费、检查费等 |
    | - fee_name | string | R | 费用名称，如：Ⅰ级护理(优质护理) |
    | - fee_unit | string | R | 计量单位 |
    | - fee_num | decimal | R | 项目数量 |
    | - fee_price | decimal | R | 项目单价 |
    | - fee_amount | decimal | R | 费用金额 |
    | - tarde_flag | string | O | 交易类型(1-正交易 2-反交易) |