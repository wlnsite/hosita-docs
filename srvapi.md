
# API接入说明
接口统一使用`POST`进行调用，编码方式为`UTF-8`，

#### 第一步：获取接口调用信息
接口调用需要如下信息：
- 1.服务器地址：从平台获取，如：http://192.168.1.127:6789
- 2.通讯密钥TOKEN：16位字符串，用于后续消息加密
- 3.SM2私钥及公钥：可自行生成，也可由平台生成，自行生成后需项平台提供`HEX`格式的公钥信息
- 4.证书序列号SN：提供公钥后由平台生成
 
#### 第二步：组装请求参数 
- **timestamp**：当前时间的UNIX时间戳，精确到秒。
- **data**：将请求参数通过JSON序列化后，使用`SM4/ECB/Padding7`加密后`HEX`编码所得，密钥为第一步中的通讯密钥TOKEN。
- **sign**：使用SM2私钥签名`data` + `Token` + `timestamp`所得，服务端使用公钥验签。

`提示：`SM4加密解密可使用 https://lzltool.cn/SM4 工具进行测试，SM2加签验签可使用 https://bkssl.com/ssl/sm2 工具处理。
#### 第三步：接口调用

- **接口地址：** 服务器地址+接口地址
- **请求方式：** GET/POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述                                   |
    | -------- | -------- | -------- | ------------------------------------ |
    | sn       | string   | R        | 第一步中的证书序列号SN                |
    | data     | string   | R        | SM4加密后的请求参数（HEX格式）        |
    | sign     | string   | R        | SM2签名字符串（HEX格式）                         |
    | timestamp  | long   | R        | 请求发起时间，UNIX时间戳，精确到秒     |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述                                  |
    | -------- | -------- | -------- | ------------------------------------- |
    | node     | string   | R        | 异常产生节点        |
    | code     | string   | R        | 执行状态：1-成功，其它表示异常        |
    | success  | bool     | R        | 执行状态：业务是否成功                |
    | message  | string   | R        | 消息：错误消息或成功提示              |
    | data     | string   | C        | 输出内容，使用SM4加密（HEX格式）      |

- **请求示例：**
```
{
    "sn": "3f6936d7bd947051f063403d9979c279",
    "data": "6dbf119546970f4dac9c878e2827e72242d816df0a76e928ed2cc8d917214f48cbf0e4338f812295f3ebd1aba64411308de78f14b6a737b26e31965825d7172d",
    "sign": "3045022052de89b3a6d73ce935ccbb829a9fdb1d1b7ce1054e607bb425deb0cd8e2298e2022100cb0c3c7707dbf827c79e58826f2b58f962fc333ee39d75066b5658c1661dd261",
    "timestamp": "1693538970"
}
```
- **返回示例：**
```
{
    "node": "hosita",
    "code": "1",
    "data": "d848bd2fc7cdb9786050b74ed108a7e9f34704bdaf63fa0b3c9ebb6a52f81628611dd0abdb124e63562d220d4656c4722ac0bf57aa695bbac2517a099acb3beb8121e8226f8841711367ee82c6f0c6f659a5dc758e1fac682d28e94221f3799a78712ddb4119b8234e13c8152435936c7a7b1c99f17532c4c680cc051267ff7bd625659c7a0bf548612682d7a49cb5f12d8a2bcc9bf7c0b72e0216e919105fe0fd1594a0198a287c21f30c08bfc1d87ac93c51603675d79eece9e8002ace165b4ebf10a0541b6f4d14e14b492af4d86df1ba2b269fc46f03f3c63a1080aca0efdf47ec78aa9ecdf3118fd075ec074ce2a7250c2538aec404d15ab4efbb93393a17528c18d9c8fdc44bb91f270f053eadf04f58fda32990a84078bb2cbcf96c216084f963d45a224701f1671aa886ea8c5748455d5255dcb35576e1a03b6abc461b157dfcca43ebba7b692ab404b4c16e193462955542d1e76f9e87b98e753a54f77013c856b6890a26a8e30769f9a543de9737b3aeec75f9666c1eac608e1b3d",
    "success": true,
    "message": "查询成功，结果已返回"
}
```

