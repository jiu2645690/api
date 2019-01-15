#### 返回数据约定
##### 返回结果
```json
    {
        "code": "0000",
        "msg": "操作成功",
        "data": {}
    }
```



#### 编号：7-0-001
#### 页面：我
#### 说明：信息中心统计 

##### URL
> /v1/message/statistics

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


#### 编号：7-0-002
#### 页面：信息中心
#### 说明：统计反馈信息

##### URL
> /v1/messge/feedbackStatistics

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

#### 编号：7-0-003
#### 页面：信息中心
#### 说明：用户和商家对话列表

##### URL
> /v1/message/conversation

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌

##### 返回字段
字段 |                 |  类型    | 说明
---  | ---             | ---      | ---
list |                 | array    |  
|    | customid        | string   | 对话的列表中的商家id
|    | customNickName  | string   | 对话的列表中的商家信息
|    | messageId       | datetime | 对话的商家列表
 
----

#### 编号：7-0-004
#### 页面：反馈详情
#### 说明：反馈信息详情

##### URL
> /v1/message/feedback

##### 请求方式
> GET

##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
token            | string | Y    | 用户令牌

##### 返回字段
字段 |                 |  类型   | 说明
---  | ---             | ---     | ---
list |                 | array   |  
|    | feedbackContent | string  | 消息内容

----

#### 编号：7-0-005
#### 页面：用户和商家对话详情
#### 说明：用户和商家对话详情 （这里 点击进入后，messageId 下的 消息 变更为已读状态）

##### URL
> /v1/message/conversation/{messageId}

##### 请求方式
> GET

##### 请求参数
字段          | 类型   | 必选 | 说明
---           | ---    | ---  | ---
token         | string | Y    | 用户令牌
messageId     | long   | Y    | 聊天主体

##### 返回字段
字段 |                 |  类型    | 说明
---  | ---             | ---      | ---
list |                 | array    |  
|    | messageContent  | string   | 消息内容
|    | sendPeople      | string   | 发送人名称
|    | sendTime        | datetime | 发送时间
----

#### 编号：7-0-006
#### 页面：举报
#### 说明：提交举报信息

##### URL
> /v1/feedback

##### 请求方式
> POST

##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
token            | string | Y    | 用户令牌
feedbackContent  | string | Y    | 举报类容
pictureList      | array  | Y    | 举报图片

##### 返回字段
字段   | 类型    | 说明
---    | ---     | ---
status | boolean |
----

#### 编号：7-0-007
#### 页面： 订单详情
#### 说明： 联系商家或用户 建立对话
##### URL
> /v1/contact

##### 请求方式
> GET
##### 请求参数
字段            | 类型    | 必选 | 说明
---             | ---     | ---  | ---
token           | string  | Y    | 用户令牌
storeId         | long    | N    | 店铺id
customer        | long    | N    | 用户id
##### 返回字段
字段      |  类型  | 说明
---       | ---    | ---
messageId | long   | 消息编号
----