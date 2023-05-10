# 查询挂号科室


- **接口说明：** 根据指定日期查询挂号科室
- **接口地址：** /api/outpatient/register_department_list
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | date | string | R | 出诊日期（格式：`yyyy-MM-dd`） |
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

`注意：输出的科室仅为指定日期仍有号源的科室，如下午查询时XX科室仅上午可挂号则列表中就不显示此科室`