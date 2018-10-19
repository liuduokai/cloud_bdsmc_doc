# 接口目录
1. login
2. logout
3. refresh
4. me
****
# 接口详情
## 1.login
***
### 简介
* 使用账户的用户名和密码请求该接口，该接口会返回用于后续操作验证身份的tokan，该账户的信息以及用户所属项目的信息
### 请求
#### 请求地址
cloud.bdsmc.net:8000/login
#### 请求方式
* get
* options
#### 参数
|参数名|是否必填|说明|
|:-:|:-:|:-:|
|email|是|用户名|
|password|是|密码|
#### 请求示例
cloud.bdsmc.net:8000/login?email=xx&password=xx
***
### 返回
#### 请求成功
##### 返回示例
```
{
    "access_token": "xxx",
    "token_type": "xxx",
    "me": {
        "id": xx,
        "email": "xx",
        "name": "xx",
        "phone": "xx",
        "gender": xx,
        "id_number": "xx",
        "home": "xx",
        "project_id": xx,
        "type": xx,
        "created_at": "xx",
        "updated_at": "xx",
        "pro_blo": xx,
        "project": {
            "id": xx,
            "name": "xx",
            "type": xx,
            "created_at": "xx",
            "updated_at": "xx",
            "lt_point": "xx",
            "rd_point": "xx",
            "sate_path": "xx",
            "sate_lvl": "xx",
            "map_path": "xx",
            "map_change_lvl": "xx,18",
            "pro_bord_path": "xx",
            "user_id": xx,
            "center_point": "xx"
        }
    },
    "expires_in": xx
}
```
##### 参数列表
|参数|作用|
|:-:|:-:|
|access_token|进行后续操作验证身份所需要的token|
|token_type|token类型|
|me|用户个人相关信息|
|id|用户id|
|emali|邮箱|
|name|姓名|
|phone|手机|
|gender|性别|
|id_number|身份证号码|
|home|住址|
|project_id|所属项目|
|type|用户类型|
|created_at|创建时间|
|updated_at|更新时间|
|pro_blo|暂无作用|
|project|所属项目信息，内容参见相关接口|
|expires_in|token有效时间|

#### 请求失败
1. 输入密码错误次数过多（超过4次）
2. 输入了错误的用户名和密码
***

## 2.logout
***
### 简介
* 此账户登出，注销此账户的token
### 请求
#### 请求地址
cloud.bdsmc.net:8000/logout
#### 请求方式
* get
* options
#### 参数
* 无
#### 请求示例
cloud.bdsmc.net:8000/logout
***
### 返回
#### 请求成功
##### 返回示例
```
{
    "message": "Successfully logged out"
}
```
##### 参数列表
* 无

#### 请求失败
* token值无效
***

## 3.refresh
***
### 简介
* 重置token的有效时间
### 请求
#### 请求地址
cloud.bdsmc.net:8000/refresh
#### 请求方式
* get
* options
#### 参数
* 无
#### 请求示例
cloud.bdsmc.net:8000/refresh
***
### 返回
#### 请求成功
##### 返回示例
```
{
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9jbG91ZC5iZHNtYy5uZXQ6ODAwMFwvcmVmcmVzaCIsImlhdCI6MTUzOTg0OTUyNiwiZXhwIjoxNTM5ODUzMTY3LCJuYmYiOjE1Mzk4NDk1NjcsImp0aSI6IkJFWnNzTlRmMUhJYzhqQWwiLCJzdWIiOjIwLCJwcnYiOiI4N2UwYWYxZWY5ZmQxNTgxMmZkZWM5NzE1M2ExNGUwYjA0NzU0NmFhIn0.BabRAZ9A4_ia003jf2Mp9TzHZeq5aKNX4uGIKsWEVE8",
    "token_type": "bearer",
    "me": {
        "id": 20,
        "email": "nx_admin",
        "name": "某某某_1",
        "phone": "13600004785",
        "gender": 1,
        "id_number": "430124999912315435",
        "home": "湖南长沙宁乡",
        "project_id": 12,
        "type": 1,
        "created_at": "2018-08-29 15:19:11",
        "updated_at": "2018-08-27 14:29:15",
        "pro_blo": null,
        "project": {
            "id": 12,
            "name": "宁乡市地质灾害监测项目",
            "type": 1,
            "created_at": "2017-08-25 20:08:33",
            "updated_at": "2018-09-21 15:17:41",
            "lt_point": "28.500678,111.867599",
            "rd_point": "27.860932,112.798691",
            "sate_path": "/NingXiang/satellite",
            "sate_lvl": "19",
            "map_path": "/NingXiang/street",
            "map_change_lvl": "11,18",
            "pro_bord_path": "file/border.json",
            "user_id": 133,
            "center_point": "27.901,112.543"
        }
    },
    "expires_in": 3600
}
```
##### 参数列表
* 与login接口返回参数一致

#### 请求失败
* token值无效
***

## 4.me
***
### 简介
* 获取当前登陆用户信息
### 请求
#### 请求地址
cloud.bdsmc.net:8000/me
#### 请求方式
* get
* options
#### 参数
* 无
#### 请求示例
cloud.bdsmc.net:8000/me
***
### 返回
#### 请求成功
##### 返回示例
```
{
    "id": 20,
    "email": "nx_admin",
    "name": "某某某_1",
    "phone": "13600004785",
    "gender": 1,
    "id_number": "430124999912315435",
    "home": "湖南长沙宁乡",
    "project_id": 12,
    "type": 1,
    "created_at": "2018-08-29 15:19:11",
    "updated_at": "2018-08-27 14:29:15",
    "pro_blo": null
}
```
##### 参数列表
* 与login接口返回参数一致

#### 请求失败
* token值无效
***