# 院区查询


- **接口说明：** 查询医院院区列表
- **接口地址：** /api/hospital/part
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | open | string | O | 值为“true”时仅查询开放的院区,为空时默认查询全部院区 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，其它表示异常 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 输出数据：院区列表 |
    | - id | string | R | 院区编号 |
    | - name | string | R | 院区名称 |
    | - address | string | O | 院区地址 |
    | - latitude | double | O | 地理坐标纬度 |
    | - longitude | double | O | 地理坐标经度 |