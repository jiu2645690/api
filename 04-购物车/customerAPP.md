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

#### 编号：4-1-001
#### 页面：店铺详情-特惠区
#### 说明：将套餐添加到购物车

##### URL
> /v1/store/combo

##### 请求方式
> POST

##### 请求参数
字段            | 类型     | 必选 | 说明
---             | ---      | ---  | ---
token           | string   | N    | 用户token
deliveryDate    | datetime | Y    | 送餐日期
deliveryTime    | int      | Y    | 0 午餐 1晚餐
storeId         | long     | Y    | 店铺id
comboTemplateId | long     | Y    | 套餐id
count           | int      | Y    | 套餐数量
foodItemIdList  | list     | Y    | 包含的菜品

##### 返回字段
字段                   | 类型 | 说明
---                    | ---  | ---
comboId                | long | 套餐编号
shoppingCartLineItemId | long | 购物行编号
-------

#### 编号：4-1-002
#### 页面：店铺详情-菜单
#### 说明：将菜品添加到购物车

##### URL
> /v1/store/dish

##### 请求方式
> POST

##### 请求参数
字段            | 类型     | 必选 | 说明
---             | ---      | ---  | ---
token           | string   | N    | 用户token
deliveryDate    | datetime | Y    | 送餐日期
deliveryTime    | int      | Y    | 0 午餐 1晚餐
storeId         | long     | Y    | 店铺id
foodItemId      | long     | Y    | 店铺id
count           | int      | Y    | 菜品数量

##### 返回字段
字段                   | 类型 | 说明
---                    | ---  | ---
shoppingCartLineItemId | long | 购物行编号
-------

#### 编号：4-1-003
#### 页面：购物车
#### 说明：变更数量

##### URL
> /v1/cart

##### 请求方式
> PUT

##### 请求参数
字段                       | 类型   | 必选 | 说明
---                        | ---    | ---  | ---
token                      | string | Y    | 用户令牌
shoppingCartLineItemId     | long   | Y    | 购物车行id
comboCount                 | int    | N    | 变更后的套餐数量(0 或者1)
foodItemCount              | int    | N    | 变更后的菜品数量

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----
#### 编号：4-1-004
#### 页面：我
#### 说明：购物车统计 顾客基本信息首页 （用于 “我” 这个页面 购物车数量的统计）

##### URL
> /v1/cart/statistics

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token        | string | Y    | 用户令牌

##### 返回字段
字段   |  类型   | 说明
---    | ---     | ---
amount | int     |数量  
----
#### 编号：4-1-005
#### 页面：购物车
#### 说明：获取购物车列表

##### URL
> /v1/cart

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌

##### 返回字段
字段 |                     |  类型    | 说明
---  | ---                 | ---      | ---
list |                     | array    |
|    | storeId             | long     | 
|    | deliveryDate        | datetime | 送餐日期
|    | deliveryTime        | int      | 送餐时段
|    | fooditemOrComboList | array    | 
##### 返回字段
字段 |                       |  类型    | 说明
---  | ---                   | ---      | ---
fooditemOrComboList    |                | array    |
|    |shoppingCartLineItemId | long     | 
|    | comboId               | long     | 套餐编号
|    | comboCount            | int      | 套餐数量
|    | comboName             | string   | 套餐名称
|    | comboPictureUrl       | string   | 套餐封面图片
|    | foodItemId            | long     | 菜品编号
|    | foodItemCount         | int      | 菜品数量
|    | foodItemName          | long     | 菜品名称
|    | foodItemprice         | decimal  | 菜品价格
|    | foodItemPictureUrl    | int      | 菜品封面图片

----

#### 编号：4-1-006
#### 页面：购物车
#### 说明：删除购物车 中的商品

##### URL
> /v1/cart

##### 请求方式
> DELETE

##### 请求参数
字段                       | 类型   | 必选 | 说明
---                        | ---    | ---  | ---
token                      | string | Y    | 用户令牌
shoppingCartLineItemIdList | string | Y    | 购物车行id

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----


