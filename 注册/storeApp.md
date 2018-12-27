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

#### 编号：2-1-013
#### 页面：手机注册 
#### 说明：发送手机验证码

##### URL
> /v1/phone/send/storeRegisterCode

##### 请求方式
> GET

##### 请求参数
字段        | 类型   | 必选 | 说明
---         | ---    | ---  | ---
phoneNumber | string | Y    | 手机号

##### 返回字段
无
-------

#### 编号：2-1-014
#### 页面：手机注册 
#### 说明：手机号注册

##### URL
> /v1/phone/storeSignUp

##### 请求方式
> POST

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
nickName       | string | Y    | 昵称
phoneNumber    | string | Y    | 手机号
verifyCode     | string | Y    | 验证码
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码

##### 返回字段
> 无
-------
#### 编号：2-1-015
#### 页面：登录
#### 说明： 手机号登录

##### URL
> /v1/phone/storeSignIn

##### 请求方式
> GET

##### 请求参数
字段        | 类型   | 必选 | 说明
---         | ---    | ---  | ---
phoneNumber | string | Y    | 手机号
password    | string | Y    | 密码

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
customerId        | Long   | 主键id
nickName          | string | 昵称
phoneNumer        | string | 手机号
email             | string | 邮箱
customerSecretkey | string | 用户秘钥
addressId         | long   | 取餐地址id
addressName       | string | 取餐地址
avatarPictureUrl  | string | 用户头像url
shoppingCartId    | Long   | 购物车id
token             | string | 用户token
--------
#### 编号：2-1-016
#### 页面：忘记密码
#### 说明：验证手机号是否存在

##### URL
> /v1/phone/storeVerify

##### 请求方式
> GET

##### 请求参数
字段        |　类型　|必选 | 说明
---         | ---    | --- | ---
phoneNumber | string | Y   | 手机号

##### 返回字段
字段 | 类型 | 说明
--- | --- | ---
status | boolean |
------
#### 编号：2-1-017
#### 页面：找回密码
#### 说明：用户注找回密码送手机证码

##### URL
> /v1/phone/send/storePasswordCode

##### 请求方式
> GET

##### 请求参数
字段        | 类型   | 必选 | 说明
---         | ---    | ---  | ---
phoneNumber | string | Y    | 手机号

##### 返回字段
无
-------
#### 编号：2-1-018
#### 页面：忘记密码
#### 说明：手机验证码校验

##### URL
> /v1/phone/code/storeVerify

##### 请求方式
> GET

##### 请求参数
字段       |　类型　|必选 | 说明
---        | ---    | --- | ---
phoneNumber| string | Y   | 手机号
verifyCode | string | Y   | 验证码

##### 返回字段
字段             | 类型   | 说明
---              | ---    | ---
passwordResetKey | string | 密码修改密匙
--------
#### 编号：2-1-019
#### 页面：邮箱注册 
#### 说明：发送邮箱验证码

##### URL
> /v1/email/send/storeRegisterCode

##### 请求方式
> GET

##### 请求参数
字段  | 类型   | 必选 | 说明
---   | ---    | ---  | ---
email | string | Y    | 邮箱

##### 返回字段
> 无
-------
#### 编号：2-1-020
#### 页面：邮箱注册 
#### 说明：邮箱注册

##### URL
> /v1/email/storeSignUp

##### 请求方式
> POST

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
nickName       | string | Y    | 昵称
email          | string | Y    | 邮箱
verifyCode     | string | Y    | 验证码
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码

##### 返回字段
> 无
-------
#### 编号：2-1-021
#### 页面：登录
#### 说明： 邮箱登录

##### URL
> /v1/email/storeSignIn

##### 请求方式
> GET

