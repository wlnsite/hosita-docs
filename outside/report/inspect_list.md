# 查询检验报告单列表

- **接口说明：** 查询检验报告单列表，此接口要注意过滤`是否审核`后的结果
- **接口地址：** /api/report/inspect_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | patient_id | string | C | 所属就诊档案（卡）Id |
    | mintime | unix | O | 查询起始时间，Unix时间戳（精确到秒），为空不限制  |
    | maxtime | unix | O | 查询截止时间，Unix时间戳（精确到秒），为空不限制  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：报告记录列表（按时间排序） |
    | - patient_id | string | R | 所属就诊档案（卡）Id |
    | - patient_name | string | R | 所属就诊档案（卡）姓名 |
    | - apply_time | string | R | 发起时间，Unix时间戳（精确到秒） |
    | - apply_dept_id | string | R | 发起科室Id |
    | - apply_dept_name | string | R | 发起科室名称 |
    | - apply_doctor_id | string | R | 发起医生Id |
    | - apply_doctor_name | string | R | 发起医生姓名 |
    | - project_code | string | R | 检测项目编码 |
    | - project_name | string | R | 检测项目名称 |
    | - categroy_code | string | R | 检测类别编码 |
    | - categroy_name | string | R | 检测类别名称 |
    | - test_time | unix | R | 检测时间，Unix时间戳（精确到秒） |
    | - sample_id | string | O | 检测样本ID |
    | - device_id | string | O | 检测设备ID |