# 医生信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| id | string | Y | 无 | 唯一标识 |
| name | string | Y | 无 | 医生姓名 |
| state | int | Y | 无 | [记录状态](enums?id=state) |
| dept_id | string | Y | 无 | 所属科室Id |
| dept_name | string | Y | 无 | 所属科室名称 |
| doctor_code | string | N | 无 | 医师注册编码 |
| doctor_name | string | N | 无 | 医师注册姓名 |
| mobile | string | N | 无 | 手机号码 |
| position | string | O | 无 | 医生职务 |
| avatar | string | O | 无 | 头像照片 |
| intro | string | O | 无 | 简单介绍 |
