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
#### 编号：3-0-001
#### 页面：店铺列表
#### 说明：店铺列表

##### URL
> /v1/store

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | N    | token(这里的token 不是 强制传入)
pageNum       | int    | N    | 页码，默认1
pageSize      | int    | N    | 每页记录数，默认10
addressId     | long   | Y    | 送餐地址id
star          | int    | N    | 星级
averageScore  | double | N    | 综合评分
searchContent | double | N    | 查询内容
deliveryTime  | int    | N    | 送餐时段：0：午餐 1：晚餐 2：全选 -1：都不选

##### 返回字段
字段 |              |  类型   | 说明
---  | ---          | ---     | ---
list |              | array   |  
|    | storeId      | long    | 店铺id
|    | storeName    | long    | 店铺名
|    | isFavorite   | boolean | 是否收藏
|    | avgScore     | double  | 评分
|    | reviewCount  | long    | 评价数量
|    | mealTimeList | List    | 送餐时间段
|    | pictureUrl   | string  | 封面图片地址
|    | star         | int     | 星级
-------
#### 编号：3-0-002
#### 页面：店铺列表
#### 说明：获取店铺更多展示图片

##### URL
> /v1/store/pictures

##### 请求方式
> GET

##### 请求参数
字段    | 类型 | 必选 | 说明
---     | ---  | ---  | ---
storeId | Long | Y    | 店铺id


##### 返回字段
字段 |            |  类型  | 说明
---  | ---        | ---    | ---
list |            | array  |
|    | pictureUrl | string | 封面图片地址
-------

#### 编号：3-0-003
#### 页面：店铺详情
#### 说明：店铺信息

##### URL
> /v1/store/{storeId}

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
storeId       | long   | Y    | 店铺id
token         | string | N    | 用户token

##### 返回字段
字段         | 类型    | 说明
---          | ---     | ---
storeId      | long    | 店铺id
storeName    | long    | 店铺名
isFavorite   | boolean | 是否收藏
avgScore     | double  | 评分
reviewCount  | long    | 评价数量
mealTimeList | List    | 送餐时间段
pictureUrl   | string  | 封面图片地址
introduction | string  | 店铺简介
--------

#### 编号：3-0-004
#### 页面：店铺详情
#### 说明：特惠区

##### URL
> /v1/store/discounts

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必须      | 说明
---           | ---    | ---       | ---
storeId       | long   | Y         | 店铺id
pageNum       | int    | N         | 页码，默认1
pageSize      | int    | N         | 每页记录数，默认10

##### 返回字段
字段           | | 类型 | 说明
---            | ---            | ---     | ---
 dishComboList |                | array   |  套餐列表
|              | comboId        | long    | 套餐Id
|              | name           | string  | 套餐名称
|              | price          | decimal | 价格
|              | remainingCount | int     | 库存
||comboTemplateDiscount| int     | 折扣比例
|              | pictureUrl     | string  | 封面图片路径
|              | isFavorite     | boolean | 是否收藏
-------

#### 编号：3-0-005
#### 页面：店铺详情
#### 说明：获取店铺今天和以后2两周内设置的营运日期，通过匹配今天是否营业，判断是否有菜品

##### URL
> /v1/store/menu

##### 请求方式
> GET

##### 请求参数
字段    | 类型   | 必选 | 说明
---     | ---    | ---  | ---
storeId | long   | Y    | 店铺id
Date    | string | N    | 当前日期

##### 返回字段
字段  |                           | 类型     | 说明
---   | ---                       | ---      | ---
 list |                           | array    | 菜品列表
|     | currentFoodItemTemplateId | long     | 菜品模板id
|     | date                      | datatime | 营运日期
--------


#### 编号：3-0-006
#### 页面：店铺详情
#### 说明：店铺评价列表

##### URL
> /v1/store/review

##### 请求方式
> GET

##### 请求参数
字段     | 类型 | 必选 | 说明
---      | ---  | ---  | ---
storeId  | long | Y    | 店铺id
type     | int  | N    | 评价类型：1:全部 2:好评  3:中评 4:差评。默认1
pageNum  | int  | N    | 页码，默认1
pageSize | int  | N    | 每页记录数，默认10

##### 返回字段
字段  |                   | 类型   | 说明
---   | ---               | ---    | ---
 list |                   | array  | 评价列表
|     | customerAvatarUrl | string | 用户头像地址
|     | customerNickName  | string |用户名
|     | reviewTime        | string | 评价时间
|     | scoreContent      | string | 评价内容
|     | pictureList       | array  | 评价图片列表
------

#### 编号：3-0-007
#### 页面：店铺详情
#### 说明：获取根据currentFoodItemTemplateId 获取当前日期运营的菜品

##### URL
> /v1/store/menu

##### 请求方式
> GET

##### 请求参数
字段                       | 类型   | 必选 | 说明
---                        | ---    | ---  | ---
token                      | string | N     | 用户token
currentFoodItemTemplateId  | long   | Y    | 菜品模板id
pageNum                    | int    | N    | 页码，默认1
pageSize                   | int    | N    | 每页记录数，默认10

##### 返回字段
字段  |                   | 类型    | 说明
---   | ---               | ---     | ---
 list |                   | array   | 评价列表
|     | foodItemId        | string  | 菜品id
|     | name              | string  | 菜品名称
|     | price             | decimal | 价格
|     | remainingCount    | int     | 库存
|     | pictureUrl        | string  | 封面图片路径
|     | dailySpecialPrice | boolean | 特惠价格
|     | isFavorite        | boolean | 是否收藏
-------
#### 编号：3-0-008
#### 页面：菜品详情
#### 说明：获取菜品详情

##### URL
> /v1/dish/{foodItemId}

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
foodItemId    | long   | Y    | 菜品编号

##### 返回字段
字段                    |  类型      | 说明
---                     | ---        | ---
name                    | string     |菜品名称  
price                   | decimal    |价格
primaryIngredient       | string     |商品主材
complementaryIngredient | string     |商品辅材 
description             | string     |描述  
pictureUrl              | string     |封面图片  
----
#### 编号：3-0-009
#### 页面：菜品详情
#### 说明：获取更多菜品图片

##### URL
> /v1/dish/pictures/{foodItemId}

##### 请求方式
> GET

##### 请求参数
字段       | 类型 | 必选 | 说明
---        | ---  | ---  | ---
foodItemId | Long | Y    | 店铺id


##### 返回字段
字段 |            |  类型  | 说明
---  | ---        | ---    | ---
list |            | array  |
|    | pictureUrl | string | 封面图片地址
----


