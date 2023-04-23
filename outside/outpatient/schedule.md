# 查询排班计划列表

- **接口说明：** 查询排班计划列表
- **接口地址：** /api/outpatient/schedule
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
    | - schedule_id | string | R | 计划编号 |
    | - reg_level | string | O | [挂号级别](enums?id=reg_level)（可选参数） |
    | - schedule_date | string | R | 出诊日期（格式：`yyyy-MM-dd`） |
    | - schedule_time | string | R | 出诊时间（格式：`HH:mm:ss`） |
    | - dept_id | string | R | 科室编号（唯一标识） |
    | - dept_name | string | R | 科室名称 |
    | - department_code | string | O | 科室注册编码 |
    | - department_name | string | O | 科室注册名称 |
    | - doctor_id | string | R | 出诊医生ID，0或空为轮值医生，其它值为医生ID |
    | - doctor_name | string | R | 出诊医生名称，留空为轮值医生 |
    | - doctor_code | string | O | 医师注册编码 |
    | - doctor_name | string | O | 医师注册姓名 |