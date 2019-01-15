#### 返回数据约定
##### 返回结果
```json
    {
        "code": "0000",
        "msg": "操作成功",
        "data": {}
    }
```
#### 编号：8-1-001
#### 页面：我
#### 说明：收藏夹统计 顾客基本信息首页  （用于 “我” 这个页面 收藏夹总数统计）

##### URL
> /v1/favorite/statistics

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌

##### 返回字段
字段   |  类型   | 说明
---    | ---     | ---
amount | int     |数量  
----
#### 编号：8-1-002
#### 页面：收藏
#### 说明：添加 菜品/店铺/套餐 到收藏夹

##### URL
> /v1/favorite  


##### 请求方式
> POST

##### 请求参数
字段            | 类型    | 必选 | 说明
---             | ---     | ---  | ---
token           | string  | Y    | 用户令牌
foodItemId      | long    | N    | 菜品编号
storeId         | long    | N    | 店铺编号
comboTemplateId | long    | N    | 套餐编号



##### 返回字段
字段   |  类型    | 说明
---    |  ---      | ---
status |  boolean

#### 编号：8-1-003
#### 页面：收藏
#### 说明：获取收藏店铺列表

##### URL
> /v1/favorite/stores

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---| ---    | ---  | ---
token         | string | Y    | 用户令牌
pageNum       | int    | Y    | 页数
pageSize      | in     | Y    | 每页显示数


##### 返回字段
字段 |              |  类型    | 说明
---  | ---          | ---      | ---
list |              | array    |
|    | foodItemId   | long     | 
|    | name | string   |
|    | pirtureUrl   | string   | 封面图片 
----

#### 编号：8-1-004
#### 页面：收藏
#### 说明：获取收藏菜品列表

##### URL
> /v1/favorite/foodItems

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
pageNum       | int    | Y    | 页数
pageSize      | in     | Y    | 每页显示数

##### 返回字段
字段 |            |  类型    | 说明
---  | ---        | ---      | ---
list |            | array    |
|    | storeId    | long     | 
|    | storeName  | string   |
|    | pirtureUrl | string   | 封面图片 
----

#### 编号：8-1-005
#### 页面：收藏
#### 说明：获取收藏套餐列表

##### URL
> /v1/favorite/combos

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
pageNum       | int    | Y    | 页数
pageSize      | in     | Y    | 每页显示数

##### 返回字段
字段 |                    |  类型    | 说明
---  | ---                | ---      | ---
list |                    | array    |
|    | comboTemplateId    | long     | 
|    | comboTemplateName  | string   |
|    | pirtureUrl         | string   | 封面图片 
----

#### 编号：8-1-006
#### 页面：收藏
#### 说明：取消 菜品/店铺/套餐 的收藏

##### URL
> /v1/favorite


##### 请求方式
> PUT

##### 请求参数
字段            | 类型    | 必选 | 说明
---             | ---     | ---  | ---
token           | string  | Y    | 用户令牌
foodItemId      | long    | N    | 菜品编号
storeId         | long    | N    | 店铺编号
comboTemplateId | long    | N    | 套餐编号

##### 返回字段
字段   |  类型    | 说明
---    |  ---      | ---
status |  boolean
-----------