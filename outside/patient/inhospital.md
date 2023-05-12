# 查询就诊人有效的住院信息


- **接口说明：** 查询就诊人有效的住院信息
- **接口地址：** /api/patient/inhospital
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | id | string | C | 就诊档案（卡）ID |
    | zyh | string | C | 住院档案号 |
    | idcard | string | C | 证件号码 |
    `说明：以上参数至少要有一个，zyh不为空时优先使用此条件`
    | state | int | O | [住院状态](enums?id=state_bein)(不传或传空为全查询)  |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：住院记录列表（按时间排序） |
    | - zyh | string | R | 住院档案号 |
    | - inhosp_no | string | R | 住院流水号（第几次住院） |
    | - patient_id | string | R | 所属就诊档案（卡）Id |
    | - patient_name | string | R | 所属就诊档案（卡）姓名 |
    | - bed_no | string | R | 床号 |
    | - dept_id | string | R | 所属科室Id |
    | - dept_name | string | R | 所属科室名称 |
    | - doctor_code | string | O | 主治医生编号 |
    | - doctor_name | string | O | 主治医生姓名 |
    | - check_in | unix | O | 入院时间，Unix时间戳（精确到秒） |
    | - check_out | unix | O | 出医时间，Unix时间戳（精确到秒），未出院时为零 |
    | - state_code | int | R | [住院状态](enums?id=state_bein) |
    | - state_name | int | R | [住院状态](enums?id=state_bein) |
    | - fee_prepay | decimal | R | 已预缴总金额 |
    | - fee_expend | decimal | R | 已消费总金额 |
    | - fee_balance | decimal | R | 预缴款余额（负数为欠费） |
    | - fee_insurance | decimal | R | 医保预报销总金额 |