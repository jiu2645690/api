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
#### 编号：5-1-001
#### 页面：订单预览
#### 说明：请求-生成预订单，单个下单也放list里

##### URL
> /v1/order/customer

##### 请求方式
> POST

##### 请求参数
字段                    |    |  类型   | 必选 | 说明
---                     |  ---  | ---     | ---  | ---
shoppingCartLineItemIdList |   | list | Y  | 购物车行集合
| |  shoppingCartLineItemId |  long | Y | 购物车行id |  

##### 返回字段
字段 |            |  类型  | 说明
---  | ---        | ---    | ---
list |            | array  |
|    | orderId    | long   | 订单编号
----
#### 编号：5-1-004
#### 页面：订单预览
#### 说明：变更数量
##### URL
> /v1/order   （这里 套餐 数量只能为1，一个用户一餐中 一种套餐 只能 点一份 ）

##### 请求方式
> PUT

##### 请求参数
字段       | 类型   | 必选 | 说明
---        | ---    | ---  | ---
orderId    | long   | Y    | 订单编号
foodItemId | long   | N    | 菜品编号
comboId    | long   | N    | 套餐编号
count      | int    | int  | 变更后数量

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----
#### 编号：5-1-005
#### 页面：订单详情中
#### 说明：补全订单信息  验证下单 

##### URL
> /v1/order/verify

##### 请求方式
> GET

##### 请求参数
字段 |                    |  类型    | 必选 | 说明
---  | ---                | ---      | ---  | ---
token|                    | string   | Y    |用户token
list |                    | array    |      |
|    | orderId            | long     | Y    | 订单编号
|    | deliveryDate       | datetime | Y    | 送餐日期
|    | deliveryTime       | int      | Y    | 送餐名称
|    | taxes              | decimal  | Y    | 税收
|    | tip                | decimal  | Y    | 消费
|    | remark             | string   | Y    | 备注（没有就填入''）

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |（成功则 弹出支付方式选择）
----

#### 编号：5-1-006
#### 页面：订单 列表页面
#### 说明： 获取所有订单 分页排序
##### URL
> /v1/order

##### 请求方式
> GET
##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
pageNum         | int    | Y    | 页数
pageSize        | in     | Y    | 每页显示数
orderState      | in     | Y    | 订单状态（0 全部，1进行中 2待评价 3已完成 4退款处理中和已退款）

##### 返回字段
字段 |                    |  类型   | 说明
---  | ---                | ---     | ---
list |                    | array   |
|    | storeName          | long    | 订单编号
|    | shortContent       | string  | 简单描述
|    | totalAmount        | decimal | 总金额
----

#### 编号：5-1-007
#### 页面：评价页面
#### 说明：对商家进行评价

##### URL
> /v1/review

##### 请求方式
> POST

##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
orderId         | double | Y    | 订单编号
tasteScore      | double | Y    | 味道评分
serviceScore    | double | Y    | 服务评分
weightScore     | double | Y    | 分量评分
scoreContent    | string | Y    | 评分内容

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----
#### 编号：5-1-008
#### 页面：订单详情
#### 说明：无条件退款

##### URL
> /v1/refund

##### 请求方式
> PUT

##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
orderId         |        | Y    | 订单编号

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：5-1-009
#### 页面：订单详情
#### 说明：申请退款（即不在退款时间内）
##### URL
> /v1/applyfor/refund

##### 请求方式
> PUT

##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
orderId         |        | Y    | 订单编号

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：5-1-010
#### 页面：订单详情
#### 说明：再来一单

##### URL
> /v1/order/onemore

##### 请求方式
> POST
##### 请求参数

字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
orderId         | long   | Y    | 订单编号

##### 返回字段
字段    | 类型    | 说明
---     | ---     | ---
orderId | long    |
----