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
41. [addUser](#41)
42. [addUserList](#42)
43. [updateUser](#43)
44. [delUser](#44)
45. [addProjectFile2](#45)
46. [listProjects2](#46)
47. [addProject2](#47)
48. [updateProject2](#48)
49. [delProject2](#49)
50. [listUsers2](#50)
51. [addUser2](#51)
52. [updateUser2](#52)
53. [delUser2](#53)
54. [listPois2](#54)
55. [addPoi2](#55)
56. [updatePoi2](#56)
57. [delPoi2](#57)
58. [listDevices2](#58)
59. [addDevice2](#59)
60. [updateDevice2](#60)
61. [delDevice2](#61)
62. [listSensors2](#62)
63. [addSensor2](#63)
64. [updateSensor2](#64)
65. [delSensor2](#65)
66. [videosource](#66)
67. [videoList](#67)
68. [videoHistory](#68)
69. [insar](#69)
70. [insarData](#70)
71. [genImage](#71)
72. [GaodeCoord](#72)
73. [deviceAlarmsById](#73)
74. [cameraAlarmsById](#74)
75. [alarmsSensor](#75)
76. [alarmsDevice](#76)
77. [alarmsCamera](#77)
78. [UsersLog](#78)

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

## <div id = 2>2.logout</div>

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
|id|是|photopostions表中记录id|

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
|id|是|所需删除图片的id|
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
|phone|是|手机号码|

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
|phone|是|手机号码|
|password|是|验证码|

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

## <div id = 41>41.addUser</div>

****

### 简介

* 添加新用户
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addUser

#### 请求方式

* get
* options

#### 参数


|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|是|姓名|
|email|是|邮箱|
|password|是|密码|
|project_id|是|所属项目|
|phone|是|手机|
|home|否|住址|
|type|否|类型|
|id_number|否|身份证号|
|gender|否|性别|

#### 请求示例

cloud.bdsmc.net:8000/addUser?email=xxx&password=xxx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "name": "qwerqweq",
    "email": "qwerrewq@qwer.com",
    "project_id": "2",
    "phone": "11111111111",
    "updated_at": "2018-10-23 14:07:58",
    "created_at": "2018-10-23 14:07:58",
    "id": 390
}
```

##### 参数列表

* 参数与[login](#1)接口中同名参数一致
  
#### 请求失败

* token值错误
* 部分不允许重复的信息出现重复

****

## <div id = 42>42.addUserList</div>

****

### 简介

* 通过文件批量添加新用户
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addUserList

#### 请求方式

* post
* options

#### 参数


|参数名|是否必填|说明|
|:-:|:-:|:-:|
|file|包含用户信息的文件|
##### 文件中所需数据格式
* 文件从第二行开始读取数据，第一行为表头

|列数|参数名|是否必须|说明|
|:-:|:-:|:-:|:-:|
|1|email|是|邮箱/用户名|
|2|password|是|密码|
|3|name|是|姓名|
|4|gender|否|性别|
|5|phone|是|手机|
|6|id_number|否|身份证号|
|7|home|否|住址|
|8|project_id|否|所属项目id|
#### 请求示例

cloud.bdsmc.net:8000/addUserList

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "add_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* 文件中的信息出现错误

****

## <div id = 43>43.updateUser</div>

****

### 简介

* 更新用户信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateUser

#### 请求方式

* get
* options

#### 参数


|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|用户id|
|email|是|用户名/邮箱|
|name|是|姓名|
|phone|是|手机号码|
|gender|否|性别|
|type|否|类型|
|password|否|密码|
|home|否|住址|
|id_number|否|身份证号|

#### 请求示例

cloud.bdsmc.net:8000/updateUser

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
* 输入了错误的参数
  
****

## <div id = 44>44.delUser</div>

****

### 简介

* 将相应的用户删除
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delUser

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|用户id|

#### 请求示例

cloud.bdsmc.net:8000/delUser?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
1
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* 用户id错误
  
****

## <div id = 45>45.addProjectFile2</div>

****

### 简介

* 上传项目地图的边界文件
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addProjectFile2

#### 请求方式

* get
* options
* post

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|pro_bord_path|是|项目地图边界文件|

#### 请求示例

cloud.bdsmc.net:8000/addProjectFile2

****

### 返回

#### 请求成功

##### 返回示例

* 无

##### 参数列表

* 无

#### 请求失败

* token值无效
* 文件错误
  
****

## <div id = 46>46.listProjects2</div>

****

### 简介

* 返回用户所负责的项目列表/所有项目（管理员账户）
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/listProjects2

#### 请求方式

* get
* options
* post

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/listProjects2

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

* 参数列表与[listProjects](#26)接口返回参数一致

#### 请求失败

* token值无效
  
****

## <div id = 47>47.addProject2</div>

****

### 简介

* 增加项目
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addProject2

#### 请求方式

* get
* options
* post

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|是|项目名称|
|lt_point|是|左上极点|
|rd_point|是|右下极点|
|center_point|是|地图中心点|
|sate_path|是|卫星地图路径|
|map_path|是|地图路径|
|map_change_lvl|是|地图改变级别|
|user_id|否|负责用户id|


#### 请求示例

cloud.bdsmc.net:8000/addProject2?name=xx&......

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "add_ok",
    "project": {
        "name": "测试测试测试",
        "lt_point": "12",
        "rd_point": "34",
        "center_point": "123",
        "sate_path": "123",
        "map_path": "123",
        "map_change_lvl": "123",
        "updated_at": "2018-10-23 15:40:06",
        "created_at": "2018-10-23 15:40:06",
        "id": 63
    }
}
```
##### 参数列表

* 参数列表与[listProjects](#26)接口返回项目信息参数一致

#### 请求失败

* token值无效
  
****

## <div id = 48>48.updateProject2</div>

****

### 简介

* 更新项目
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateProject2

#### 请求方式

* get
* options
* post

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|是|项目名称|
|lt_point|是|左上极点|
|rd_point|是|右下极点|
|center_point|是|地图中心点|
|sate_path|是|卫星地图路径|
|map_path|是|地图路径|
|map_change_lvl|是|地图改变级别|
|user_id|否|负责用户id|


#### 请求示例

cloud.bdsmc.net:8000/updateProject2?name=xx&......

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "add_ok",
    "project": {
        "name": "测试测试测试",
        "lt_point": "12",
        "rd_point": "34",
        "center_point": "123",
        "sate_path": "123",
        "map_path": "123",
        "map_change_lvl": "123",
        "updated_at": "2018-10-23 15:40:06",
        "created_at": "2018-10-23 15:40:06",
        "id": 63
    }
}
```
##### 参数列表

* 参数列表与[listProjects](#26)接口返回项目信息参数一致

#### 请求失败

* token值无效
  
****

## <div id = 49>49.delProject2</div>

****

### 简介

* 更新项目
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delProject2

#### 请求方式

* get
* options
* post

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|项目id|

#### 请求示例

cloud.bdsmc.net:8000/delProject2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "del_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* id值不是有效的id值
  
****

## <div id = 50>50.listUsers2</div>

****

### 简介

* 返回项目中的所有用户
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delProject2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|否|项目id，若有此参数则返回项目中所有用户，若没有此参数且用户为管理员，返回所有用户信息|

#### 请求示例

cloud.bdsmc.net:8000/delProject2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "del_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* id值不是有效的id值
* 没有传递id参数且登录账户不是管理员账户
  
****

## <div id = 51>51.addUser2</div>

****

### 简介

* 添加新用户
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addUser2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|否|姓名|
|email|否|邮箱/用户名|
|password|否|密码|
|project_id|否|所属项目id|
|phone|否|手机|
|home|否|住址|
|type|否|类型|
|id_number|否|身份证号码|
|gender|否|性别|

#### 请求示例

cloud.bdsmc.net:8000/addUser2?name=xx&email=xx&password=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "add_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入参数与已有账户重复
  
****

## <div id = 52>52.updateUser2</div>

****

### 简介

* 更新用户信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateUser2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|否|姓名|
|email|否|邮箱/用户名|
|password|否|密码|
|project_id|否|所属项目id|
|phone|否|手机|
|home|否|住址|
|type|否|类型|
|id_number|否|身份证号码|
|gender|否|性别|

#### 请求示例

cloud.bdsmc.net:8000/updateUser2?name=xx&email=xx&password=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "update_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入参数与已有账户重复
  
****

## <div id = 53>53.delUser2</div>

****

### 简介

* 删除用户
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delUser2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|用户id|

#### 请求示例

cloud.bdsmc.net:8000/delUser2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
1
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入id有误
  
****

## <div id = 54>54.listPois2</div>

****

### 简介

* 返回项目中所有的监测点
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/listPois2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|项目id|

#### 请求示例

cloud.bdsmc.net:8000/listPois2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
[
    {
        "id": 86,
        "id2": 0,
        "project_id": 12,
        "user_id": 133,
        "lngflag": 0,
        "lng": 112.612778,
        "latflag": 0,
        "lat": 28.120278,
        "altitude": 0,
        "init": 0,
        "name": "nx22",
        "location": "东湖塘镇西冲山村上马组（滑坡）",
        "props": "",
        "created_at": "2018-09-13 11:51:02",
        "updated_at": "2018-09-13 11:51:02",
        "photos": [
            {
                "id": 74,
                "poi_id": 86,
                "path": null,
                "created_at": "2018-09-17 09:34:56",
                "updated_at": "2018-09-17 09:34:56",
                "info_path": "file/5b9f04c0d90d2_dcq_htd_xujiazui.jpg",
                "devices": [],
                "photopostions": []
            }
        ]
    },
    ......
]
```
##### 参数列表

* 与接口[listPois](#10)参数一致

#### 请求失败

* token值无效
* 项目id错误
  
****

## <div id = 55>55.addPoi2</div>

****

### 简介

* 添加监测点
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addPoi2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|是|监测点名称|
|location|是|监测点位置|
|project_id|是|监测点所属项目id|
|id2|是|监测点id2|
|user_id|否|管理用户id|
|lng|否|经度|
|lat|否|纬度|
|altitude|否|高程|

#### 请求示例

cloud.bdsmc.net:8000/addPoi2?name=xx&location=xx&projet_id=xx&id2=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "add_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入其他参数错误
  
****

## <div id = 56>56.updatePoi2</div>

****

### 简介

* 更新监测点信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updatePoi2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|
|name|否|监测点名称|
|location|否|监测点位置|
|project_id|否|监测点所属项目id|
|id2|否|监测点id2|
|user_id|否|管理用户id|
|lng|否|经度|
|lat|否|纬度|
|altitude|否|高程|

#### 请求示例

cloud.bdsmc.net:8000/updatePoi2?id=xx&id2=xx&name=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "update_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入其他参数错误
  
****

## <div id = 57>57.delPoi2</div>

****

### 简介

* 删除监测点
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delPoi2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/delPoi2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "del_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传入其他参数错误
  
****

## <div id = 58>58.listDevices2</div>

****

### 简介

* 列出监测点下设备信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/listDevices2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/listDevices2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
[
    {
        "id": 570,
        "id2": "844424931246080",
        "mac": "000300000011",
        "poi_id": 179,
        "latflag": 0,
        "lat": 29.616547,
        "lngflag": 0,
        "lng": 111.855236,
        "altitude": 45.3971,
        "init": 1,
        "name": "GNSS-1",
        "type": 0,
        "dimension": "",
        "unit": "",
        "color": "",
        "online": 1,
        "created_at": "2018-08-24 18:03:08",
        "updated_at": "2018-09-13 10:19:51",
        "report_cycle": null,
        "communication_way": null,
        "version_number": null,
        "company_name_header": null
    },
    ......
]
```
##### 参数列表

* 返回参数与接口[listDevices](#18)相同

#### 请求失败

* token值无效
* 监测点id错误
  
****

## <div id = 59>59.addDevice2</div>

****

### 简介

* 增加设备
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addDevice2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|poi_id|是|监测点id|
|name|是|设备名称|
|id2|是|设备id2|
|lng|否|经度|
|lat|否|纬度|
|altitude|否|高程|
|dimension|否|面积|
|unit|否|单位|
|type|否|类型，若设备类型为5，会同时将数据插入到qianxun和gnss数据表中

#### 请求示例

cloud.bdsmc.net:8000/addDevice2?poi_id=xx&name=xx&id2=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "add_ok",
    "id":1,
}
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|id|设备id|

#### 请求失败

* token值无效
* 传入其他参数错误
  
****

## <div id = 60>60.updateDevice2</div>

****

### 简介

* 更新设备信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateDevice2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|
|poi_id|是|监测点id|
|name|是|设备名称|
|lng|否|经度|
|lat|否|纬度|
|altitude|否|高程|
|dimension|否|面积|
|unit|否|单位|

#### 请求示例

cloud.bdsmc.net:8000/updateDevice2?id=xx&poi_id=xx&name=xx&id2=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "update_ok",
}
```
##### 参数列表

|参数|说明|

* 无

#### 请求失败

* token值无效
* 设备id错误
  
****

## <div id = 61>61.delDevice2</div>

****

### 简介

* 删除设备信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delDevice2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/delDevice2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "del_ok",
}
```
##### 参数列表

|参数|说明|

* 无

#### 请求失败

* token值无效
* 设备id错误
  
****

## <div id = 62>62.listSensors2</div>

****

### 简介

* 返回设备中所有传感器的参数
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/listSensors2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/listSensors2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
[
    {
        "id": 176,
        "id2": "848844552339526",
        "device_id": 179,
        "lng": 0,
        "lat": 0,
        "name": "经度",
        "type": 0,
        "dimension": "",
        "unit": "度",
        "min": -100,
        "max": 100,
        "up1": 100000,
        "down1": -10000,
        "up2": 100000,
        "down2": -10000,
        "value": 10,
        "color": "",
        "created_at": "2018-07-16 17:30:09",
        "updated_at": "2018-07-16 17:30:09",
        "seq": null
    },
    ......
]
```
##### 参数列表

* 无

* 与接口[listSensors](#20)返回参数一致

#### 请求失败

* token值无效
* 设备id错误
  
****

## <div id = 63>63.addSensor2</div>

****

### 简介

* 增加传感器
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/addSensor2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|device_id|是|设备id|
|name|是|传感器名称|
|id2|是|传感器id2|
|up1|否|一级预警上限|
|up2|否|二级预警上限|
|down1|否|一级预警下限|
|down2|否|二级预警下限|
|unit|否|单位|
|value|否|数值|

#### 请求示例

cloud.bdsmc.net:8000/addSensor2?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "add_ok",
}
```
##### 参数列表

* 与接口[listSensors](#20)返回参数一致

#### 请求失败

* token值无效
    
****

## <div id = 64>64.updateSensor2</div>

****

### 简介

* 更新传感器信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateSensor2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|传感器id|
|device_id|否|设备id|
|name|否|传感器名称|
|id2|否|传感器id2|
|up1|否|一级预警上限|
|up2|否|二级预警上限|
|down1|否|一级预警下限|
|down2|否|二级预警下限|
|unit|否|单位|
|value|否|数值|

#### 请求示例

cloud.bdsmc.net:8000/updateSensor2?id=xx&name=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "update_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传感器id错误
  
****

## <div id = 65>65.delSensor2</div>

****

### 简介

* 删除传感器
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/delSensor2

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|传感器id|

#### 请求示例

cloud.bdsmc.net:8000/delSensor2?id=xx

****

### 返回

#### 请求成功

##### 返回示例
```json
{
    "message": "del_ok",
}
```
##### 参数列表

* 无

#### 请求失败

* token值无效
* 传感器id错误
  
****



## <div id = 66>66.videosource</div>

****

### 简介

* 根据摄像头pid请求视频播放地址(接口未使用，设备不在线，请求只会返回失败信息)
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/videosource

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|puid|是|摄像头puid|

#### 请求示例

cloud.bdsmc.net:8000/videosource?puid=xx

****

### 返回

#### 请求成功

##### 返回示例

* 无

##### 参数列表

* 无

#### 请求失败

* 因设备无法长时间在线，请求必定返回失败值

****

## <div id = 67>67.videoList</div>

****

### 简介

* 返回视频设备列表
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/videoList

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|page|是|页码|
|rows|是|行数|

#### 请求示例

cloud.bdsmc.net:8000/videoList?page=xx&rows=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{"code":0,"msg":"success","total":"4","rows":[]}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|code|状态码|
|msg|状态消息|
|total|设备总数|
|rows|设备信息|

#### 请求失败

* token值无效
* 行列信息无效

****

## <div id = 68>68.videoHistory</div>

****

### 简介

* 返回摄像头设备的历史数据（接口已弃用，因为摄像头并无常在线，也没有返回监控数据所以请求必定返回失败值）
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/videoHistory

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|puid|是|页码|
|begin|是|开始时间|
|end|是结束时间|

#### 请求示例

cloud.bdsmc.net:8000/videoHistory?puid=xx&begin=xx&end=xx

****

### 返回

#### 请求成功

##### 返回示例

* 无

##### 参数列表

* 无

#### 请求失败

* 请求必定失败
****

## <div id = 69>69.insar</div>

****

### 简介

* 查看insar数据，当有用户type==3时仅返回mean_velocity<-20的值
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/insar

#### 请求方式

* get
* options

#### 参数

*无

#### 请求示例

cloud.bdsmc.net:8000/insar

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    "color": "FFFF0000",
            "insars": [
                {
                    "id": 4855,
                    "latitude": "28.251137",
                    "longitude": "112.414267",
                    "lng_g": "112.419992675782",
                    "lat_g": "28.247960069445",
                    "mean_velocity": -21.14
                },
                ......
            ]
]
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|color|颜色|
|insars|insars数据|

#### 请求失败

* token值错误
* 项目中没有insar信息

****

## <div id = 70>70.insarData</div>

****

### 简介

* 获取insar数据
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/insarData

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|insar id|

#### 请求示例

cloud.bdsmc.net:8000/insarData?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 1,
    "latitude": "28.363493",
    "longitude": "112.638301",
    "lng_g": "112.643679470487",
    "lat_g": "28.359995659723",
    "color": "FF61FFDA",
    "range": 2404,
    "azimuth": 14,
    "point_height": 51.67,
    "mean_velocity": 2.87,
    "height_correction": 5.88,
    "coherence": 0.91,
    "musigma": 4.91,
    "h_precision": 6.13,
    "v_precision": 1.91,
    "data": [
        {
            "id": 1,
            "insar_id": 1,
            "time": 1496505600,
            "value": "0.00"
        },
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|id|insar id|
|latitude|经度|
|longitude|纬度|
|lng_g|另一种精度的纬度|
|lat_g|另一种精度的经度|
|color|颜色|
|range|范围|
|azimuth||
|point_height||
|mean_velocity||
|height_correction||
|coherence||
|musigma||
|h_precision||
|v_precision||
|data|insars数据|

#### 请求失败

* token值错误
* insar id错误

****

## <div id = 71>71.genImage</div>

****

### 简介

* 获取指定颜色的图片
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/genImage

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|color|是|图片颜色|

#### 请求示例

cloud.bdsmc.net:8000/genImage?color=xx

****

### 返回

#### 请求成功

##### 返回示例

* 返回值为一张12 *12的相应颜色图片

##### 参数列表

* 无

#### 请求失败

* token值错误
****

## <div id = 72>72.GaodeCoord</div>

****

### 简介

* 更新insar相关信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/GaodeCoord

#### 请求方式

* get
* options

#### 参数

参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|insar id|
|lng_g|是|纬度|
|lat_g|是|经度|

#### 请求示例

cloud.bdsmc.net:8000/GaodeCoord?id=xx&lng_g=xx&lat_g=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "msg": "ok",
}  
```
##### 参数列表

* 无

#### 请求失败

* token值错误
****

## <div id = 73>73.deviceAlarmsById</div>

****

### 简介

* 根据设备id查询报警信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/deviceAlarmsById

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|
|pn|是|页码|
|ps|是|页大小|

#### 请求示例

cloud.bdsmc.net:8000/deviceAlarmsById?id=xx&ps=xx&pn=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 3,
        "content": "10:23:45 已掉线",
        "type": 4,
        "device_id": 230,
        "state": 0,
        "time": "2018-10-16 10:23:45",
        "conclusion": null,
        "handleUser": null,
        "handleTime": null,
        "created_at": "2018-10-16 10:23:45",
        "updated_at": null
    },
    ......
]
```
##### 参数列表

* 与[handleDeviceAlarm](#33)接口中返回的参数一致

#### 请求失败

* token值错误
* 请求id不存在
* 请求页数超出数据范围
  
****

## <div id = 74>74.cameraAlarmsById</div>

****

### 简介

* 根据摄像机id查询报警信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/cameraAlarmsById

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|摄像机id|
|pn|是|页码|
|ps|是|页大小|

#### 请求示例

cloud.bdsmc.net:8000/cameraAlarmsById?id=xx&ps=xx&pn=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 3,
        "content": "检测到入侵",
        "type": 4,
        "device_id": 230,
        "state": 0,
        "time": "2018-10-16 10:23:45",
        "conclusion": null,
        "handleUser": null,
        "handleTime": null,
        "created_at": "2018-10-16 10:23:45",
        "updated_at": null
    },
    ......
]
```
##### 参数列表

* 与[handleDeviceAlarm](#33)接口中返回的参数一致

#### 请求失败

* token值错误
* 请求id不存在
* 请求页数超出数据范围
  
****

## <div id = 75>75.alarmsSensor</div>

****

### 简介

* 返回传感器报警信息
* 根据不同条件过滤警报信息，返回过滤后的警报信息，若未传入参数管理员账户返回项目下所有监测点的报警信息，普通用户返回所属监测点下所有账户信息
* 接口目前仅支持单条件过滤，暂时不支持多条件过滤
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/alarmsSensor

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|ps|是|页面大小|
|pn|是|页码|
|id2|否|设备id2|
|id|否|设备id|
|lvl|否|警报等级|
|starttime|否|开始时间|
|endtime|否|结束时间|
|poiid|否|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/alarmsSensor?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "totalCount": 99,
    "alarms": [
        {
            "id": 940,
            "content": "偏北超过二级预警下限1次",
            "type": 2,
            "sensor_id": 940,
            "state": 0,
            "time": "2018-10-24 15:32:11",
            "conclusion": null,
            "handleUser": null,
            "handleTime": null,
            "created_at": "2018-10-24 15:32:11",
            "updated_at": null,
            "deleted_at": null,
            "name": "GNSS-1",
            "sensor_name": "偏北",
            "poi_name": "津市古大同老果园滑坡滑坡",
            "poi_location": "津市古大同老果园滑坡滑坡",
            "up1": 300,
            "down1": -300,
            "up2": 80,
            "down2": -80
        },
        ......
    ]
}
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|totalCount|预警信息总数|
|alarms|预警信息|
#### 请求失败

* token值错误
* 请求过滤条件参数错误
* 请求页数超出数据范围
  
****

## <div id = 76>76.alarmsDevice</div>

****

### 简介

* 返回设备报警信息
* 根据不同条件过滤警报信息，返回过滤后的警报信息，若未传入参数管理员账户返回项目下所有监测点的报警信息，普通用户返回所属监测点下所有账户信息
* 接口目前仅支持单条件过滤，暂时不支持多条件过滤
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/alarmsDevice

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|ps|是|页面大小|
|pn|是|页码|
|id2|否|设备id2|
|id|否|设备id|
|lvl|否|警报等级|
|starttime|否|开始时间|
|endtime|否|结束时间|
|poiid|否|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/alarmsDevice?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "totalCount": 2,
    "alarms": [
        {
            "id": 88,
            "content": "12:05:00 已上线",
            "type": 5,
            "device_id": 570,
            "state": 0,
            "time": "2018-10-22 12:05:00",
            "conclusion": null,
            "handleUser": null,
            "handleTime": null,
            "created_at": "2018-10-22 12:05:00",
            "updated_at": null,
            "deleted_at": null,
            "name": "GNSS-1",
            "poi_name": "津市古大同老果园滑坡滑坡",
            "poi_location": "津市古大同老果园滑坡滑坡"
        },
        ......
    ]
}
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|totalCount|预警信息总数|
|alarms|预警信息|
#### 请求失败

* token值错误
* 请求过滤条件参数错误
* 请求页数超出数据范围
  
****

## <div id = 77>77.alarmsCamera</div>

****

### 简介

* 返回摄像头报警信息
* 根据不同条件过滤警报信息，返回过滤后的警报信息，若未传入参数管理员账户返回项目下所有监测点的报警信息，普通用户返回所属监测点下所有账户信息
* 接口目前仅支持单条件过滤，暂时不支持多条件过滤
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/alarmsCamera

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|ps|是|页面大小|
|pn|是|页码|
|id2|否|摄像机id2|
|id|否|摄像机id|
|lvl|否|警报等级|
|starttime|否|开始时间|
|endtime|否|结束时间|
|poiid|否|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/alarmsCamera?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "totalCount": 1,
    "alarms": [
        {
            "id": 1,
            "content": "21",
            "type": 2,
            "camera_id": 5,
            "state": 0,
            "time": "2018-10-24 17:08:43",
            "conclusion": "1",
            "handleUser": "1",
            "handleTime": "2018-09-05 17:08:40",
            "created_at": "2018-10-24 17:08:43",
            "updated_at": null,
            "deleted_at": null,
            "name": "视频监控",
            "poi_name": "澧县火连坡镇芦桥村4组滑坡",
            "poi_location": "澧县火连坡镇芦桥村4组滑坡"
        },
        ......
    ]
}
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|totalCount|预警信息总数|
|alarms|预警信息|
#### 请求失败

* token值错误
* 请求过滤条件参数错误
* 请求页数超出数据范围
  
****

## <div id = 78>78.UsersLog</div>

****

### 简介

* 返回用户操作日志
* 仅有管理员可以使用此接口
* 仅会记录对数据库改动的操作
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/UsersLog

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/UsersLog

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 12,
        "user_id": 1,
        "content": "addUser",
        "time": "2018-07-26 15:10:03",
        "type": 1,
        "created_at": "2018-07-26 15:10:03",
        "updated_at": "2018-07-26 15:10:03",
        "deleted_at": null,
        "name": "YM"
    },
    ......
]
```
##### 参数列表

|参数|说明|
|:-:|:-:|
|id|记录id|
|user_id|操作用户id|
|content|操作内容|
|time|操作日志|
|type|操作类型 type 1=add 2=del   3=upd|
|created_at/updated_at/deleted_at|增删改时间|
|name|操作用户姓名|
#### 请求失败

* token值错误
* 用户没管理员权限

****