# 三方应用网页授权接口

- **接口说明：** 三方应用使用此接口可发起网页授权并返回对应的ticket
- **接口地址：** /oauth?certsn=${certsn}&callback=${callback}
- **请求方式：** GET
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | certsn | string | R | 三方应用的证书序列号 |
    | callback | string | R | 授权成功后返回的页面，需要UrlEncode后提交 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | ticket | string | R | 当前用户身份信息换取凭据 |
    | time | string | R | 用户授权的时间戳 |
    | sign | string | R | 参数签名，通过SM2签名(ticket + 通讯密钥 + time)得出，请使用请求参数中certsn对应的服务端公钥进行验签 |

