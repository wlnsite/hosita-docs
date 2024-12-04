# 就诊档案（卡）信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| name | string | Y | 无 | 姓名，院内手动登记的婴儿可以为空 |
| idcard | string | N | 无 | 证件号码 |
| sex | int | Y | 0 | [性别](enums?id=sex)：0-未知,1-男,2-女 |
| age | double | Y | 0 | 年龄 |
| tel | string | N | 无 | 手机号码 |
| address | string | N | 无 | 联系地址 |
| birthday | string | N | 无 | 出生日期 |
| patient_id | string | N | 无 | 就诊档案（卡）唯一标识 |
| patient_mzh | string | N | 无 | 门诊号 |
| patient_zyh | string | N | 无 | 住院号 |
| health_cardno | string | N | 无 | 电子健康卡号 |