##### 请求参数
字段     | 类型   | 必选 | 说明
---      | ---    | ---  | ---
email    | string | Y    | 邮箱
password | string | Y    | 密码

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
customerId        | Long   | 主键id
nickName          | string | 昵称
phoneNumer        | string | 手机号
email             | string | 邮箱
customerSecretkey | string | 用户秘钥
addressId         | long   | 取餐地址id
addressName       | string | 取餐地址
avatarPictureUrl  | string | 用户头像url
shoppingCartId    | Long   | 购物车id
token            | string | 用户token
---------
#### 编号：2-1-022
#### 页面：忘记密码
#### 说明：验证邮箱是否存在

##### URL
> /v1/email/storePasswordCode

##### 请求方式
> GET

##### 请求参数
字段  |　类型　|必选 | 说明
---   | ---    | --- | ---
email | string | Y   | 邮箱

##### 返回字段
字段 | 类型 | 说明
--- | --- | ---
status | boolean |
------
--------
#### 编号：2-1-023
#### 页面：邮箱 找回密码
#### 说明：发送找回密码的邮箱验证码

##### URL
> /v1/email/send/storeVerify

##### 请求方式
> GET

##### 请求参数
字段  | 类型   | 必选 | 说明
---   | ---    | ---  | ---
email | string | Y    | 邮箱

##### 返回字段
> 无
-------
#### 编号：2-1-024
#### 页面：忘记密码
#### 说明：邮箱验证码校验

##### URL
> /v1/email/code/storeVerify

##### 请求方式
> GET

##### 请求参数
字段       |　类型  | 必选 | 说明
---        | ---    | ---  | ---
email      | string | Y   | 手机号
verifyCode | string | Y    | 验证码

##### 返回字段
字段             | 类型   | 说明
---              | ---    | ---
passwordResetKey | string | 密码修改密匙
--------





























#### 编号：2-1-007
#### 页面：登录
#### 说明： 微信登陆，如果是新增用户 创建用户并登陆。返回提示需要 绑定手机号和邮箱

##### URL
> /v1/wechat/customerSignin

##### 请求方式
> GET

##### 请求参数
字段         | 类型   | 必选 | 说明
---          | ---    | ---  | ---
wechatOpenId | string | Y    | 微信openId

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
customerId        | Long   | 主键id
nickName          | string | 昵称
phoneNumer        | string | 手机号
email             | string | 邮箱
customerSecretkey | string | 用户秘钥
addressId         | long   | 取餐地址id
addressName       | string | 取餐地址
avatarPictureUrl  | string | 用户头像url
token             | string | 用户token
---------











#### 编号：2-1-012
#### 页面：重设密码
#### 说明：修改密码(未登录状态)

##### URL
> /v1/password/customerReset

##### 请求方式
> PUT

##### 请求参数
字段             | 类型   | 必选 | 说明
---              | ---    | ---  | ---
password         | string | Y    | 密码
verifyPassword   | string | Y    | 确认密码
resetPasswordKey | string | Y    | 密码修改密匙

##### 返回字段
> 无
--------

#### 编号：2-1-013
#### 页面：重设密码
#### 说明：修改密码（登陆状态）

##### URL
> /v1/password/customerReset

##### 请求方式
> PUT

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
token          | string | Y    | 用户令牌
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码

##### 返回字段
字段              | 类型   | 说明
---               | ---    | ---
token             | string | 用户token （因为密码已经修改 需要新的token）
--------

#### 编号：2-1-025
#### 页面：pc端手机注册 
#### 说明：pc端手机号注册

##### URL
> /v1/phone/pcStoreSignUp

##### 请求方式
> POST

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
phoneNumber    | string | Y    | 手机号
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码
--------
#### 编号：2-1-026
#### 页面：pc端邮箱注册 
#### 说明：pc端邮箱号注册

##### URL
> /v1/email/pcStoreSignUp

##### 请求方式
> POST

##### 请求参数
字段           | 类型   | 必选 | 说明
---            | ---    | ---  | ---
email          | string | Y    | 手机号
password       | string | Y    | 密码
verifyPassword | string | Y    | 确认密码




