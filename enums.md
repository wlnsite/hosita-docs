# 枚举类型定义

#### 性别 :id=sex

| 枚举值 | 说明 | 枚举值 | 说明 | 枚举值 | 说明 |
| ------ | ---- | ------ | ---- | ------ | ---- |
|   0    | 未知 |   1    | 男   |   2    | 女   |

#### 通用状态 :id=state

| 枚举值 | 说明 | 枚举值 | 说明 | 枚举值 | 说明 |
| ------ | ---- | ------ | ---- | ------ | ---- |
|   0    | 无效 |   1    | 有效 |   -1   | 丢失 |

#### 是否标识 :id=yesno

| 枚举值 | 说明 | 枚举值 | 说明 |
| ------ | ---- | ------ | ---- |
|   0    |  否  |   1    |  是  |

#### 有效性标识 :id=valid

| 枚举值 | 说明 | 枚举值 | 说明 |
| ------ | ---- | ------ | ---- |
|   0    | 无效 |   1    | 有效 |


#### 平台标志 :id=platform

| 枚举值 |     说明     | 枚举值 |     说明     |
| ------ | ------------ | ------ | ------------ |
| weixin | 微信         | alipay | 支付宝       |
| client | 自助终端     | siapp  | 医保APP      |
| other  | 其他         |        |              |

#### 业务类型 :id=business

|  枚举值   |     说明     | 枚举值 |     说明     |
| -------- | ------------ | ------ | ------------ |
| register | 挂号         | charge | 门诊缴费       |
| prepay | 住院费预缴     | parking | 停车缴费      |
| online  | 线上服务       | other | 其它业务      |

#### 支付方式 :id=payment

| 枚举值 |     说明     | 枚举值 |     说明     |
| ------ | ------------ | ------ | ------------ |
|   01   | 现金         |   02   | 银行卡       |
|   06   | 医保账户     |   07   | 医保统筹     |
|   08   | 就诊卡       |   10   | 数字人民币   |
|   11   | 微信         |   12   | 支付宝       |
|   13   | 云闪付       |   14   | 信用就医     |
|   41   | 医保+微信    |   42   | 医保+支付宝  |
|   00   | 其它    |        |    |

#### 挂号级别 :id=reg_level
| 枚举值 | 说明          | 枚举值 | 说明          |
| ------ | ------------- | ------ | ------------- |
|   01   | 普通挂号      |   02   | 副主任医师号  |
|   03   | 主任医师号    |   10   | 急诊号        |

#### 费用类别 :id=fee_category
| 枚举值 | 说明 |
| ------ | ---- |
|   00   | 未定义 |

#### 医保标准医疗类别 :id=med_type
| 枚举值 |     说明     | 枚举值 |     说明     |
| ------ | ------------ | ------ | ------------ |
|   11   |   普通门诊   |   41   | 定点药店购药 |
|   12   |   门诊挂号   |   51   | 生育门诊     |
|   13   |     急诊     |   52   | 生育住院     |
|   14   |  门诊慢特病  |   53   | 计划生育手术费 |
|   21   |   普通住院   |   91   | 其他门诊     |
|   22   |   外伤住院   |   92   | 其他住院     |
|   23   | 转外诊治住院 |   93   | 其他购药     |
|   24   |  急诊转住院  |   99   | 地方扩展医疗类别  |

#### 医保标准险种类型 :id=insutype
| 枚举值 |       说明       | 枚举值 |       说明       |
| ------ | ---------------- | ------ | ---------------- |
|  310   | 职工基本医疗保险 |  390   | 城乡居民基本医疗保险 |
|  320   |  公务员医疗补助  |  392   | 城乡居民大病医疗保险 |
|  330   | 大额医疗费用补助 |  510   | 生育保险 |
|  340   | 离休人员医疗保障 |     |  |


#### 处方明细频次 :id=recipe_frequency
| 枚举值 | 说明 |
| ------ | ---- |
|   00   | 未定义 |

#### 处方用量单位 :id=recipe_dosage_unit
| 枚举值 | 说明 |
| ------ | ---- |
|   00   | 未定义 |

#### 处方用量剂型 :id=recipe_dosage_form
| 枚举值 | 说明 |
| ------ | ---- |
|   00   | 未定义 |
