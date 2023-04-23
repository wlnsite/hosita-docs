# 根据样本查询检测报告内容

- **接口说明：** 根据样本查询检测报告内容，此接口要注意过滤`是否审核`后的结果
- **接口地址：** /api/report/sample_report
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | sample_id | string | R | 检测样本Id |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：报告记录列表（按时间排序） |
    | - sample_id | string | R | 检测样本ID |
    | - device_id | string | O | 检测设备ID |
    | - test_time | unix | O | 检测时间，Unix时间戳（精确到秒） |
    | - test_type | string | O | 检测类型 |
    | - test_method | string | O | 检测方法 |
    | - item_id | string | O | 检测内容Id |
    | - item_name | string | O | 检测内容名称 |
    | - value_unit | string | O | 检验单位，如：pg/mL |
    | - value_desc | string | O | 描述结果 |
    | - value_list | string | O | 结果列表（历史值） |
    | - value_report | string | O | 报告结果（检测值） |
    | - value_original | string | O | 原始结果（检测值） |
    | - value_return | string | O | 复查前结果（检测值） |
    | - value_range | string | O | 参考范围，如：0~7 |
    | - result_flag | string | O | 结果标识 |
    | - alert_flag | string | O | 危急值标识 |
    | - alert_range | string | O | 危急值范围 |