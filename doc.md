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
12. [addPos](#12)
13. [delPos](#13)
14. [delImage](#14)
15. [listPoses](#15)
16. [assignPoi](#16)
17. [searchPoi](#17)
18. [listDevices](#18)
19. [listDevices3](#19)
20. [listSensors](#20)
21. [poi](#21)
22. [device](#22)
23. [devicedata](#23)
24. [history](#24)
25. [UpdateSensor](#25)
26. [listProjects](#26)
27. [listAlarms](#27)
28. [countAlarms](#28)
29. [updateAlarm](#29)
30. [listRegs](#30)
31. [listMaintenances](#31)
32. [addMaintenance](#32)
33. [handleDeviceAlarm](#33)
34. [handleSensorAlarm](#34)
35. [handleCameraAlarm](#35)
36. [getPWD](#36)
37. [login2](#37)
38. [counts](#38)
39. [user2](#39)
40. [listUsers](#40)

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

## <div id = 12>11.addPos</div>

****

### 简介

* 向photopostions表中添加信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/addPos

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|photo_id|是|照片id|
|device_id|是|设备id|
|x|是|在图片中坐标的x值|
|y|是|在图片中坐标的y值|

#### 请求示例

cloud.bdsmc.net:8000/addPos?photo_id=xx&device_id=xx&x=xx&y=xx
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "photo_id": "x",
    "device_id": "xx",
    "x": "x",
    "y": "x",
    "updated_at": "x",
    "created_at": "x",
    "id": x
}
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|photo_id|照片id|
|device_id|设备id|
|x|是|在图片中坐标的x值|
|y|是|在图片中坐标的y值|
|updated_at/created_at|创建/更新时间|
|id|记录表中的id|
#### 请求失败

* token值无效
* photo_id或device_id错误

****

## <div id = 13>13.delPos</div>

****

### 简介

* 删除photopostions表中信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/delPos

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|photopostions表中记录id|

#### 请求示例

cloud.bdsmc.net:8000/delPos?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "del_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id错误

****

## <div id = 14>14.delImage</div>

****

### 简介

* 删除图片

### 请求

#### 请求地址

cloud.bdsmc.net:8000/delImage

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|所需删除图片的id|
|del_flag|否|若存在该项字段说明只删除图片表中的一项信息，若值为1删除项目图片，若为其他值删除项目描述图片

#### 请求示例

cloud.bdsmc.net:8000/delImage?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "del_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id错误

****

## <div id = 15>15.listPoses</div>

****

### 简介

* 查询一张图片中的所有描述信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listPoses

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|所需查询图片的id|

#### 请求示例

cloud.bdsmc.net:8000/listPoses?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": xx,
    "poi_id": xx,
    "path": "xx",
    "created_at": "xx",
    "updated_at": "xx",
    "info_path": "xx",
    "devices": [
        {
            "id": xx,
            "photo_id": xx,
            "device_id": xx,
            "x": xx,
            "y": xx,
            "created_at": "xxx",
            "updated_at": "xxx",
            "device": null
        },
        ......
    ]
    "photopostions": [
        {
            "id": xx,
            "photo_id": xx,
            "device_id": xx,
            "x": xx,
            "y": xx,
            "created_at": "xx",
            "updated_at": "xx",
            "device": xx
        },
        ......
    ]
}

```

##### 参数列表

|名称|说明|
|:-:|:-:|
|id|查询图片的id|
|poi_id|所属监测点的id|
|path|图片路径
|created_at/updated_at|创建/更新时间|
|info_path|项目信息图片路径|
|devices|监测点图片中的设备信息|
|photopostions|图片中描述信息的参数|

#### 请求失败

* token值无效
* id错误

****

## <div id = 16>16.assignPoi</div>

****

### 简介

* 将一个监测点分配给一个用户，仅有管理员账户可以调用此接口

### 请求

#### 请求地址

cloud.bdsmc.net:8000/assignPoi

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|poiId|是|监测点id|
|id|是|管理该监测点的账户id|

#### 请求示例

cloud.bdsmc.net:8000/listPoses?poiId=xx&id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "assign_ok"
}

```

##### 参数列表

* 无
#### 请求失败

* token值无效
* 调用该接口用户不是管理员账户
* poiId或id存在问题

****

## <div id = 17>17.searchPoi</div>

****

### 简介

* 使用监测点名称或设备id搜索监测点

### 请求

#### 请求地址

cloud.bdsmc.net:8000/searchPoi

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|$q|是|搜索参数|

#### 请求示例

cloud.bdsmc.net:8000/searchPoi/xxxxxxx

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
        "props": "xx",
        "created_at": "xx",
        "updated_at": "xx",
        "pinyin": "xx",
        "photos": [xx],
        "devices2": [
            {
                "id": xx,
                "id2": "xx",
                "poi_id": xx,
                "latflag": xx,
                "lat": xx,
                "lngflag": xx,
                "lng": xx,
                "altitude": xx,
                "init": xx,
                "name": "xx",
                "type": xx,
                "dimension": "xx",
                "unit": "xx",
                "color":"xx",
                "online": xx,
                "created_at": "xx",
                "updated_at": "xx",
                "report_cycle": xx,
                "communication_way": xx,
                "version_number": xx,
                "company_name_header": xx,
                "mac": "xx"
            },
            ......
        ],
        "devices": [
            {
                "id": xx,
                "id2": "xx",
                "poi_id": xx,
                "latflag": xx,
                "lat": xx,
                "lngflag": xx,
                "lng": xx,
                "altitude": xx,
                "init": xx,
                "name": "xx",
                "type": xx,
                "dimension": "xx",
                "unit": "xx",
                "color": "xx",
                "online": xx,
                "created_at": "xx",
                "updated_at": "xx",
                "report_cycle": xx,
                "communication_way": xx,
                "version_number": xx,
                "company_name_header": x,
                "mac": "xx"
            },
            ......
         ]
    }

```

##### 参数列表

参数与[listPois](#10)接口中返回参数一致

#### 请求失败

* token值无效
* 当前用户不属于相关项目
* 查询参数出现问题

****

## <div id = 18>18.listDevices</div>

****

### 简介

* 列出监测点下所有设备的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listDevices

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/listDevices?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": xx,
        "id2": "xx",
        "poi_id": xx,
        "latflag": xx,
        "lat": xx,
        "lngflag": xx,
        "lng": xx,
        "altitude": xx,
        "init": xx,
        "name": "xx",
        "type": xx,
        "dimension": "xx",
        "dimension": "xx",
        "color": "xx",
        "online": 0,
        "created_at": "xx",
        "updated_at": "xx",
        "report_cycle": xx,
        "communication_way": xx,
        "version_number": xx,
        "company_name_header": xx,
        "mac": "xx"
    },
    ......
]

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|设备id|
|id2|设备id2|
|poi_id|监测点id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|设备名称|
|type|设备类型|
|dimension|范围|
|color|颜色|
|online|在线|
|created_at/updated_at|创建/更新时间|
|report_cycle|报告周期|
|communication_way|通信方式|
|version_number|版本号|
|company_name_header|公司名称头|
|mac|设备mac|

#### 请求失败

* token值无效
* 调用该接口用户不属于该项目或者不是管理员账户

****

## <div id = 19>19.listDevices3</div>

****

### 简介

* 将用户所属的监测点的设备信息，按分页参数返回

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listDevices3

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|ps|是|每页数据条数|
|pn|页码|

#### 请求示例

cloud.bdsmc.net:8000/listDevices3?ps=xx&pn=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "count": 46,
    "result": [
        {
            "id": 612,
            "id2": "844424933539840",
            "poi_id": 176,
            "latflag": 0,
            "lat": 28.726615,
            "lngflag": 0,
            "lng": 111.623234,
            "altitude": 56.654451,
            "init": 0,
            "name": "0",
            "type": 0,
            "dimension": "0",
            "unit": "0",
            "color": "0",
            "online": 0,
            "created_at": "2018-09-13 10:53:44",
            "updated_at": "2018-09-13 10:54:36",
            "deleted_at": "2018-09-13 10:54:36",
            "report_cycle": null,
            "communication_way": null,
            "version_number": null,
            "company_name_header": "BDWX",
            "mac": "000300000034",
            "pname": "鼎城区花岩溪乡党家庵村滑坡",
            "poi_location": "鼎城区花岩溪乡党家庵村滑坡"
        },
        ......
    ]
}

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|count|符合条件的内容总条数|
|result|查询得到的监测点信息|

#### 请求失败

* token值无效
* 用户不是监测点的负责人或者管理员

****

## <div id = 20>20.listSensors</div>

****

### 简介

* 将用户所属的监测点的设备信息，按分页参数返回

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listSensors

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/listSensors?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 149,
        "id2": "1129215706660872",
        "device_id": 165,
        "lng": 0,
        "lat": 0,
        "name": "小时雨量",
        "type": 0,
        "dimension": "",
        "unit": "ml",
        "min": -100,
        "max": 100,
        "up1": 80,
        "down1": 70,
        "up2": 60,
        "down2": 50,
        "value": 100,
        "color": "",
        "created_at": "2018-05-31 16:27:19",
        "updated_at": "2018-05-31 16:27:19",
        "deleted_at": null,
        "seq": 1
    },
    ......
]

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|传感器id|
|id2|传感器id2|
|device_id|设备id|
|lng|经度|
|lat|纬度|
|name|名称|
|type|类型|
|dimension|范围|
|unit|单位|
|min|最小值|
|max|最大值|
|up1|一级预警上限|
|down1|一级预警下线|
|up2|二级预警上限|
|down2|二级预警下线|
|value|数值|
|color|颜色|
|created_at/updated_at/deleted_at|增删改时间|
|seq|排序号|


#### 请求失败

* token值无效
* 设备id出现错误

****

## <div id = 21>21.poi</div>

****

### 简介

* 根据id返回相应监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/poi

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/poi?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 85,
    "id2": 0,
    "project_id": 12,
    "user_id": 20,
    "lngflag": 0,
    "lng": 112.708638,
    "latflag": 0,
    "lat": 27.979172,
    "altitude": 0,
    "init": 0,
    "name": "nx21",
    "location": "道林镇靳水村季鱼塘上游组（滑坡）",
    "props": "",
    "created_at": "2018-09-13 11:49:41",
    "updated_at": "2018-09-13 11:49:41"
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|监测点id|
|id2|监测点id2|
|project_id|项目id|
|user_id|用户id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|监测点名称|
|location|监测点位置|
|props|参数|
|created_at/updated_at|增改时间|



#### 请求失败

* token值无效
* 监测点id出现问题
* 用户不属于此监测点项目或管理员

****

## <div id = 22>22.device</div>

****

### 简介

* 根据id返回相应设备及其属于的监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/device

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/device?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 256,
    "id2": "1407370588651520",
    "mac": "0004FFFF0001",
    "poi_id": 185,
    "latflag": 0,
    "lat": 0,
    "lngflag": 0,
    "lng": 0,
    "altitude": 0,
    "init": 0,
    "name": "雨量计",
    "type": 0,
    "dimension": "",
    "unit": "",
    "color": "",
    "online": 0,
    "created_at": "2018-08-21 20:17:47",
    "updated_at": "2018-08-21 20:17:47",
    "report_cycle": null,
    "communication_way": null,
    "version_number": null,
    "company_name_header": null,
    "poi": {
        "id": 185,
        "id2": 1,
        "project_id": 20,
        "user_id": 376,
        "lngflag": 0,
        "lng": 213,
        "latflag": 0,
        "lat": 1,
        "altitude": 1,
        "init": 0,
        "name": "测试1",
        "location": "长沙",
        "props": "",
        "created_at": "2018-08-16 10:08:15",
        "updated_at": "2018-08-16 10:08:15"
    }
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|设备id|
|id2|设备id2|
|mac|设备mac|
|poi_id|设备属于的监测点id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|设备名称|
|type|设备类型|
|dimension|范围|
|color|颜色|
|online|在线|
|created_at/updated_at|创建/更新时间|
|report_cycle|报告周期|
|communication_way|通信方式|
|version_number|版本号|
|company_name_header|公司名称头|
|poi|相关监测点信息|

#### 请求失败

* token值无效
* 设备id出现问题
* 用户不属于此设备属于的监测点项目或管理员

****

## <div id = 23>23.devicedata</div>

****

### 简介

* 根据id返回相应设备及其属于的监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/devicedata

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|type|是|查询类型，=1时按小时查询，=2时按天查询|
|device_id|是|设备id|
|start|否|开始时间|
|end|否|结束时间|
#### 请求示例

cloud.bdsmc.net:8000/devicedata?type=xx&device_id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "request": {
        "device_id": "1053",
        "type": "1",
        "image": {}
    },
    "data": [
        {
            "id": 2371542,
            "gps_time": "2018-09-30 15:00:00",
            "device_id": 1053,
            "displacement": 111.622460906
        },
        ......
    ],
    "elapsed time": "0.0025860319213867 s",
      "dataChange": [
        {
            "displacement": 0,
            "gps_time": "2018-09-30 15:00:00",
            "device_id": 1053
        },
        ......
      ]
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|request|请求信息|
|data|设备中的传感器数据|
|elapsed time|函数运行时间|
|dataChange|数据变化值|

#### 请求失败

* token值无效
* 设备id出现问题
* 用户不属于此设备属于的监测点项目或管理员

****

## <div id = 24>24.history</div>

****

### 简介

* 根据设备id返回相应设备在指定时间段中的历史数据

### 请求

#### 请求地址

cloud.bdsmc.net:8000/history

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|
|start|是|开始时间|
|end|是|结束时间|
#### 请求示例

cloud.bdsmc.net:8000/devicedata?id=xx&start=xx&end=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "request": {
        "device_id": "1053",
        "type": "1",
        "image": {}
    },
    "data": [
        {
            "id": 2371542,
            "gps_time": "2018-09-30 15:00:00",
            "device_id": 1053,
            "displacement": 111.622460906
        },
        ......
    ],
    "elapsed time": "0.0025860319213867 s",
      "dataChange": [
        {
            "displacement": 0,
            "gps_time": "2018-09-30 15:00:00",
            "device_id": 1053
        },
        ......
      ]
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|request|请求信息|
|data|设备中的传感器数据|
|elapsed time|函数运行时间|
|dataChange|数据变化值|

#### 请求失败

* token值无效
* 设备id出现问题
* 用户不属于此设备属于的监测点项目或管理员

****

## <div id = 25>25.UpdateSensor</div>

****

### 简介

* 更新设备的一二级预警的上下限值

### 请求

#### 请求地址

cloud.bdsmc.net:8000/UpdateSensor

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|传感器id|
|up1|否|一级预警上限|
|up2|否|二级预警上限|
|down1|否|一级预警下限|
|down2|否|二级预警下限|
#### 请求示例

cloud.bdsmc.net:8000/devicedata?id=xx&up1=xx&down1=xx

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
* 传感器id出现问题
* 上下限值类型出现错误

****

## <div id = 26>26.listProjects</div>

****

### 简介

* 返回当前所有的项目

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listProjects

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/listProjects

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 2,
        "name": "湖南移动天线监测项目",
        "type": 1,
        "created_at": "-0001-11-30 00:00:00",
        "updated_at": "2018-01-08 13:22:14",
        "lt_point": "",
        "rd_point": "",
        "sate_path": "",
        "sate_lvl": "",
        "map_path": "",
        "map_change_lvl": "",
        "pro_bord_path": "",
        "user_id": null,
        "center_point": null
    },
    ......
]
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|项目id|
|name|项目名称|
|type|项目类型|
|created_at/updated_at|增/改时间|
|lt_point|项目地图左上极点|
|rd_point|项目地图右下极点|
|sate_path|卫星地图路径|
|sate_lvl|卫星地图层级|
|map_path|地图路径|
|map_change_lvl|地图改变最大层级|
|pro_bord_path|边界文件路径|
|user_id|项目管理用户id|
|center_point|地图中心点|


#### 请求失败

* token值无效

****

## <div id = 27>27.listAlarms</div>

****

### 简介

* 接口实现文件已被注释

### 请求

#### 请求地址

* 无

#### 请求方式

* 无

#### 参数

* 无

#### 请求示例

* 无

****

### 返回

#### 请求成功

##### 返回示例

* 无

##### 参数列表

*无

#### 请求失败

* 无

****

## <div id = 28>28.countAlarms</div>

****

### 简介

* 返回alarms表中所有state未0的消息计数

### 请求

#### 请求地址

cloud.bdsmc.net:8000/countAlarms

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/countAlarms

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "cnt": 0
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|cnt|满足条件的alarms计数


#### 请求失败

* token值无效

****

## <div id = 29>29.updateAlarm</div>

****

### 简介

* 将相应警报的state更改为1

### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateAlarm

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|$id|是|需要更新的警报的id|

#### 请求示例

cloud.bdsmc.net:8000/updateAlarm/xx

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

****

## <div id = 30>30.listRegs</div>

****

### 简介

* 返回registrations表中相应的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listRegs

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|否|若存在id参数，则返回所有device_id==id的内容（包含user表中信息），否则返回表中所有内容（包含device表中相关信息）

#### 请求示例

cloud.bdsmc.net:8000/listRegs?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 1,
        "user_id": 373,
        "device_id": 230,
        "time": "2018-10-23 09:19:10",
        "created_at": "2018-10-23 09:19:10",
        "updated_at": "2018-10-23 09:19:10",
        "device": {
            "id": 230,
            "id2": 844424930590720,
            "mac": "000300000007",
            "poi_id": 184,
            "latflag": 0,
            "lat": 23.306252,
            "lngflag": 0,
            "lng": 116.241909,
            "altitude": 20.384900000000002,
            "init": 1,
            "name": "一体化位移监测站(流动站)",
            "type": 5,
            "dimension": "",
            "unit": "",
            "color": "",
            "online": 0,
            "created_at": "2018-08-10 08:35:25",
            "updated_at": "2018-08-28 09:30:00",
            "report_cycle": null,
            "communication_way": null,
            "version_number": null,
            "company_name_header": null
        }
    }
]

[
    {
        "id": 1,
        "user_id": 373,
        "device_id": 230,
        "time": "2018-10-23 09:19:10",
        "created_at": "2018-10-23 09:19:10",
        "updated_at": "2018-10-23 09:19:10",
        "user": {
            "id": 373,
            "email": "ltest",
            "name": "lxusj",
            "phone": "17782565539",
            "gender": 1,
            "id_number": "",
            "home": "",
            "project_id": 12,
            "type": 0,
            "created_at": "2018-10-22 09:49:49",
            "updated_at": "2018-07-26 16:30:08",
            "pro_blo": null
        }
    }
]
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|表中数据的编号|
|user_id|用户id|
|device_id|设备id|
|time|时间|
|created_at/updated_at|增/改时间|
|user|用户信息|
|device|设备信息|


#### 请求失败

* token值无效
* id值为不存在的设备

****

## <div id = 31>31.listMaintenances</div>

****

### 简介

* 返回maintenance表中相应的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listMaintenances

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|否|若存在id参数，则返回所有device_id==id的内容（包含user表中信息），否则返回表中所有内容（包含device表中相关信息）

#### 请求示例

cloud.bdsmc.net:8000/listMaintenances?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 1,
        "content": "测试",
        "user_id": 20,
        "device_id": 230,
        "time": "2018-05-28 09:24:40",
        "created_at": "2018-05-28 09:24:40",
        "updated_at": "2018-05-28 09:24:40",
        "user": {
            "id": 20,
            "email": "nx_admin",
            "name": "nxadmin",
            "phone": "13600004785",
            "gender": 1,
            "id_number": "430124999912315435",
            "home": "湖南长沙宁乡",
            "project_id": 12,
            "type": 1,
            "created_at": "2018-10-22 08:55:23",
            "updated_at": "2018-10-22 08:55:24",
            "pro_blo": null
        }
    }
]

[
    {
        "id": 1,
        "content": "测试",
        "user_id": 373,
        "device_id": 230,
        "time": "2018-05-28 09:24:40",
        "created_at": "2018-05-28 09:24:40",
        "updated_at": "2018-05-28 09:24:40",
        "device": {
            "id": 230,
            "id2": 844424930590720,
            "mac": "000300000007",
            "poi_id": 184,
            "latflag": 0,
            "lat": 23.306252,
            "lngflag": 0,
            "lng": 116.241909,
            "altitude": 20.384900000000002,
            "init": 1,
            "name": "一体化位移监测站(流动站)",
            "type": 5,
            "dimension": "",
            "unit": "",
            "color": "",
            "online": 0,
            "created_at": "2018-08-10 08:35:25",
            "updated_at": "2018-08-28 09:30:00",
            "report_cycle": null,
            "communication_way": null,
            "version_number": null,
            "company_name_header": null
        }
    }
]
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|表中数据的编号|
|content|记录名称|
|user_id|用户id|
|device_id|设备id|
|time|时间|
|created_at/updated_at|增/改时间|
|user|用户信息|
|device|设备信息|


#### 请求失败

* token值无效
* id值为不存在的设备

****

## <div id = 32>32.addMaintenance</div>

****

### 简介

* 增加maintenance表中内容

### 请求

#### 请求地址

cloud.bdsmc.net:8000/addMaintenance

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|content|是|数据说明|
|$id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/addMaintenance/xx?content=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 1,
        "content": "测试",
        "user_id": 20,
        "device_id": 230,
        "time": "2018-05-28 09:24:40",
        "created_at": "2018-05-28 09:24:40",
        "updated_at": "2018-05-28 09:24:40",
        "user": {
            "id": 20,
            "email": "nx_admin",
            "name": "nxadmin",
            "phone": "13600004785",
            "gender": 1,
            "id_number": "430124999912315435",
            "home": "湖南长沙宁乡",
            "project_id": 12,
            "type": 1,
            "created_at": "2018-10-22 08:55:23",
            "updated_at": "2018-10-22 08:55:24",
            "pro_blo": null
        }
    }
]

```

##### 参数列表

* 返回参数表同[listMaintenances](#31)中参数列表

#### 请求失败

* token值无效
* id值为不存在的设备

****

## <div id = 33>33.handleDeviceAlarm</div>

****

### 简介

* 操作设备报警信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/handleDeviceAlarm

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|conclusion|是|报警处理结论|
|id|是|报警信息id|

#### 请求示例

cloud.bdsmc.net:8000/handleDeviceAlarm?id=xx&conclusion=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 64,
    "content": "11:46:09 已掉线",
    "type": 4,
    "device_id": 230,
    "state": 1,
    "time": "2018-10-18 11:46:09",
    "conclusion": "test",
    "handleUser": "nxadmin",
    "handleTime": "2018-10-23 09:10:19",
    "created_at": "2018-10-18 11:46:09",
    "updated_at": "2018-10-23 09:51:19"
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|报警信息id|
|content|报警消息|
|type|警报类型|
|device_id|设备id|
|state|状态|
|time|时间|
|conclusion|处理结论|
|handleUser|处理用户|
|handleTime|处理时间|
|created_at/updated_at|增/改时间|

#### 请求失败

* token值无效
* id错误

****

## <div id = 34>34.handleSensorAlarm</div>

****

### 简介

* 操作传感器报警信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/handleSensorAlarm

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|conclusion|是|报警处理结论|
|id|是|报警信息id|

#### 请求示例

cloud.bdsmc.net:8000/handleSensorAlarm?id=xx&conclusion=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 64,
    "content": "高程变化超过一级预警下限1次",
    "type": 1,
    "sensor_id": 1147,
    "state": 1,
    "time": "2018-09-28 23:14:25",
    "conclusion": "test",
    "handleUser": "nxadmin",
    "handleTime": "2018-10-23 10:10:37",
    "created_at": "2018-09-28 23:14:25",
    "updated_at": "2018-10-23 10:03:37"
}
```

##### 参数列表

* 与[handleDeviceAlarm](#33)参数列表中内容基本相同
|参数|说明|
|:-:|:-:|
|sensor_id|c传感器id|

#### 请求失败

* token值无效
* id错误

****

## <div id = 35>35.handleCameraAlarm</div>

****

### 简介

* 操作摄像机报警信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/handleCameraAlarm

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|conclusion|是|报警处理结论|
|id|是|报警信息id|

#### 请求示例

cloud.bdsmc.net:8000/handleCameraAlarm?id=xx&conclusion=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 64,
    "content": "检测到入侵",
    "type": 1,
    "camera_id": 1147,
    "state": 1,
    "time": "2018-09-28 23:14:25",
    "conclusion": "test",
    "handleUser": "nxadmin",
    "handleTime": "2018-10-23 10:10:37",
    "created_at": "2018-09-28 23:14:25",
    "updated_at": "2018-10-23 10:03:37"
}
```

##### 参数列表

* 与[handleDeviceAlarm](#33)参数列表中内容基本相同
|参数|说明|
|:-:|:-:|
|camera_id|摄像机id|

#### 请求失败

* token值无效
* id错误

****

## <div id = 36>36.getPWD</div>

****

### 简介

* 生成短信验证码，并将相应验证码发送给相应的手机

### 请求

#### 请求地址

cloud.bdsmc.net:8000/getPWD

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|phone|手机号码|

#### 请求示例

cloud.bdsmc.net:8000/getPWD?phone=xxxx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "send it"
}
```

##### 参数列表

* 无
#### 请求失败

* token值无效
* id错误

****

## <div id = 37>37.login2</div>

****

### 简介

* 通过手机号码进行登录
### 请求

#### 请求地址

cloud.bdsmc.net:8000/login2

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|phone|手机号码|
|password|验证码|

#### 请求示例

cloud.bdsmc.net:8000/getPWD?phone=xxxx&password=xxx

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

* 与[login](#1)接口返回参数一致

#### 请求失败

* 手机号码错误
* 验证码错误
* 没有请求过验证码

****

## <div id = 38>38.counts</div>

****

### 简介

* 对当前登录用户所属项目的用户、监测点和警报进行计数
### 请求

#### 请求地址

cloud.bdsmc.net:8000/counts

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/counts

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "user": 10,
    "poi": 89,
    "alarm": 0
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|user|用户数量|
|poi|监测点数量|
|alarm|警报数量|

#### 请求失败

* token值错误

****

## <div id = 39>39.user2</div>

****

### 简介

* 根据登录用户的token值获取用户信息 ps:接口逻辑存在问题无法正常使用
### 请求

#### 请求地址

cloud.bdsmc.net:8000/user2

#### 请求方式

* post
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/user2

****

### 返回

#### 请求成功

##### 返回示例

* 无

##### 参数列表

* 无

#### 请求失败

* 无

****

## <div id = 40>40.listUsers</div>

****

### 简介

* 列出当前登录账户所属项目下的所有用户
### 请求

#### 请求地址

cloud.bdsmc.net:8000/listUsers

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/listUsers

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 20,
        "email": "nx_admin",
        "name": "nxadmin",
        "phone": "13600004785",
        "gender": 1,
        "id_number": "430124999912315435",
        "home": "湖南长沙宁乡",
        "project_id": 12,
        "type": 1,
        "created_at": "2018-10-22 08:55:23",
        "updated_at": "2018-10-22 08:55:24",
        "pro_blo": null
    },
   ......
]
```

##### 参数列表

|参数|说明|

* 与[login](#1)接口中返回参数一致

#### 请求失败

* token值错误
* 当前登录用户不是管理员账户

****

