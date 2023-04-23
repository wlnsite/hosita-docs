# API开放平台统一说明
## 1. HTTP协议

- #### 1.1 请求方法
所有接口均支持POST请求，部分接口只支持POST请求。

- #### 1.2 字符编码
HTTP通讯及报文`HEX`、`BASE64`编码均采用`UTF-8`字符集编码格式。

## 2. 编码格式及字段要求 :id=format
- #### 2.1 内容编码 
    内容均采用`JSON`格式，部分平台接口有加密要求，具体加密方式查看对应产品平台。

- #### 2.2 日期及时间格式
    | 类型 | 格式 | 说明 |
    | ---- | ---- | ---- |
    | 日期 |`yyyy-MM-dd`| 如：`2002-01-01` |
    | 时间 | `HH:mm:ss` | 如：`21:07:00`|

- #### 2.3 字段出现要求说明 :id=requirements
    | 符号 | 说明 |
    | ---- | ---- |
    |  R   | 报文中该字段必须出现（Required） |
    |  O   | 报文中该字段可选出现（Optional） |
    |  C   | 报文中该字段在一定条件下出现（Conditional） |

## 3. 公共参数 :id=base_params
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | access_token | string | O | 认证参数 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：1-成功，无值表示请求失败，其它均为异常值 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | array/object/string | R | 输出数据结果 |

## 4. 关于状态码 :id=status_code
- #### 4.1 统一规范
    | 状态码 | 状态 | 说明 |
    | ---- | ---- | ---- |
    | -1  | 未知异常 unkown error | 未确认具体的错误内容 |
    |  0  | 调用成功 result success | 代表调用成功，流程正常 |
    |  1  | 调用成功 result success | 代表调用成功，但流程可能不正常 |
    | 1xx | 参数错误 parameter error | 检查接口调用参数是否正确 |
    | 2xx | 部分完成 partially completed | 进行了部分处理并保存，但未获取到最终输出 |
    | 3xx | 服务状态 service state | 下线、停机维护等 |
    | 4xx | 内部错误 internal error | 网络错误，返序列化失败等 |
    | 5xx | 业务错误 business error | 业务错误，无权限、数据不存在等 |

- #### 4.2 常见错误码
    | 态码 | 状态 | 说明 |
    | ---- | ---- | ---- |
    | 100 | 参数错误 parameter error | 参数丢失、格式错误、不符合传参要求等 |
    | 101 | 参数错误 parameter error | 参数丢失、格式错误、不符合传参要求等 |
    | 102 | 解密失败 decryption failed | 确认token通讯密钥是否正确 |
    | 103 | 签名错误 signature failed | 确认签名算法及密钥是否正确 |
    | 104 | 请求超时 request timeout | 确认timestamp参数是否在有效期内 |
    | 301 | 服务停用 service transfer | 系统部署地址已转移 |
    | 302 | 服务停用 service maintain | 系统正在维护中 |
    | 304 | 服务停用 service stop | 不再提供响应服务 |
    | 400 | 通讯异常 internal error | 本地参数缺少或配置有误 |
    | 401 | 通讯异常 internal error | 服务器无返回或状态异常 |
    | 402 | 通讯异常 internal error | 已获取到输出，但反序列化失败 |
    | 403 | 通讯异常 internal error | 禁止访问，如无权限等 |
    | 500 | 业务错误 business error | 业务错误，无具体原因内部异常 |
