#### 返回数据约定
##### 返回结果
```json
    {
        "code": "0000",
        "msg": "操作成功",
        "data": {}
    }
```



#### 编号：9-0-001
#### 页面： 评价页面
#### 说明：上传图片
##### URL
> /v1/review/upload

##### 请求方式
> POST

##### 请求参数
字段            | 类型   | 必选 | 说明
---             | ---    | ---  | ---
token           | string | Y    | 用户令牌
picture         | byte   | Y    | 图片 

##### 返回字段
字段      |  类型  | 说明
---       | ---    | ---
pictureId | long     | 订单编号
----