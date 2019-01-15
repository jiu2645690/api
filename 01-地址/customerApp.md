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

#### 编号：1-0-001
#### 页面：引导页
#### 说明：获取(系统设置的)送餐地址

##### URL
> /v1/address/{addressId}

##### 请求方式
> GET
##### 请求参数
> 无

##### 返回字段
字段        | 类型   | 说明
---         | ---    | ---
addressId   | long   | 主键id
addressName | string | 地址
zipCode     | string | 邮编
-----------

#### 编号：1-0-002
#### 页面：引导页
#### 说明：获取送餐地址列表

##### URL
> /v1/address

##### 请求方式
> GET
##### 请求参数
> 无

##### 返回字段
字段 |             | 类型 | 说明 |
---  | ---         | ---  | ---
list |             | 列表 | ---
|    | addressId   | long   | 主键id
|    | addressName | string | 地址
|    | zipCode     | string | 邮编
-----------

#### 编号：1-1-002
#### 页面：引导页
#### 说明：用户绑定地址/或者用户切换地址

##### URL
> /v1/address/customerBind

##### 请求方式
> PUT

##### 请求参数
 字段          | 类型   | 必选 | 说明
 ---           | ---    | ---  | ---
 token         | string | Y    | 用户token
 addressId     | string | Y    | 地址主键id

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |


-----------






