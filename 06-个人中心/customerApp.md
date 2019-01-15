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
#### 编号：6-1-001
#### 页面：我
#### 说明：获取我的基本信息

##### URL
> /v1/me/cusomer

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌

##### 返回字段
字段      | 类型      | 说明
---       | ---       | ---
nickName  | string    |昵称
firstName | string    |名
lastName  | string    |姓
sex       | string    |性别
balance   | decimal   |余额
----
#### 编号：6-1-002
#### 页面：我的钱包
#### 说明：用户流水记录

##### URL
> /v1/wallet/customerTransaction

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
pageNum       | int    | Y    | 页数
pageSize      | in     | Y    | 每页显示数

##### 返回字段
字段 |           |  类型    | 说明
---  | ---       | ---      | ---
list |           | array    |
|    | walleType | long     | 流水类型：0 支付， 1提现 2充值 3退款
|    | amount    | decimal  | 金额
|    | createdAt | datetime | 操作时间'
----
#### 编号：6-1-003
#### 页面：绑定邮箱
#### 说明：绑定邮箱

##### URL
> /v1/customer/email

##### 请求方式
> PUT

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
email         | string | Y    | 邮箱
verifyCode    | string | Y    | 验证码

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：6-1-004
#### 页面：绑定手机
#### 说明：绑定手机

##### URL
> /v1/customer/phone

##### 请求方式
> PUT

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
phoneNumber   | string | Y    | 手机
verifyCode    | string | Y    | 验证码

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：6-1-005
#### 页面：变更昵称
#### 说明：变更昵称
##### URL
> /v1/customer/nickname

##### 请求方式
> PUT
##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
token            | string | Y    | 用户令牌
nickName         | string | Y    | 昵称

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----