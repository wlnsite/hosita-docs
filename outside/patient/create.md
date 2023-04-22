# 科室列表查询


- **接口说明：** 就诊信息建档
- **接口地址：** /api/patient/create
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | name | string | R | 就诊人姓名 |
    | idcard | string | R | 就诊人证件号 |
    | mobile | string | R | 就诊人手机号 |
    | sex | string | O | [性别](outside/enums?id=sex)：0-未知,1-男,2-女 |
    | age | string | O | 年龄 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：科室详细信息 |
    | - dept_id | string | R | 科室编号 |
    | - dept_name | string | R | 科室名称 |
    | - part_id | string | C | 所属院区编号 |
    | - part_name | string | C | 所属院区名称 |
    | - address | string | C | 科室院内地址 |
    | - latitude | double | O | 地理坐标纬度 |
    | - longitude | double | O | 地理坐标经度 |