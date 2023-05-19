# 查询住院患者日清单

- **接口说明：** 查询住院患者日清单
- **接口地址：** /api/inhospital/daily_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | zyh | string | C | 住院档案号 |
    | inhops_no | string | C | 住院流水号 |

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
    | - fee_date | string | R | 费用日期 |
    | - sum_amount | decimal | R | 合计金额 |
