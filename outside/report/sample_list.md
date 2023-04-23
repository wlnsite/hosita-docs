# 查询检测样本列表

- **接口说明：** 查询检测样本列表
- **接口地址：** /api/report/sample_list
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
    | - sample_id | string | R | 检测样本ID |
    | - sample_barcode | string | O | 检测样本条码号 |
    | - sample_state | int | R | 样本状态(1.已核收 2.有结果 3已审核 4已打印) |
    | - sample_type_id | string | O | 检测类型id |
    | - sample_type_name | string | O | 检测类型名称，如：血清 |
    | - client_id | string | O | 所属检查人Id |
    | - client_name | string | O | 所属检查人姓名 |
    | - client_type | string | O | 患者类型，如：住院 |
    | - project_code | string | O | 检测项目编码 |
    | - project_name | string | O | 检测项目名称 |
    | - project_price | decimal | O | 检测项目单价 |
    | - categroy_code | string | O | 检测类别编码 |
    | - categroy_name | string | O | 检测类别名称 |
    | - test_time | unix | O | 检测时间，Unix时间戳（精确到秒） |
    | - test_type | string | O | 检测类型 |
    | - device_id | string | O | 检测设备ID |
    | - diagnosis | string | O | 医生诊断信息 |
    | - apply_time | string | O | 发起时间，Unix时间戳（精确到秒） |
    | - apply_dept_id | string | O | 发起科室Id |
    | - apply_dept_name | string | O | 发起科室名称 |
    | - apply_doctor_id | string | O | 发起医生Id |
    | - apply_doctor_name | string | O | 发起医生姓名 |
    | - exec_time | string | O | 执行时间，Unix时间戳（精确到秒） |
    | - exec_dept_id | string | O | 执行科室Id |
    | - exec_dept_name | string | O | 执行科室名称 |
    | - exec_doctor_id | string | O | 执行医生Id |
    | - exec_doctor_name | string | O | 执行医生姓名 |
    | - print_time | string | O | 首次打印时间，Unix时间戳（精确到秒） |
    | - print_operator_id | string | O | 打印人员Id |
    | - print_operator_name | string | O | 打印人员姓名或自助渠道名 |