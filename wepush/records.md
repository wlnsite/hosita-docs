# 推送场景查询

- **接口说明：** 查询消息推送记录
- **接口地址：** /push/records
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述                                             |
    | -------- | -------- | -------- | ------------------------------------------------ |
    | size     | int      | O        | 查询结果返回的列表长度，取值范围：0~1000         |
    | offset   | int      | O        | 分页查询列表偏移量                               |
    | scene_id | string   | O        | 查询指定消息场景的推送记录  |
    | mintime  | long     | O        | 查询起始时间，Unix时间戳（精确到秒），为空不限制 |
    | maxtime  | long     | O        | 查询截止时间，Unix时间戳（精确到秒），为空不限制 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：0-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 返回符合条件的记录信息 |
    | - record_id | string | R | 记录ID |
    | - scene_id | string | R | 推送记录所属场景编号 |
    | - scene_title | string | R | 推送记录所属场景名称 |
    | - msg_data | object | R | 消息数据，具体定义请参考场景的参数定义 |
    | - msg_link | string | O | 详情连接，点击消息可打开的页面连接 |
    | - send_time | long | O | 推送时间，Unix时间戳（精确到秒） |
    | - send_state | string | R | 推送消息发送状态 |
    | - user_key | string | R | 接收对象：用户标识，如手机号、OpenId等 |
    | - platform | string | R | 接收对象：[平台类型](wepush/_enums?id=platform) |


