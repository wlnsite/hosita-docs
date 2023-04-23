# 科室列表查询


- **接口说明：** 查询医院科室列表
- **接口地址：** /api/hospital/department_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | dept_id | string | O | 上级Id。不传时仅查询一级科室，传值时查询下级科室 |
    | dept_type | string | R | 科室类型。N病区,C门诊,F财务,T医技,L后勤,OT其他等 |
    | branch_id | string | O | 院区Id。为空时查询所有院区下属科室 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：科室列表 |
    | - dept_id | string | R | 科室编号 |
    | - dept_name | string | R | 科室名称 |
    | - branch_id | string | O | 所属院区编号 |
    | - branch_name | string | O | 所属院区名称 |
    | - address | string | O | 科室院内地址 |