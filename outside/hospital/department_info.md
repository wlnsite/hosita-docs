# 科室详情查询


- **接口说明：** 按科室ID查询详情
- **接口地址：** /api/hospital/department_info
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | dept_id | string | R | 要查询的科室Id |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | object | R | 输出数据：科室详细信息 |
    | - state | int | Y | [记录状态](enums?id=state) |
    | - dept_id | string | R | 科室编号（唯一标识） |
    | - dept_name | string | R | 科室名称 |
    | - dept_type | string | R | 科室类型 |
    | - department_code | string | N | 科室注册编码 |
    | - department_name | string | N | 科室注册名称 |
    | - branch_id | string | O | 所属院区编号 |
    | - branch_name | string | O | 所属院区名称 |
    | - address | string | C | 科室院内地址 |
    | - latitude | double | O | 地理坐标纬度 |
    | - longitude | double | O | 地理坐标经度 |