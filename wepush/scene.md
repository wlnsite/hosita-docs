# 推送场景查询

- **接口说明：** 查询推送平台中定义的场景信息
- **接口地址：** /push/scene
- **请求方式：** POST
- **请求参数：** 无

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：0-成功，其它表示异常 |
    | success | bool   | R | 执行状态：业务是否成功      |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array | R | 返回当前可用的场景列表 |
    | - scene_id | string | R | 场景ID |
    | - scene_name | string | R | 场景名称 |
    | - templeta | string | R | 场景定义的模板字段列表 |
    | - platform | string | R | 场景支持的[平台类型](wepush/_enums?id=platform) |