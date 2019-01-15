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
#### 编号：5-2-011
#### 页面：商家订单 列表页面
#### 说明：获取商家所有订单 分页排序
##### URL
> /v1/order/store

##### 请求方式
> GET
##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
pageNum         | int    | Y    | 页数
pageSize        | int    | Y    | 每页显示数
addressId       | long   | N    | 送餐地址id（如果没有表示获取全部）
orderState      | int    | Y    | 订单状态（0 全部，1进行中 2待评价（已送达） 3已完成 4退款处理中和已退款）

##### 返回字段
字段 |                    |  类型    | 说明
---  | ---                | ---      | ---
list |                    | array    |
|    | deliveryDate       | datetime | 订单编号
|    | deliveryTime       | int      | 简单描述
|    | totalAmount        | decimal  | 总金额
|    | remark             | string   | 备注
|    | uuId               | string   | 订单编号
----

#### 编号：5-2-012
#### 页面：商家订单 
#### 说明：根据所选地址订单一建送达
##### URL
> /v1/order/delivery

##### 请求方式
> PUT
##### 请求参数
|     |    字段            | 类型     | 必选 | 说明
| --- |    ---             | ---      | ---  | ---
|     |    token           | string   | Y    | 用户令牌
 list |                    | array    |
|     | addressId          | long     | 地址编号
state |                    | int      | Y    |状态

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：5-2-013
#### 页面：商家订单 详情 
#### 说明： 变更单个订单的送达状态/同意退款
##### URL
> /v1/order/state

##### 请求方式
> PUT
##### 请求参数
字段          | 类型     | 必选 | 说明
 ---          | ---      | ---  | ---
token         | string   | Y    | 用户令牌
orderId       | long     | Y    |地址编号
state         | int      | Y    |状态
##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----
#### 编号：5-2-014
#### 页面：订单列表
#### 说明：商家删除订单
##### URL
> /v1/order/store

##### 请求方式
> DELETE
##### 请求参数
字段          | 类型     | 必选 | 说明
 ---          | ---      | ---  | ---
token         | string   | Y    | 用户令牌
orderId       | long     | Y    |地址编号

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：5-2-015
#### 页面：商家 备菜日历/即时订单统计
#### 说明：商家 点击日历中某一天 查看今天需要备的菜

##### URL
> /v1/order/fooditemStatistics

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
Date          | string | Y    | 当前选中的日期

##### 返回字段
字段  |                   | 类型    | 说明
---   | ---               | ---     | ---
 list |                   | array   | 
|     | foodItemId        | string  | 菜品id
|     | name              | string  | 菜品名称
---------
#### 编号：5-2-016
#### 页面：即时订单统计
#### 说明：商家  查看今天 菜品统计。

##### URL
> /v1/order/fooditemStatistics

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌

##### 返回字段
字段  |                   | 类型    | 说明
---   | ---               | ---     | ---
 list |                   | array   | 
|     | foodItemId        | string  | 菜品id
|     | name              | string  | 菜品名称
---------
