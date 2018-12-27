#### 返回数据约定
##### 返回结果
```json
    {
        "code": "0000",
        "msg": "操作成功",
        "data": {}
    }
```
##### 返回参数
字段 |  类型  | 说明
---  | ---    | ---
code | string | 状态码
msg  | string | 状态信息
data | object | 结果集
-----------

#### 编号：2-1-027
#### 页面：用户重设密码
#### 说明：修改密码(未登录状态)

##### URL
> /v1/password/customerReset

##### 请求方式
> PUT

##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
password         | string | Y    | 密码
verifyPassword   | string | Y    | 确认密码
resetPasswordKey | string | Y    | 密码修改密匙

##### 返回字段
> 无
--------

#### 编号：2-1-028
#### 页面：用户重设密码
#### 说明：修改密码（登陆状态）

##### URL
> /v1/password/loginCustomerReset

##### 请求方式
> PUT

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
token          | string | Y    | 用户令牌
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
token             | string | 用户token （因为密码已经修改 需要新的token）
--------

#### 编号：2-2-029
#### 页面：商家重设密码
#### 说明：修改密码(未登录状态)

##### URL
> /v1/password/storeReset

##### 请求方式
> PUT

##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
password         | string | Y    | 密码
verifyPassword   | string | Y    | 确认密码
resetPasswordKey | string | Y    | 密码修改密匙

##### 返回字段
> 无
--------



#### 编号：2-2-030
#### 页面：商家重设密码
#### 说明：修改密码（登陆状态）

##### URL
> /v1/password/loginStoreReset

##### 请求方式
> PUT

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
token          | string | Y    | 用户令牌
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
token             | string | 用户token （因为密码已经修改 需要新的token）
--------
