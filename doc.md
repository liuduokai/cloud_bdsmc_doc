# 接口目录

1. [login](#1)
2. [logout](#2)
3. [refresh](#3)
4. [me](#4)
5. [updateMe](#5)
6. [pick](#6)
7. [gnss](#7)
8. [Update](#8)
9. [Del](#9)
10. [listPois](#10)
11. [addImage](#11)

****

# 接口详情

## <div id = 1>1.login</div>

****

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

****

### 返回

#### 请求成功

##### 返回示例

```json
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

****

## <div i = 2>2.logout</div>

****

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
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "Successfully logged out"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效

****

## <div id = 3>3.refresh</div>

****

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

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "access_token": "xx",
    "token_type": "xx",
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
            "map_change_lvl": "xx",
            "pro_bord_path": "xx",
            "user_id": xx,
            "center_point": "xx"
        }
    },
    "expires_in": xx
}
```

##### 参数列表

* 与login接口返回参数一致

#### 请求失败

* token值无效

****

## <div id = 4>4.me</div>

****

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

****

### 返回

#### 请求成功

##### 返回示例

```json
{
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
    "pro_blo": xx
}
```

##### 参数列表

* 与login接口返回参数一致

#### 请求失败

* token值无效

***

## <div id = 5>5.updateMe</div>

****

### 简介

* 更新当前登录用户的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateMe

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|否|姓名|
|phone|否|手机|
|gender|否|性别|
|home|否|住址|
|id_number|否|身份证号|

#### 请求示例

cloud.bdsmc.net:8000/updateMe?name='xx'&phone='123456'

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效

***

## <div id = 6>6.pick</div>

****

### 简介

* 将一条数据插入到传感器数据表（displacementsensor1）中，并判断数据是否超过预警上下限，若超过预警上下限则在数据库警报表中插入一条新信息并通过mqtt进行通知

### 请求

#### 请求地址

cloud.bdsmc.net:8000/pick

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|传感器id|
|time|是|数据时间|
|value|是|传感器数据|

#### 请求示例

cloud.bdsmc.net:8000/pick?id=xx&time=xx&value=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id在sensors表中不存在

***

## <div id = 7>7.gnss</div>

****

### 简介

* 给设备或监测点添加gnss信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/gnss

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|type|是|添加数据目标的类型，type=1时向设备添加信息，type=2时候向监测点添加信息|
|lat|是|经度|
|lng|是|纬度|
|height|是|高程|

#### 请求示例

cloud.bdsmc.net:8000/pick?type=x&lat=xx&lng=xx&&height=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* 设备或监测点不存在

***

## <div id = 8>8.Update</div>

****

### 简介

* 作用未知，新建一个user对象，若请求中有用户相关信息，则将新对象的相应值赋值，再将当前用户的id赋给此对象中的user_id字段
* ps:此接口中存在问题，插入新对象时插入了不存在的的字段，因此无法正常运行

### 请求

#### 请求地址

cloud.bdsmc.net:8000/Update

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|phone|否|手机|
|name|否|姓名|
|id_number|否|身份证号|
|home|否|住址|
|gende|否|性别|

#### 请求示例

cloud.bdsmc.net:8000/Update?phone=xx&name=xx

****

### 返回

#### 请求成功

无法请求成功

##### 返回示例

无

##### 参数列表

* 无

#### 请求失败

插入了不存在的数据项，任何情况下都会请求失败

***

## <div id = 9>9.Del</div>

****

### 简介

* 接口实现不存在，仅在路由表中有相关字段

***

## <div id = 10>10.listPois</div>

****

### 简介

* 显示登录账户所属的项目下的所有监测点信息，同时返回监测点中设备与照片信息，若登录账户为管理员账户，则列出所有监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listPois

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/listPois

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": xx,
        "id2": xx,
        "project_id": xx,
        "user_id": xx,
        "lngflag": xx,
        "lng": xx,
        "latflag": xx,
        "lat": xx,
        "altitude": xx,
        "init": xx,
        "name": "xx",
        "location": "xx",
        "props": "",
        "created_at": "xx",
        "updated_at": "xx",
        "pinyin": "xx",
        "devices2": [],
        "photos": [],
        "devices": []
    },
    ......
]
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|id|监测点id|
|id2|监测点id2|
|project_id|监测点所属项目id|
|user_id|监测点负责人用户id|
|lngflag|经度标志|
|lng|经度|
|latflag|纬度标志|
|lat|纬度|
|altitude|高度|
|init|未知参数|
|name|监测点名称|
|location|监测点|
|props|未知参数|
|created_at/updated_at|创建/更新时间|
|pinyin|监测点拼音|
|decives2|监测点设备2|
|photos|监测点图像|
|device|监测点设备|


#### 请求失败

* token值无效
* 用户的projectid字段出现问题

***

## <div id = 11>11.addImage</div>

****

### 简介

* 向相应的项目添加图片，可以向项目添加项目照片和项目的信息图片

### 请求

#### 请求地址

cloud.bdsmc.net:8000/addImage

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|poi_id|是|监测点id|
|image|否|项目图片|
|info_image|否|项目信息图片|

#### 请求示例

cloud.bdsmc.net:8000/addImage?poi_id=xx
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "poi_id": "200",
    "path": "file/5bcd3680d083b_u=195531778,3494036849&fm=26&gp=0.jpg",
    "info_path": null,
    "updated_at": "2018-10-22 10:31:28",
    "created_at": "2018-10-22 10:31:28",
    "id": 85
}
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|poi_id|监测点id|
|path|监测点图片路径|
|infopath|监测点信息图片路径|
|updated_at/created_at|创建/更新时间|
|id|图片id|

#### 请求失败

* token值无效
* poi_id参数错误

***