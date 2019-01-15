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

#### 编号：5-0-002
#### 页面：订单预览/订单详情
#### 说明：详情 -获取 基本信息  （如果 是已完成订单，点击后变更 读取状态）

##### URL
> /v1/order/info/{orderId}

##### 请求方式
> GET

##### 请求参数
字段    | 类型  | 必选 | 说明
---     | ---   | ---  | ---
orderId | long  | Y    | 订单编号

##### 返回字段
字段         | 类型      | 说明
---          | ---       | ---
addressName  | string    | 地址
deliveryDate | long      | 送餐日期
deliveryTime | datetime  | 送餐时段
sotreName    | string    | 店铺名称
totalAmount  | string    | 总金额
taxes        | string    | 税收
tip          | string    | 消费
remark       | string    | 备注
refundReason | string    | 退款原因
----
#### 编号：5-0-003
#### 页面：订单预览/订单详情
#### 说明：详情 -获取 菜品列表 套餐列表

##### URL
> /v1/order/meals/{orderId}

##### 请求方式
> GET

##### 请求参数
字段    | 类型  | 必选 | 说明
---     | ---   | ---  | ---
orderId | long  | Y    | 订单编号
token   | string| Y    |用户token

##### 返回字段
字段 |                    |  类型  | 说明
---  | ---                | ---    | ---
list |                    | array  |
|    | comboId            | long   | 套餐编号
|    | comboCount         | int    | 套餐数量
|    | comboName          | string | 套餐名称
|    | comboPictureUrl    | string | 套餐封面图片
|    | foodItemId         | long   | 菜品编号
|    | foodItemCount      | int    | 菜品数量
|    | foodItemName       | long   | 菜品名称
|    | foodItemprice      | decimal| 菜品价格
|    | foodItemPictureUrl | int    | 菜品封面图片
----
