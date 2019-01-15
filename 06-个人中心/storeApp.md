#### 返回数据约定
##### 返回结果
```json
    {
        "code": "0000",
        "msg": "操作成功",
        "data": {}
    }
```
#### 编号：6-2-006
#### 页面：我
#### 说明：商家的基本信息

##### URL
 > /v1/me/store
##### 请求方式
 > GET

##### 请求参数
 字段          | 类型   | 必选 | 说明
 ---           | ---    | ---  | ---
Token          | string | Y    | 用户令牌

##### 返回字段
 字段                  | 类型      | 说明
---                    | ---       | ---
 nickName              | string    |昵称
 firstName             | string    |名
 lastName              | string    |姓
 sex                   | string    |性别
 balance               | decimal   |余额
zhangPeriodStatistics  | decimal   |未到账金额 统计
----
#### 编号：6-2-007
#### 页面：我的钱包
#### 说明：用户 分类资金统计

##### URL
> /v1/wallet/storeTransactionStatistics

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
Token         | string | Y    | 用户令牌
month         | int    | Y    | 月
##### 返回字段
字段                   |  类型     | 说明
---                    | ---       | ---
turnoverStatistics     | decimal   | 营业额统计
zhangPeriodStatistics  | decimal   | 到账金额统计
withdrawalStatistics   | decimal   | 提现金额统计
rechargeStatistics     | decimal   | 充值金额统计
refundStatistics       | decimal   | 退款金额统计

----
 
#### 编号：6-2-008
#### 页面：我的钱包
#### 说明：用户流水记录

##### URL
> /v1/wallet/storeTransaction

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
Token         | string | Y    | 用户令牌
pageNum       | int    | Y    | 页数
pageSize      | in     | Y    | 每页显示数
month         | int    | Y    | 月
walleType     | long   | N    | 流水类型：0 支付， 1提现 2充值 3退款  4到账

##### 返回字段
字段 |           |  类型    | 说明
---  | ---       | ---      | ---
list |           | array    |
|    | walleType | long     | 流水类型：0 支付， 1提现 2充值 3退款  4到账
|    | amount    | decimal  | 金额
|    | createdAt | datetime | 操作时间
----
#### 编号：6-2-009
#### 页面：绑定邮箱
#### 说明：绑定邮箱

##### URL
> /v1/sotre/email

##### 请求方式
> PUT

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
Token         | string | Y    | 用户令牌
email         | string | Y    | 邮箱
verifyCode    | string | Y    | 验证码

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：6-2-010
#### 页面：绑定手机
#### 说明：绑定手机

##### URL
> /v1/sotre/phone

##### 请求方式
> PUT

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
Token         | string | Y    | 用户令牌
phoneNumber   | string | Y    | 手机
verifyCode    | string | Y    | 验证码

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：6-2-011
#### 页面：变更昵称
#### 说明：变更昵称 
##### URL
> /v1/sotre/nickname

##### 请求方式
> PUT
##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
Token            | string | Y    | 用户令牌
nickName         | string | Y    | 昵称

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----