# 查询排班计划分组

- **接口说明：** 查询排班计划分组
- **接口地址：** /api/outpatient/schedule_group
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | date | string | R | 排班所属日期（格式：yyyy-MM-dd） |
    | dept_id | string | R | 科室Id |
    | doctor_id | string | O | 医生Id（可选参数） |
    | reg_level | string | O | [挂号级别](enums?id=reg_level)（可选参数） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：排班计划列表 |
    | - schedule_no | string | R | 计划编号 |
    | - schedule_type | string | R | 计划分类 |
    | - reg_fee | int | R | 挂号费用（单位：分） |
    | - reg_count | int | R | 可用余号 |
    | - reg_level_id | string | R | [挂号级别](enums?id=reg_level)（可选参数） |
    | - reg_level_name | string | O | 挂号级别名称 |
    | - partime | bool | R | 是否分时段，true或false |
    | - schedule_date | string | R | 出诊日期（格式：`yyyy-MM-dd`） |
    | - schedule_time_zones | string | R | 出诊时间区间（如：`08:30-12:30`） |
    | - dept_id | string | R | 科室编号（唯一标识） |
    | - dept_name | string | R | 科室名称（院内简称） |
    | - department_code | string | O | 科室注册编码 |
    | - department_name | string | O | 科室注册名称 |
    | - department_caty | string | O | 医保可别编码 |
    | - doctor_id | string | R | 出诊医生ID，0或空为轮值医生，其它值为医生ID |
    | - doctor_name | string | R | 出诊医生名称，留空为轮值医生 |
    | - doctor_regcode | string | O | 医师注册编码 |
    | - doctor_regname | string | O | 医师注册姓名 |
    | - med_list_codg | string | O | 医疗目录编码 |
    | - med_list_name | string | O | 医疗目录名称 |
    | - med_list_specs | string | O | 医疗目录规格 |
    | - medins_list_codg | string | O | 医药机构目录编码 |
    | - hosp_appr_flag | int | O | 医院审批标志，1：已审批，2：转自费 |


